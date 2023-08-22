# Modules

[Overview](README.md)

The great strength f Loco-CAN lies in its modularity. Specialised modules are available for different tasks, which only need to be connected to the four-pole bus cable.

## Universal
The universal module has the same structure on the CAN bus side as the standard modules. However, there are no special hardware drivers but the IOs are led out directly. The universal module and the universal WiFi module are pin-compatible.

A main field of application are controllers, which can be built up for example with the controller adapter.

In principle, it can be operated with any software, but the special hardware functions must then be implemented externally.


## Universal WiFi
The WiFi universal module has the same structure on the CAN bus side as the standard modules. In contrast to the universal module, it has a WiFi and Bluetooth interface for the wireless transmission of CAN messages. In addition, a web interface provides easy configuration of the entire system.

However, there are no special drivers but the IOs are directly led out. The universal module and the universal WiFi module are pin-compatible.

A main field of application are controllers, which can be built up for example with the controller adapter.

In principle, it can be operated with any software, but the special hardware functions must then be implemented externally.

## Control Adapter
The control adapter provides the most important connections for the control elements and display devices of a control desk. For the connection to the CAN bus, a universal or WiFi universal module can be plugged in.

## Motor
The motor module is used to control a power output stage via the CAN bus. The module can be connected to all common motor controls via different cables. A voltage measurement input checks the motor voltage to avoid destructive switching operations on bridge circuits. Another measurement input is used to monitor the voltage of the traction battery.

## Power
(Not yet developed)
The power module contains a battery that is charged via the CAN bus supply. The module can be used to power modules when no other power source is available, for example on a steam locomotive. In addition to the two CAN connectors, the power module has a connector for an external voltage source (e.g. charger).

## Switch
The switch or light module provides six switching outputs for resistive and inductive loads with a maximum load capacity of three amps. The assignment of the outputs can be assigned to any switching states in CAN messages with the configuration. The default setting provides control of lights on locomotive and train.

## Servo
The servo module offers the connection of up to six analog model servos. The assignment of the servo positions to CAN messages can be freely selected via the configuration. It is possible to convert analog values into angular positions, but switching states can also be assigned to certain positions of the servo. The positioning speed can be selected, for example to let a panthograph slowly go up and down.

## Sensor
In addition to four voltage measurement inputs and one pulse measurement input for rotational speed or velocity measurement, the sensor module also offers a current measurement up to 50 amps.

## Split
The split module is a simple distributor of the CAN bus line with three connections. In addition, an external supply can be plugged in via a supply connector. By means of a diode, different voltages can be introduced at different points. Only the highest voltage is then decisive.