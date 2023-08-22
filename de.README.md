# Das Projekt

[English](README.md)

<img
  src="Loco-CAN-Logo.png"
  alt="Loco-CAN"
  title="Loco-CAN - Ein Bis für die Bahn"
  style="float: left; margin-right: 10px; max-height: 150px">
  


Bei dem Projekt LOCO-CAN handelt es sich um ein elektronisches Steuerungssystem für die große Gartenbahn zur Personenbeförderung. Die Kommunikation zwischen den Geräten basiert auf dem CAN-Bus, der in der Automobilindustrie und in der Automatisierung eingesetzt wird. Die serielle Signalübertragung ist sehr robust und unterstützt mehrere Master und mehrere Slaves.

Das modulare System besteht aus verschiedenen Komponenten mit spezialisierten Aufgaben. So gibt es Module zum Bedienen, zum Steuern von Motorsteuerungen, Lichtschaltermodule oder Sensoren für Strom- und Spannungsmessung oder Drehzahlwerte. Aktuatoren, die von einem Servomodul angesprochen werden, können sogar zur Steuerung von Dieselmotoren oder Getrieben eingesetzt werden.

Durch die Flexibilität des CAN-Busses können zusätzliche Module einfach angeschlossen werden, ohne dass die bestehende Struktur verändert werden muss.

Das System ist nicht nur für die Vernetzung innerhalb eines Triebfahrzeugs gedacht, sondern kann auch über ein vierpoliges Kabel durch den Zug geführt werden. So können nicht nur Steuerpulte an jeder beliebigen Stelle im Zug angeschlossen werden, sondern beispielsweise auch Lichter in Waggons bedient werden.

Das System befindet sich noch in der Entwicklung. Die CAN-Spezifikation ist definiert, kann aber noch erweitert werden. Die Platinen sind in verschiedenen Versionen verfügbar, da sie sich in der Entwicklung befinden. Neben Fehlern im Board-Design unterscheiden sich Details wie die Pinbelegung der Programmschnittstelle zwischen den Versionen.

## Beispielaufbau

* [Beispiel PDF](Loco-CAN Zusammenstellung.pdf)

## [Module](de.modules.md)

## [Protokoll](de.protocol.md)
