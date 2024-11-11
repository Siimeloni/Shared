## 1. Allgemeines

- ***Verteilte Software***

·       eine **Sammlung von Prozessen oder Diensten**, die unabhängig voneinander ausgeführt                   werden und über Kommunikationsmechanismen koordiniert werden, unabhängig davon, ob           sie auf einem oder mehreren Computern laufen.
·       Prozesse (Dienste) erbringen gemeinsam die Leistung zur **Lösung einer Aufgabe**
·       Zum Austausch von Informationen müssen Prozesse **über Netzwerke miteinander                          interagieren**
·       Verteilung von Daten und Ausführung der Daten

- ***Vorteile:***

·       Effiziente Nutzung von Ressourcen
·       Betriebswirtschaftliche Gründe
·       Zugriff auf entfernte Daten möglich
·       Robust durch redundante Datenkopien

- ***Nachteile: erhöhte Komplexität in allen SWE-Phasen***

·       **Entwurf:** Modell muss Kommunikationsmechanismen beachten
·       **Implementierung:** durch Kommunikation zusätzliche Fehlerfälle und Sicherheitsmaßnahmen
·       **Test:** Entfernte Partner müssen simuliert werden
·       **Betrieb:** Ausfälle einzelner Rechner können zu Gesamtausfällen führen
·       **Versionierung und Konfiguration:** muss konform gehen, um Austausch von Teilen zu                       ermöglichen

- ***Architektur (Struktur des Gesamtsystems):***

·       **Klassische Architekturen:** Client-Server, Peer-to-Peer
·       **Statisch festgelegte oder dynamische:** im Rahmen einer konkreten Kommunikation                        Teilnehmer können unterschiedliche Rollen annehmen

