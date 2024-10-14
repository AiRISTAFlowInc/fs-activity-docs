# ParseNPIPayload

This activity parses the payload from a parsed packet to extract and structure relevant data fields.

## Configuration

### Input:
| Name       | Type   | Description
|:---        | :---   | :---    
| ParsedPacket | object | The json object containing the packet data to be processed, including fields like CommandID and Payload.

### Output:

| Name   | Type    | Description                       |
| :----- | :------ | :-------------------------------- |
| ParsedPayload | object | The json object that contains the extracted and structured data fields from the input packet.
