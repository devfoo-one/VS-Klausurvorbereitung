*1. Erläutern Sie was ein* ***verteiltes*** *System ist! Was bedeutet hierbei die Eigenschaft der* ***Nebenläufigkeit*** *?*

Ein verteiltes System ist ein System aus Prozessen (welche nicht unbedingt auf dem selben Rechner ausgeführt werden müssen) welche mittels Nachrichten gemeinsam kommunizieren. Idealerweise verhält sich dieses System nach außen wie ein einzelnes System.

Nebenläufigkeit bedeutet hierbei "Scheinparallelität". Die Prozesse laufen nie gleichzeitig, suggerieren dies jedoch. Der Scheduler kümmert sich um die Verteilung der Prozesse auf die CPU. *[Script Seite 2, 76]*

---

*2. Erläutern Sie das klassische "Two-army problem"* ***und*** *dessen Bedeutung für verteilte Kommunikationssysteme hinsichtlich Zuverlässigkeit und Sicherheit einer Übertragungsstrecke!*

Zwei Armeen wollen über feindliches Gebiet hinweg kommunizieren. Wenn B1 B2 eine Nachricht sendet möchte B1 sicherstellen:

-	das B2 diese erhalten hat
-	B1 und B2 müssen feststellen können ob W die Nachricht manipuliert hat
-	dass der Feind diese nicht manipuliert hat
-	das der Feind deren Inhalt nicht erhalten hat

Das gleiche gilt für jede Übertragung. Man muss sicherstellen dass eine Nachricht genauso beim Sender ankommt wie sie gesendet wurde (z.B. Prüfsumme). Man benötigt eine Bestätigung über korrekten Empfang (Zuverlässigkeit) und die Nachricht darf nicht manipuliert worden sein. *[Script Seite 192 fff]*

---

*3. Tragen Sie die Namen der fehlenden* ***drei*** *Layer (Deutsch oder Englisch) des OSI-Schichtenmodells in die folgende Grafik ein! Beschreiben Sie jeweils kurz die Bedeutung* ***dieser drei*** *Layer!*

Application Layer = In dieser Schicht laufen die Anwendungsprogramme

Transport Layer = Auf und Abbau von Verbindungen, Paketverlust kontrollieren, Aufteilen der Nachricht in kleinere Teile

Network Layer = Vermittlung der Nachricht über beliebig viele Zwischenstationen (Routing)

*[Script Seite 35-43]*

---

*4. Beschreiben Sie die **wesentlichen Eigenschaften und Unterschiede** von Threads und Prozessen! Was macht ein Thread im Zustand* ***"running"*** *und was im Zustand* ***"blocked"*** *?*

Prozess = in Ausführung befindliches Programm, bestehend aus *[Script Seite 87]*

-	einer Folge von Maschinenbefehlen
-	Inhalt des Stacks
-	haben einen eigenen Speicherbereich (durch Betriebssystem zugewiesen)
-	Verwaltungsinformationen die den Bearbeitungszustand beschreiben
-	Kommunikation zwischen Prozessen erfolgt nur über Nachrichten

Thread = *[Script Seite 98]*

-	eine Ausführungseinheit eines Prozesses mit minimalen Zustandsinformationen
-	gehören alle zu einem bestimmten Prozess und arbeiten deshalb auf den selben Daten

Jeder Prozess hat seinen eigenen Speicherbereich (Dies wird vom Betriebssystem überwacht) und können untereinander nur über Nachrichten kommunizieren. Prozesse bestehen aus Threads. Threads hingegen werden von bestimmten Prozessen gestartet und teilen sich einen Speicherbereich und arbeiten gemeinsam auf diesem.

-	running = Thread läuft aktiv auf einem Prozessor
-	blocked = Thread wartet auf ein Ereignis z.B. auf Eingabe

running und blocked werden vom Scheduler gesetzt.

---

*5. Beschreiben Sie was passiert, wenn im Browser `http://google.de` eingegeben und die Enter-Taste gedrückt wird. Seien Sie so detailliert wie möglich! In der Erklärung sollten die Begriffe: Client, Server, Port, IP-Adrese, DNS, Socket, TCP, HTML und HTTP vorkommen*

-	IP Adresse zu `google.de` ermitteln
	-	DNS Auflösung (OS Resolver anfragen)
	-	Wenn IP nicht im lokalen Cache dann DNS Server anfragen
	-	bekannter DNS Server (bei DSL Verbindungen vom Provider konfiguriert) wird angefragt
-	Client öffnet Socket zur zurückgelieferten IP-Adresse.
	-	Lokaler Port wird vom OS ausgewählt
	-	remote Port ist bei Browsern, sofern nicht näher in Adresse angegeben, Port 80