|     | ![](file:///C:/Users/SELINA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png) |
| --- | ----------------------------------------------------------------------------------- |


·       **Multi-Tier-Architektur (n-Tier):** erweitert das Client-Server-Modell um zusätzliche Schichten zwischen dem Client und dem Server, wie z.B. Präsentationsschicht (Frontend), Logikschicht (Middle Tier, in der die Geschäftslogik verarbeitet wird) bzw. Datenzugriffsschicht (Backend), Beispiel: eine typische Webanwendung

·       **Microservices-Architektur:** teilt Anwendungen in kleinere, voneinander unabhängige Dienste auf, die miteinander über APIs interagieren. Dienste haben eine spezifische Aufgabe und können unabhängig entwickelt, getestet und bereitgestellt werden, laufen oft in Containern oder virtuellen Maschinen und kommunizieren über ein Netzwerk. Beispiele: Webanwendungen, mobile Anwendungen, Desktop-Anwendungen mit komplexer Geschäftslogik, Embedded Systems und IoT, Spiele

·       **Event-Driven Architektur**: realisiert das Interagieren von Komponenten durch das Austauschen von Ereignissen. Dienste reagieren auf Ereignisse und führen daraufhin Aktionen aus. Beispiele: IoT, medizinische Überwachung, Social Media, Finanz- und E-Commerce Plattformen

·       **Publish-Subscribe (Pub-Sub):** Komponenten agieren entweder als Publisher (die Nachrichten senden) oder als Subscriber (die Nachrichten empfangen), das Interagieren läuft über einen Vermittler (Message Broker).

·       **Serverless Computing:** sieht vor, dass der Entwickler den Code schreibt, ohne sich um die zugrundeliegende Infrastruktur kümmern zu müssen. Die Ausführung wird von einem Cloud-Anbieter übernommen, der die Skalierung, Wartung und Verteilung verwaltet.

·       **Grid Computing:** nutzt eine Vielzahl von losegekoppelten Computern (meist über verschiedene Standorte verteilt), um große Mengen an Rechenleistung zu bündeln und komplexe (meistens spezielle) Aufgaben zu lösen. Beispiel: wissenschaftliche Berechnungen wie SETI@home-Projekt (Suche nach außerirdischer Intelligenz zu Hause, 2004-2020)

- ***Interaktion und Interaktionsmuster:***

![](file:///C:/Users/SELINA~1/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

- ***Kommunikationsparadigmen***

·       **Nachichtenbasierte Kommunikation:** über Dienstprimitiven: send and recieve, verbindungsorientiert, paketorientiert, Sockets, Jakarta Messaging (Java Message Service)

·     **Fernaufruf:** Aufruf von Funktionen (Prozeduren) im anderen Adressraum (Remote Procedure Call – RPC) – nach Ausführung der Funktionen wird Ergebnis in ehemaligen Adressraum geliefert

- ***Eigenschaften einer Verteilten Anwendung:***
	- Heterogenität: Anwendung ist eine Gesamtheit, die aus nicht gleichartigen Elementen besteht

		·    Einheitliches Programmiermodell, zur Entwicklung verteilter Software (Prozedurenaufruf – RPC, Objektfernaufruf – RIM)
		·    Grundlegende Bausteine einer Anwendung: Prozesse (Threads) und Nachichtenaustausch
		·    Hardwareunabhängiger übertragbarer Maschienencode inkl. Interpreter, Zwischencode und virtuelle Maschiene

	-      Nebenläufigkeit: Die Fähigkeit einer Anwendung mehrere Aufgaben gleichzeitig ausführen zu können (nebenläufige Server, nebenläufige Clienten)

		·  Fähigkeit zur Fehlerbehandlung: Die Fähigkeit Fehler zu erkennen und darauf               zu reagieren (Fehler können erkennbar – z.B. durch Prüfsummen – und nicht                erkennbar sein – z.B. Server-Ausfall)
		·    Fehler verbergen (maskieren): z.B. verlorene Nachrichten wiederholen,                     Dateien auf mehrere Datenträger sichern oder abschwächen (z.B. fehlerhafte                Nachrichten verwerfen)
		·    Fehler tolerieren: einige Fehler können hingenommen werden und ggf. dem                    Anwender gemeldet werden

	-       Sicherheit: Informationen sicher über ein Netzwerk zu übertragen

		·    Integrität: Schutz vor Beschädigung oder generell Veränderung der                         Informationen
		·    Verfügbarkeit: Vermeidung der Störungen während des Betriebs
		·    Vertraulichkeit: Informationen (Inhalte inkl. Absenderidentität) vor                      Unbefugten schützen (Verschlüsselung)

	-        Verteilungstransparenz: Ziel jeder Anwendung, Transparenz = Verteilung ist für Nutzer nicht sichtbar

		·    Zugriffstransparenz: wie die Daten, in welchem Format gespeichert sind
		·    Ortstransparenz: wo die Ressourcen sich befinden
		·    Migrationstransparenz: pre-Session Mobilität
		·    Relokationstransparenz: mid-Session Mobilität
		·    Persistenztransparenz: flüchtige oder persistente Speicherung
		·    Nebenläufigkeitstransparenz: mehrere Prozesse
		·    Replikationstransparenz: mehrere Kopien
		·    Fehlertransparenz: Verbergen von Ausfällen von Teilsystemen

	-       Skalierbarkeit: skalierbar heißt kann wachsen ohne Veränderung der Eigenschaften

		·    Größe: Möglichkeit des Hinzufügens von Komponenten
		·    Geographische Verteilung: System funktioniert unabhängig von der Entfernung
		·    Administrative Verteilung: System funktioniert über die Grenzen der                       administrativen Domäne hinweg (verschiedene Sicherheitsrichtlinien)
		
-     ***Anforderung an Programmiersprache bzw. Technologie:***

·    Netzfähigkeit: Netzwerk-Socket-Programmierung (TCP, UDP) bzw. Techniken auf               höherer Abstraktionsebene (Remote Method Invocation (RMI), WebSockets…)

·    Protokollunterstützung: für Protokolle wie HTTP, FTP, SMTP und WebSockets

·       Nebenläufigkeit und Parallelität:
	·    Thread-Management: Threads oder andere Formen der Nebenläufigkeit wie Coroutines, Promises, async/await bieten
	·    Asynchrone Programmierung: die Fähigkeit blockierende Netzwerkaufrufe zu vermeiden

·       Interoperabilität: Fähigkeit, Daten sicher und automatisch auszutauschen. D.h. die Sprachen sollen Mechanismen zur Kommunikation mit anderen Sprachen bieten.
	·    Serialisierung und Deserialisierung: eingebaute Unterstützung für Formate wie JSON, XML etc., um Daten zwischen verschiedenen Komponenten zu übertragen und zu interpretieren

·       Plattformunabhängigkeit: Mechanismen um Code Plattformunabhängig auszuführen (z.B. durch Bytecode oder virtuelle Maschienen wie die JVM)

·       Sicherheit: Bibliotheken zur Verschlüsselung und Entschlüsselung von Daten (z.B. SSL/TLS) sowie zur Implementierung von Zugriffskontrolle bereitstellen.
	·    Zugriffskontrolle: Mechanismen zur sicheren Authentifizierung (Überprüfung der Identität) und Autorisierung (Berechtigungen)

·       Fehlertoleranz und Wiederherstellung: einschließlich die Fähigkeit, Netzwerkausfälle, Übertragungsfehler oder den Ausfall von Knoten zu erkennen und umzugehen.

·       Modularität: Fähigkeit große Anwendungen zu unterteilen und wiederverwendbare Komponenten zu entwickeln

·       Skalierbarkeit: Werkzeuge oder Frameworks, die die Skalierung von Anwendungen über mehrere Knoten hinweg ermöglichen, z.B. durch Unterstützung für Cloud-Computing-Plattformen oder Containerisierung (wie z.B. Docker)

·       Umfangreiche Bibliotheken: eine Vielzahl von Bibliotheken oder Frameworks für häufige Aufgaben in verteilten Systemen (für Netzwerke, asynchrone Operationen, Protokollverarbeitung usw.)