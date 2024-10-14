<!--
title: MergeNPIPayload
weight: 4705
-->
# FSMergeNPIPayload
This activity processes MQTT messages by buffering, combining, and averaging RSSI data from multiple sources before publishing the refined payload to a specified MQTT topic.

## Installation

### Flogo CLI
```bash
flogo install github.com/AiRISTAFlowInc/fs-activity/tree/main/FSMergeNPIPayload
```

## Configuration

### Settings:
| Name           | Type   | Description
| :---           | :---   | :---
| interval       | int    | The time in milliseconds to wait before processing and publishing buffered data for each unique MAC address - ***REQUIRED***
| ignoreInterval | int    | Ignore interval for same SQN - ***REQUIRED***
| broker         | string | The broker URL - ***REQUIRED***
| id             | string | The id of client - ***REQUIRED***
| username       | string | The name of the user
| password       | string | The password of the user
| store          | string | The store for message persistence
| cleanSession   | bool   | Clean session flag
| topic          | string | The topic to publish to
| retain         | bool   | Retain Messages       
| qos            | int    | The quality of service
| sslConfig      | object | SSL configuration

 #### *sslConfig* Object:
 | Property      | Type   | Description
 |:---           | :---   | :---     
 | skipVerify    | bool   | Skip SSL validation, defaults to true
 | useSystemCert | bool   | Use the systems root certificate file, defaults to true
 | caFile        | string | The path to PEM encoded root certificates file
 | certFile      | string | The path to PEM encoded client certificate
 | keyFile       | string | The path to PEM encoded client key

 *Note: used if broker URI is ssl*

### Input:

| Name              | Type   | Description
| :---              | :---   | :---
| parsedPayload     | object | input JSON object containing the data to be processed, including fields like MAC, BLESQN, SourceMAC, and SourceRSSI.
