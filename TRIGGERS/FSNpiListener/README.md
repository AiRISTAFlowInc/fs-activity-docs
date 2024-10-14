<!--
title: TCP/UDP
weight: 4701
-->
# NPI Packet Listener Trigger

This trigger reads NPI Packet from tcp/udp

## Configuration

### Setting :

| Name       | Type    | Description
|:---        | :---    | :---     
| network    | string  | Network type. Supported types: tcp,tcp4,tcp6,udp,udp4,udp6  - ***REQUIRED***
| host       | string  | Host IP or DNS resolvable name
| port       | string  | Port to listen on - ***REQUIRED***
| delimiter  | string  | Sof of NPI Packet
| timeout    | integer | Read and Write timeout in milliseconds. To disable timeout, set value to 0.


### Output:

| Name         | Type     | Description
|:---          | :---     | :---   
| data         | array    | the bytes of NPI packet

### Reply:

| Name         | Type     | Description
|:---          | :---     | :---   
| reply        | string   | The data to be sent back to the client

## Examples

```json
{
  "triggers": [
          {
              "ref": "github.com/AiRISTAFlowInc/fs-contrib/trigger/FSNpiListener",
              "name": "ReceiveTCPData",
              "settings": {
                  "network": "tcp4",
                  "host": "localhost",
                  "port": "8999",
                  "delimiter": 254,
                  "timeout": 200
              },
              "id": "ReceiveTCPData",
              "handlers": [
                  {
                      "settings": {},
                      "action": {
                          "ref": "github.com/AiRISTAFlowInc/fs-flow",
                          "settings": {
                              "flowURI": "res://flow:TCP"
                          },
                          "input": {
                              "packet": "=$.data"
                          },
                          "output": {
                              "reply": "=$.reply"
                          }
                      },
                      "reply": {
                          "reply": ""
                      }
                  }
              ]
          }
      ]
}
```