-	Über diesen Socket wird nun eine TCP Verbindung aufgebaut
	-	TCP 3 Way Handshake
-	Über TCP Verbindung wird nun ein HTTP GET Request gesendet
-	Es erfolgt eine HTTP Response mit Code 200 (google sollte OK zurückliefern)
-	in HTTP Response sind nun die anzuzeigenden HTML Daten
	-	Sofern weitere Dokumente wie Bilder eingebunden -> neue TCP Verbindung zu jeder Bildquelle
-	Browser rendert Daten und zeigt diese an

---

*6. Nennen Sie* ***zwei*** *Technologien die von Web Services verwendet werden! Erläutern Sie kurz deren Aufgabe.*

-	JSON = Datenaustausche zwischen Web-Services bzw. zwischen Server (HTTP Server) und Client (JavaScript auf Seite)
-	AJAX = Asynchroner HTTP Request, Seite muss im Browser nicht neu geladen werden sondern bezieht sich Daten aus XML oder JSON Datenquelle
-	XML = Datenaustauschformat, viel Overhead
-	SOAP = XML basiertes Protokoll zum Datenaustausch und Remote Procedure Call

---

*7. Erläutern Sie das Zustandekommen einer* ***Race Condition*** *zwischen mindestens zwei Softwareprozessen anhand eines selbst gewählten Beispiels. Nennen Sie* ***zwei*** *Beispiele für Synchronisationsmechanismen für nebenläufige Prozesse.*

"Ist das Ergebnis einer Ausführung nebenläufiger Prozesse abhängig von der zeitlichen Reihenfolge der Ausführung dieser Prozesse, so beschreibt diese Situation einen kritischen Wettlauf" *[Script Seite 141 - 143]*

---

*8. Tragen Sie die Begriffe* ***Anwendung, Dienst, Middleware*** *(mehrfache Benennungen möglich) und den Begriff* ***Netzwerk*** *korrekt in das folgende Beispiel einer verteilten Middleware-Lösung ein! Beschreiben Sie kurz **welche** Rolle die Middleware hier hat!*

---

*9. Nach dem Aufruf einer URL erhalten Sie folgende Ausgabe im Browser:*

```javascript
{
    "Vorname": "Hans",
    "Nachname": "Peters",
    "Alter": 49,
}
```

*um welches Datenformat handelt es sich? Wie kann diese Ausgabe interpretiert werden?*

JSON Format. JavaScript Objekte (Key/Value Paare). URL enthielt warscheinlich Anfrage zu einer bestimmten Person.

---

*10. In vielen Protokollen und Verschlüsselungsalgorithmen werden kryptographisch sichere Zufallszahlen benötigt.*

-	*beschreiben Sie die besonderen Anforderungen, die an kryptographisch sichere Zufallszahlen gestellt werden!*
-	*für welche Zwecke werden kryptographisch sichere Zufallszahlen benötigt?*
-	*Welche Möglichkeiten zur Erzeugung kryptographisch sicherer Zufallszahlen gibt es? Was ist bei ihrem Einsatz zu beachten?*

*[Crypto ab Seite 79]*

-	Anforderungen
	-	nicht verhersagbar
	-	"wirklich" zufällig
	-	müssen statistische Eigenschaften erfüllen *siehe [Crypto Seite 80]*
-	Zweck
	-	Initialisierungsvektoren von Verschlüsselungsalgorithmen
	-	zufällige Wahl von Master-Schlüsseln
	-	Erzeugung eines kontinuierlichem Schlüsselstroms für Stromchiffren
-	Erzeugung *[Crypto Seite 82]*
	-	spezielle Hardware
	-	Verwendung von "zufälligen" physikalischen Eingangsgrößen
		-	Tastatureingaben des Nutzers
		-	Festplattenaktivität

---

*11. Für eine RSA-Verschlüsselung seien die Primzahlen* ***p = 19*** *und* ***q = 7*** *sowie* ***e = 7*** *gegeben.*

-	*Berechnen Sie* ***n, φ(n)***. *Ein Angreifer müsste* ***φ(n)*** *kennen um den zweiten Schlüssel* ***d*** *zu berechnen. Warum ist das für den Angreifer schwierig/unmöglich?*
-	*Wie groß ist der Wertebereich der vorliegenden RSA-Funktion?*
-	*Geben Sie die zurchzuführenden Berechnungen für eine Ver- und Entschlüsselung an, wenn* ***d=31*** *beträgt. (Symbolische Lösung ist ausreichend!)*

*[Crypto ab Seite 72]*

Wertebereich = `M,S e {0,1,2, ... ,n-1} = n-1` *[Crypto Seite 74]*
