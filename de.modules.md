# Module

[Übersicht](de.README.md)

Die große Stärke von Loco-CAN liegt in seiner Modularität. Für unterschiedliche Aufgaben stehen spezialisierte Module zur Verfügung, die nur noch an das vierpolige Buskabel angeschlossen werden müssen.

## Universal
Das Universalmodul hat auf der CAN-Bus-Seite den gleichen Aufbau wie die Standardmodule. Allerdings gibt es keine speziellen Hardwaretreiber sondern die IOs werden direkt herausgeführt. Das Universalmodul und das Universal-WLAN-Modul sind Pin-kompatibel.

Ein Hauptanwendungsgebiet sind Controller, die beispielsweise mit dem Controller-Adapter aufgebaut werden können.

Der Betrieb ist prinzipiell mit jeder Software möglich, allerdings müssen die speziellen Hardwarefunktionen dann extern implementiert werden.

## Universal WiFi
Das WiFi-Universalmodul hat auf der CAN-Bus-Seite den gleichen Aufbau wie die Standardmodule. Im Gegensatz zum Universalmodul verfügt es über eine WiFi- und Bluetooth-Schnittstelle zur drahtlosen Übertragung von CAN-Nachrichten. Darüber hinaus ermöglicht eine Weboberfläche die einfache Konfiguration des gesamten Systems.

Allerdings gibt es keine speziellen Treiber sondern die IOs werden direkt herausgeführt. Das Universalmodul und das Universal-WLAN-Modul sind Pin-kompatibel.

Ein Hauptanwendungsgebiet sind Controller, die beispielsweise mit dem Controller-Adapter aufgebaut werden können.

Der Betrieb ist prinzipiell mit jeder Software möglich, allerdings müssen die speziellen Hardwarefunktionen dann extern implementiert werden.

## Steueradapter
Der Steueradapter stellt die wichtigsten Anschlüsse für die Bedienelemente und Anzeigegeräte eines Steuerpultes bereit. Für den Anschluss an den CAN-Bus kann ein Universal- oder WiFi-Universalmodul eingesteckt werden.

## Motor
Das Motormodul dient zur Ansteuerung einer Leistungsendstufe über den CAN-Bus. Das Modul kann über verschiedene Kabel an alle gängigen Motorsteuerungen angeschlossen werden. Ein Spannungsmesseingang prüft die Motorspannung, um zerstörerische Schaltvorgänge an Brückenschaltungen zu vermeiden. Ein weiterer Messeingang dient zur Überwachung der Spannung der Traktionsbatterie.

## Power
(Noch nicht entwickelt)
Das Powermodul enthält eine Batterie, die über die CAN-Bus-Versorgung geladen wird. Das Modul kann zur Stromversorgung von Modulen verwendet werden, wenn keine andere Stromquelle verfügbar ist, beispielsweise bei einer Dampflokomotive. Zusätzlich zu den beiden CAN-Anschlüssen verfügt das Powermodul über einen Anschluss für eine externe Spannungsquelle (z. B. Ladegerät).

## Schalter
Das Schalt- bzw. Lichtmodul stellt sechs Schaltausgänge für ohmsche und induktive Lasten mit einer maximalen Belastbarkeit von drei Ampere zur Verfügung. Die Belegung der Ausgänge kann mit der Konfiguration beliebigen Schaltzuständen in CAN-Nachrichten zugeordnet werden. Die Standardeinstellung ermöglicht die Steuerung der Lichter an Lokomotive und Zug.

## Servo
Das Servomodul bietet den Anschluss von bis zu sechs analogen Modellservos. Die Zuordnung der Servopositionen zu CAN-Nachrichten ist über die Konfiguration frei wählbar. Es ist möglich, analoge Werte in Winkelpositionen umzuwandeln, aber auch Schaltzustände können bestimmten Positionen des Servos zugeordnet werden. Die Positioniergeschwindigkeit ist wählbar, um beispielsweise einen Panthographen langsam auf und ab fahren zu lassen.

## Sensor
Das Sensormodul bietet neben vier Spannungsmesseingängen und einem Impulsmesseingang zur Drehzahl- oder Geschwindigkeitsmessung auch eine Strommessung bis 50 Ampere.

## Split
Das Split-Modul ist ein einfacher Verteiler der CAN-Bus-Leitung mit drei Anschlüssen. Darüber hinaus kann über einen Versorgungsstecker eine externe Versorgung angeschlossen werden. Mittels einer Diode können an verschiedenen Stellen unterschiedliche Spannungen eingebracht werden. Ausschlaggebend ist dann nur die höchste Spannung.