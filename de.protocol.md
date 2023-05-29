# Das CAN-Protokoll

Die CAN-Nachrichten werden durch Identifier gekennzeichnet. Loco-CAN verwendet ein eigenes ID-System. Jedes Modul kann Nachrichten senden und sich auf die IDs registrieren, die für es interessant sind. Es gibt einige spezielle Nachrichten, die einen besonderen Einfluss auf die Gesamtfunktion haben. In erster Linie handelt es sich dabei um die Kommunikation zwischen Fahrregler und dem Motormodul.

Loco-CAN verwendet die erweiterten 29-Bit-Identifier. Der 11-Bit-Standard-Identifier enthält den Nachrichtentyp, 16 Bit des erweiterten Identifiers enthalten eine eindeutige Hardware-ID des Moduls. Diese uuid wird für die Einstellung der Modulparameter verwendet.

## Heartbeat
Heartbeat-Nachrichten werden verwendet, um die Präsenzen von Modulen zu identifizieren. Es gibt verschiedene Heartbeats:

* Modul-Heartbeat: Jedes Modul sendet eine Identifikationsnachricht, die Folgendes enthält
* Controller Heartbeat
## Heartbeat und die Priorität des Controllers
Es gibt keine Begrenzung der an den Bus angeschlossenen Steuerungen, aber es kann nur eine aktiv sein. Wenn der Hauptschalter eines Controllers auf "on" gestellt wird, prüft er, ob ein anderer Controller einen Heartbeat sendet. In diesem Fall wird ein Fehler angezeigt und der Regler bleibt inaktiv.
Um einen sicheren Betrieb zu gewährleisten, können einige Funktionen so konfiguriert werden, dass sie auf eine Heartbeat-Nachricht reagieren. Der Heartbeat wird von der aktiven Steuerung gesendet. Im System kann nur ein Regler für eine Lokomotive aktiviert werden. Ein fehlender Heartbeat führt zu einem Notstopp.

## Statusmeldungen
Eine Statusmeldung wird von jeder Lokomotive gesendet.

# Betriebsmeldungen

## Meldungen mit hoher Priorität

|Name|Value|
|----|-----|
|CAN_ID_CURRENT|0x100|
|CAN_ID_MOTOR_CURRENT|0x110|
|CAN_ID_BATT_CURRENT|0x120|
|CAN_ID_LIGHT_CURRENT|0x130|

## Nachrichten mittlerer Priorität

|Name|Value|
|----|-----|
|CAN_ID_SPEED|0x200|
|CAN_ID_DIR|0x210|
|CAN_ID_SIGNAL|0x220|
|CAN_ID_TACHO|0x230|

## Nachrichten mit niedriger Priorität

|Name|Value|
|----|-----|
|CAN_ID_VOLTAGE|0x300|
|CAN_ID_MOTOR_VOLTAGE|0x310|
|CAN_ID_BATT_VOLTAGE|0x320|
|CAN_ID_BATT_1_VOLTAGE|0x321|
|CAN_ID_BATT_2_VOLTAGE|0x322|

## Befehlsmeldungen

|Name|Value|
|----|-----|
|CAN_ID_DRIVE|0x400|
|CAN_ID_LIGHT|0x410|
|CAN_ID_SWITCH|0x420|

## Statusmeldungen

|Name|Value|
|----|-----|
|CAN_ID_STATUS|0x500|

## Heardbeat-Werte
Der Drive Heartbeat wird von der aktiven Steuerung gesendet und dient zur Überwachung der Verbindung zwischen Steuerung und Motormodulen. Die Zugende-Laternsignale werden beim Start der Fahrt in der Steuerung registriert. Eine Änderung in der Laternsignalliste während der Fahrt führt zu einem Nothalt (Abschalten des Heartbeat-Signals)

|Name|Value|
|----|-----|
|CAN_ID_DRIVE_HEARTBEAT|0x010|
|CAN_ID_TRAINEND_HEARTBEAT|0x020|

vom Zugende gesendet laterns

