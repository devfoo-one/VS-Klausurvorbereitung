*1. Erläutern Sie was ein* ***verteiltes*** *System ist! Was bedeutet hierbei die Eigenschaft der* ***Nebenläufigkeit*** *?*

Ein verteiltes System ist ein System aus Prozessen (welche nicht unbedingt auf dem selben Rechner ausgeführt werden müssen) welche mittels Nachrichten gemeinsam kommunizieren. Idealerweise verhält sich dieses System nach außen wie ein einzelnes System.

Nebenläufigkeit bedeutet hierbei "Scheinparallelität". Die Prozesse laufen nie gleichzeitig, suggerieren dies jedoch. Der Scheduler kümmert sich um die Verteilung der Prozesse auf die CPU. *[Script Seite 2, 76]*

---

*2. Erläutern Sie das klassische "Two-army problem"* ***und*** *dessen Bedeutung für verteilte Kommunikationssysteme hinsichtlich Zuverlässigkeit und Sicherheit einer Übertragungsstrecke!*

---

*3. Tragen Sie die Namen der fehlenden* ***drei*** *Layer (Deutsch oder Englisch) des OSI-Schichtenmodells in die folgende Grafik ein! Beschreiben Sie jeweils kurz die Bedeutung* ***dieser drei*** *Layer!*

Application Layer = In dieser Schicht laufen die Anwendungsprogramme

Transport Layer = Auf und Abbau von Verbindungen, Paketverlust kontrollieren, Aufteilen der Nachricht in kleinere Teile

Network Layer = Vermittlung der Nachricht über beliebig viele Zwischenstationen (Routing)

---

*4. Beschreiben Sie die **wesentlichen Eigenschaften und Unterschiede** von Threads und Prozessen! Was mach ein Thread im Zustand* ***"running"*** *und was im Zustand* ***"blocked"*** *?*

---

*5. Beschreiben Sie was passiert, wenn im Browser `http://google.de` eingegeben und die Enter-Taste gedrückt wird. Seien Sie so detailliert wie möglich! In der Erklärung sollten die Begriffe: Client, Server, Port, IP-Adrese, DNS, Socket, TCP, HTML und HTTP vorkommen*

---

*6. Nennen Sie* ***zwei*** *Technologien die von Web Services verwendet werden! Erläutern Sie kurz deren Aufgabe.*

---

*7. Erläutern Sie das Zustandekommen einer* ***Race Condition*** *zwischen mindestens zwei Softwareprozessen anhand eines selbst gewählten Beispiels. Nennen Sie* ***zwei*** *Beispiele für Synchronisationsmechanismen für nebenläufige Prozesse.*

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

---

*10. In vielen Protokollen und Verschlüsselungsalgorithmen werden kryptographisch sichere Zufallszahlen benötigt.*

-	*beschreiben Sie die besonderen Anforderungen, die an kryptographisch sichere Zufallszahlen gestellt werden!*
-	*für welche Zwecke werden kryptographisch sichere Zufallszahlen benötigt?*
-	*Welche Möglichkeiten zur Erzeugung kryptographisch sicherer Zufallszahlen gibt es? Was ist bei ihrem Einsatz zu beachten?*

---

*11. Für eine RSA-Verschlüsselung seien die Primzahlen* ***p = 19*** *und* ***q = 7*** *sowie* ***e = 7*** *gegeben.*

-	*Berechnen Sie* ***n, φ(n)***. *Ein Angreifer müsste* ***φ(n)*** *kennen um den zweiten Schlüssel* ***d*** *zu berechnen. Warum ist das für den Angreifer schwierig/unmöglich?*
-	*Wie groß ist der Wertebereich der vorliegenden RSA-Funktion?*
-	*Geben Sie die zurchzuführenden Berechnungen für eine Ver- und Entschlüsselung an, wenn* ***d=31*** *beträgt. (Symbolische Lösung ist ausreichend!)*
