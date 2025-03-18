## Aufgabe 5:

## Part 1: Examine an ARP Request

### Step 1: Generate ARP Requests**

**a. Ist die Ziel-MAC-Adresse in der Tabelle oben aufgeführt?**

Ja, die MAC-Adresse des Ziels (172.16.31.3) 0060.7036.2849 ist in der Tabelle aufgeführt.

**b. Wie viele Kopien des PDU hat Switch1 erstellt?**

Es wurden 3 Kopien von Switch1 erstellt.

**c. Welche IP-Adresse hat das PDU akzeptiert?**

Die IP-Adresse 172.16.31.3, da sie der Ziel-IP-Adresse entspricht.

**d. Was passierte mit den Quell- und Ziel-MAC-Adressen?**

Die Quell-MAC-Adresse war die MAC-Adresse von 172.16.31.2 (000C.85CC.1DA7).
Die Ziel-MAC-Adresse wurde als Broadcast (FFFF.FFFF.FFFF) gesetzt, da die ARP-Anfrage an alle Geräte im Netzwerk gesendet wird.

**e. Wie viele Kopien des PDU hat der Switch während der ARP-Antwort erstellt?**

Da die ARP-Antwort ein Unicast-Paket ist, wird es nur an den anfragenden Host gesendet. Der Switch hat also eine einzige Kopie des PDUs weitergeleitet.

## Part 2: Examine a Switch MAC Address Table

### Step 1: Generate additional traffic to populate the switch MAC address table.

**Wie viele Antworten wurden gesendet und empfangen?**

Beim Ping von 172.16.31.2 - 172.16.31.4 und 10.10.10.2 - 10.10.10.3 werden vier ICMP-Antworten gesendet und empfangen.

### Step 2: Examine the MAC address table on the switches.

**a. Stimmen die Einträge in der MAC-Adressentabelle mit der Tabelle oben überein?**

Ja, die MAC-Adressen stimmen mit den Einträgen der Netzwerkgeräte überein.


**b. Warum sind zwei MAC-Adressen mit einem Port verbunden?**

Das geschieht normalerweise, wenn ein Switch an ein anderes Netzwerkgerät angeschlossen ist, das mehrere MAC-Adressen verwendet (z. B. ein weiterer Switch, ein Router oder ein Access Point).
In diesem Fall würde der Switch lernen, dass mehrere MAC-Adressen über denselben Port erreichbar sind.

## Part 3: Examine the ARP Process in Remote Communications

### Step 1: Generate traffic to produce ARP traffic.

**a. Was ist die IP-Adresse des neuen ARP-Tabelleneintrags?**

Nachdem ping 10.10.10.1 ausgeführt wurde und arp -a überprüft wird, ist ein neuer Eintrag mit der MAC-Adresse von 10.10.10.1 erschienen.

**b. Wie viele PDUs erscheinen nach arp -d und erneutem Ping?**

Zwei PDUs erscheinen

**c. Was ist die Ziel-IP-Adresse des ARP-Requests?**

Die Ziel-IP-Adresse des ARP-Requests ist die IP-Adresse des Standard-Gateways (Router) und nicht direkt 10.10.10.1.

**d. Warum ist die Ziel-IP-Adresse nicht 10.10.10.1?**

Das liegt daran, dass 172.16.31.2 und 10.10.10.1 sich in unterschiedlichen Netzwerken befinden.
Ein Host fragt per ARP nur nach MAC-Adressen im eigenen Subnetz.
Da 10.10.10.1 ausserhalb des Subnetzes 172.16.31.0 liegt, sendet der PC stattdessen einen ARP-Request an das Standard-Gateway (Router1), weil dieser für das Routing zuständig ist.

### Step 2: Examine the ARP table on Router1.

**a. Wie viele MAC-Adressen sind in der Tabelle? Warum?**

show mac-address-table auf Router1 zeigt wie viele adressen auf der Tabelle sind. Bei mir waren keine aufgelistet.der Router speichert nur MAC-Adressen für direkt verbundene Geräte.

**b. Gibt es einen Eintrag für 172.16.31.2 in der ARP-Tabelle (show arp)?**

Ja, da der Router eine ARP-Anfrage von 172.16.31.2 erhalten hat, speichert er dessen MAC-Adresse in der ARP-Tabelle.

**c. Was passiert beim ersten Ping, wenn der Router eine ARP-Anfrage beantworten muss?**

Der erste Ping schlägt oft fehl oder hat eine Verzögerung, weil der Router zuerst eine ARP-Anfrage senden muss, um die MAC-Adresse von 172.16.31.2 oder 10.10.10.1 zu lernen.
Sobald der Router die ARP-Antwort erhält, kann er den Ping weiterleiten.