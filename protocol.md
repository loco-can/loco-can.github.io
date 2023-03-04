# The CAN protocol

The CAN messages are identified by an identifier. Loco-CAN uses its own ID-system.

# Operation Messages
Message Mask
CAN_ID_MASK 0x770

## High priority messages
|Name|Value|
|----|-----|
|CAN_ID_CURRENT|0x100|
|CAN_ID_MOTOR_CURRENT|0x110|
|CAN_ID_BATT_CURRENT|0x120|
|CAN_ID_LIGHT_CURRENT|0x130|

## Mid priority messages
|Name|Value|
|----|-----|
|CAN_ID_SPEED|0x200|
|CAN_ID_DIR|0x210|
|CAN_ID_SIGNAL|0x220|
|CAN_ID_TACHO|0x230|

## Low priority messages
|Name|Value|
|----|-----|
|CAN_ID_VOLTAGE|0x300|
|CAN_ID_MOTOR_VOLTAGE|0x310|
|CAN_ID_BATT_VOLTAGE|0x320|
|CAN_ID_BATT_1_VOLTAGE|0x321|
|CAN_ID_BATT_2_VOLTAGE|0x322|

## Command messages
|Name|Value|
|----|-----|
|CAN_ID_DRIVE|0x400|
|CAN_ID_LIGHT|0x410|
|CAN_ID_SWITCH|0x420|

## Status messages
|Name|Value|
|----|-----|
|CAN_ID_STATUS|0x500|

## Heardbeat values
The heartbeat is sent from the active controller and used to monitor the connection between controller and motor modules. The train end latern signals are registered in the controller when starting to drive. A change in the latern signal list while driving leads to a emergency stop (switch off the heartbeat signal)

|Name|Value|
|----|-----|
|CAN_ID_HEARTBEAT|0x600|
|CAN_ID_TRAINEND|0x610|

sent from train end laterns

## Setup

The setup command is used to send and receive module setup data.
* 0x7FF request setup info from module (0 byte message length)
        the identifier uuid is ignored and the info is sent any way
* 0x7nn returns info packages (nn = data id)
        + 8 bytes text description
        adding the own uuid in the extended identifier
        so no other module can interpret it as a write command

* write commands are sent with the target uuid in the first two bytes
0x600   set module name

0x6nn   set data
        nn => data id + max 8 bytes of data

* message  bytes 0, 1 	=> UUID of module
           byte 2		=> message id
* 0xFF = module name
           bytes 3-7 	=> data

## Masks
* CAN_REQUEST_MASK 0x7FF
* CAN_ID_REQUEST 0x7FF

* CAN_REPLY_MASK 0x7FF
*  CAN_ID_REPLY 0x780

* CAN_SETUP_MASK 0x700
* CAN_ID_SETUP 0x700


* CAN_NAME_MAX_SIZE 5
* CAN_VALUE_MAX_SIZE 6

Footer
© 2023 GitHub, Inc
