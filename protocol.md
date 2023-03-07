# The CAN protocol

The CAN messages are identified by identifier. Loco-CAN uses its own ID-system. Every module can send messages and register to ids that are interesting. There are some spezial messages, that have a spezial impact on the overall function. Primary it is the communication between controllers and the motor module.

Loco-CAN uses the extended 29 bit identifiers. The 11 bit standard id contains the message type, 16 bits of the extended id holds an unique hardware id of the module. This uuid is used for the setup of module parameters.

## Heartbeat
Heartbeat messages are used to identify the presents of modules. There are different heartbeats:

* Module heartbeat: Each module sends an identification message contain
* Controller heartbeat
## Heartbeat and the Controller priority
There are no limitations of controllers connected to the bus, but only one can be active. When the main switch of a controller is set to on, it checks, if another controller is sending a heartbeat. In this case an error is displayed and the controller stays inactive.
To ensure a safe operation some functions can be configured to react on a heartbeat message. The heartbeat is sent from the active controller. In the system only one controller can be activated for a locomotive. A missing heartbeat leads to an emergency stop.

## Status Messages
A status message is sent by each locomotive.

# Operation Messages

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

|Name|Value|
|----|-----|
|CAN_ID_MASK|0x770|
|CAN_REQUEST_MASK|0x7FF|
|CAN_ID_REQUEST|0x7FF|
|CAN_REPLY_MASK|0x7FF|
|CAN_ID_REPLY|0x780|
|CAN_SETUP_MASK|0x700|
|CAN_ID_SETUP|0x700|

|Name|Value|
|----|-----|
|CAN_NAME_MAX_SIZE|5|
|CAN_VALUE_MAX_SIZE|6|
