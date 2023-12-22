_Last updated Dec. 21th 2023_

## Specifications for the Slayer Macro's WebSocket API

### Important:
- YOU MUST ENABLE CARRIER_MODE IN THE SLAYER MACRO CONFIG FOR THIS TO BE ACTIVE
- All messages are sent in JSON format, with a "type" property and a "data" property

## Server -> Client Messages
- type: `auth`
  - requires client to respond with `auth_response` message containing the auth key as `data` (string)
- type: `carrier_name`
  - data: `name` (string)
  - sent when the auth sequence is complete. provides the name of the carrier.
- type: `error`
  - data: `error` (string)
  - sent when an error occurs. provides the error message.

## Client -> Server Messages
- type: `auth_response`
  - data: `auth_key` (string)
  - sent in response to the `auth` message. provides the auth key.
- type: `set_username`
  - data: `name` (string)
  - sets the username of the client. this is sent AFTER the auth sequence is complete.
- type: `set_slayer`
  - data: {`slayer` (string), `slayerTier` (string)}
  - sets the slayer type of the client. this is sent AFTER the auth sequence is complete.


After all of the necessary data has been sent, the client can now party the carrier and should warp the carrier to the designated slayer location. The carrier will path to the slayer location and remain idle until the client's boss spawns, in which case it will attack and attempt to kill it. 
