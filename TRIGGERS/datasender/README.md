<!--
title: datasender
weight: 4705
-->
# Simple Data Send Trigger

This trigger sends simple string data to the flow only one time

## Configuration

### Setting :

| Name         | Type     | Description
|:---          | :---     | :---   
| inputdata    | string   | The input data for test

### Output:

| Name         | Type     | Description
|:---          | :---     | :---   
| output       | array    | the output data

### Reply:

| Name         | Type     | Description
|:---          | :---     | :---   
| reply        | string   | The data to be sent back to the client

## Examples

```json
{
  "triggers": [
    {
      "id": "simple_data_sender",
      "ref": "#FSDataSender",
      "name": "Simple Data Sender",
      "description": "Simple Data Sender",
      "settings": {
        "inputdata": "test data"
      },
      "handlers": [
        {
          "action": {
            "ref": "#fs-flow",
            "settings": {
              "flowURI": "res://flow:tester"
            },
            "input": {
              "data": "=$.output"
            },
            "output": {
              "reply": "=$.mappings"
            }
          }
        }
      ]
    }
  ]
}
```