# SendMessageToAssets

This activity sends a message to a specified asset.

## Configuration

### Input:

| Name        | Type   | Description                                                                                                 |
| :---------- | :----- | :---------------------------------------------------------------------------------------------------------- |
| IP          | string | IP address followed by port. e.g. "32.41.13.112:322"                                                        |
| Username    | string | Username used to log into Sofia. e.g. "adminUser"                                                           |
| Password    | string | Password used to log into Sofia. e.g. "adminPassword"                                                       |
| StaffIdList | string | Takes a comma delimited list, a single ItemId, or staff object. e.g. "234, 1234, 15" OR "1023", Or StaffObj |
| Message     | string | Message to be sent to asset(s). e.g. "Report to nearest checkpoint"                                         |

### Output:

| Name   | Type    | Description                       |
| :----- | :------ | :-------------------------------- |
| Status | boolean | True if message sent successfully |
