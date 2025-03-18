## Aufgabe 04:


| Feld              | Wert             |
|-------------------|------------------|
| Destination MAC  | 000C:85CC:1DA7   |
| Source MAC       | 00D0:D311:C788   |
| Source IP        | 172.16.31.5      |
| Destination IP   | 172.16.31.2      |



| At Device     | Dest. MAC       | Src MAC        | Src IPv4     | Dest IPv4    |
|--------------|----------------|---------------|-------------|-------------|
| 172.16.31.5  | 000C:85CC:1DA7  | 00D0:D311:C788 | 172.16.31.5 | 172.16.31.2 |
| Switch1      | 000C:85CC:1DA7  | 00D0:D311:C788 | 172.16.31.5 | 172.16.31.2 |
| Hub          | N/A             | N/A            | 172.16.31.5 | 172.16.31.2 |
| 172.16.31.2  | 00D0:D311:C788  | 000C:85CC:1DA7 | 172.16.31.2 | 172.16.31.5 |
| Router       | 000C:85CC:1DA7  | 00D0:D311:C788 | 172.16.31.5 | 172.16.31.2 |

**Step 2**

| At Device     | Dest. MAC       | Src MAC        | Src IPv4     | Dest IPv4    |
|--------------|----------------|---------------|-------------|-------------|
| 172.16.31.3  | 000C:85CC:1DA7  | 0060:7036:2849 | 172.16.31.2 | 172.16.31.3 |
| Switch1      | 000C:85CC:1DA7  | 0060:7036:2849 | 172.16.31.2 | 172.16.31.3 |
| Hub          | N/A             | N/A            | 172.16.31.2 | 172.16.31.3 |
| 172.16.31.2  | 0060:7036:2849  | 000C:85CC:1DA7 | 172.16.31.3 | 172.16.31.2 |

| At Device     | Dest. MAC       | Src MAC        | Src IPv4     | Dest IPv4    |
|--------------|----------------|---------------|-------------|-------------|
| 172.16.31.4  | 00D0:D311:C788  | 000C:CF0B:BC80 | 172.16.31.4 | 172.16.31.5 |
| Switch1      | 000C:CF0B:BC80  | 00D0:D311:C788 | 172.16.31.4 | 172.16.31.5 |
| Hub          | N/A             | N/A            | 172.16.31.4 | 172.16.31.5 |
| 172.16.31.5  | 000C:CF0B:BC80  | 00D0:D311:C788 | 172.16.31.4 | 172.16.31.5 |

### Part 2:

| At Device     | Dest. MAC        | Src MAC          | Src IPv4   | Dest IPv4  |
|-------------------|---------------------|----------------------|---------------|---------------|
| 172.16.31.5  | 00D0:BA8E:741A       | 00D0:D311:C788       | 172.16.31.5   | 10.10.10.2    |
| Switch1      | 00D0:BA8E:741A       | 00D0:D311:C788       | N/A           | N/A           |
| Router       | 0060:2F84:4AB6       | 00D0:588C:2401       | 172.16.31.5   | 10.10.10.2    |
| Switch0      | 0060:2F84:4AB6       | 00D0:588C:2401       | N/A           | N/A           |
| Access Point | N/A                  | N/A                  | N/A           | N/A           |
| 10.10.10.2   | 00D0:588C:2401       | 0060:2F84:4AB6       | 10.10.10.2    | 172.16.31.5   |

## Fragen:

---

**Wurden verschiedene Arten von Kabeln oder Medien verwendet, um Geräte zu verbinden?**  
✅ Ja, in Netzwerksimulationen können verschiedene Kabeltypen (z. B. Kupferkabel, Glasfaserkabel, drahtlose Verbindungen) verwendet werden. Die Wahl hängt von den verbundenen Geräten und den Netzwerkanforderungen ab.  

**Hat die Art des Kabels die Handhabung der PDU beeinflusst?**  
✅ Nein, die Art des Kabels oder Übertragungsmediums beeinflusst nicht die Verarbeitung der PDU selbst. Sie kann jedoch die Übertragungsgeschwindigkeit und Reichweite verändern.  

**Hat der Hub Informationen verloren, die er erhalten hat?**  
✅ Nein, ein Hub speichert keine Daten, sondern leitet alle empfangenen Pakete an alle angeschlossenen Ports weiter.  

**Wie geht ein Hub mit MAC- und IP-Adressen um?**  
✅ Ein Hub arbeitet auf OSI-Schicht 1 (physikalische Schicht) und verarbeitet keine MAC- oder IP-Adressen. Er verstärkt lediglich Signale und leitet sie an alle Geräte weiter.  

**Hat der drahtlose Access Point die übertragenen Daten verändert?**  
✅ Nein, ein Access Point überträgt Daten zwischen kabelgebundenen und drahtlosen Geräten. Er kann MAC-Adressen für den Netzwerkzugang verwenden, verändert aber den Inhalt der PDUs nicht.  

**Wurde während der drahtlosen Übertragung eine MAC- oder IP-Adresse verloren?**  
✅ Nein, MAC- und IP-Adressen gehen während der Übertragung nicht verloren. Sie sind essenziell für die korrekte Zustellung der Pakete.  

**Welche OSI-Schicht nutzen der Hub und der Access Point?**  
✅ Der Hub arbeitet auf Schicht 1 (physikalische Schicht). Der Access Point kann auf Schicht 2 (Sicherungsschicht) arbeiten, da er MAC-Adressen zur Steuerung des Netzwerkzugangs nutzt.  

**Hat der Hub oder Access Point jemals eine PDU weitergeleitet, die mit einem roten "X" abgelehnt wurde?**  
✅ Ja, Hubs und Access Points leiten alle eingehenden PDUs weiter, unabhängig davon, ob die Übertragung erfolgreich oder fehlerhaft ist.  

**Beim Betrachten des PDU-Detailreiters: Welche MAC-Adresse erscheint zuerst, die Quelle oder das Ziel?**  
✅ Die Quell-MAC-Adresse erscheint zuerst, gefolgt von der Ziel-MAC-Adresse.  

**Warum ist diese Reihenfolge so?**  
✅ Ethernet-Rahmen sind so aufgebaut, dass zuerst die Quelladresse und dann die Zieladresse steht, damit Empfänger und Sender korrekt identifiziert werden können.  

**Gab es ein Muster in der MAC-Adressierung?**  
✅ Ja, MAC-Adressen folgen einem standardisierten Format. Die ersten drei Bytes geben den Hersteller des Geräts an, während die restlichen Bytes eine eindeutige Gerätekennung enthalten.  

**Haben Switches eine PDU repliziert, die mit einem roten „X“ abgelehnt wurde?**  
✅ Nein, Switches leiten Pakete basierend auf MAC-Adresstabellen weiter. Wenn eine PDU nicht zugestellt werden kann, liegt dies meist an einem Konfigurationsproblem im Netzwerk.  

**Wann wechselten die MAC-Adressen zwischen dem 10er-Netzwerk und dem 172er-Netzwerk?**  
✅ Der Wechsel fand am Router statt, da dieser als Gateway zwischen den Netzwerken fungiert und die Quell- oder Ziel-MAC-Adresse entsprechend anpasst.  

**Welches Gerät verwendet MAC-Adressen, die mit 00D0:BA beginnen?**  
✅ Diese MAC-Adresse gehört wahrscheinlich zu einem bestimmten Hersteller. Um dies zu überprüfen, könnte eine MAC-Adressdatenbank genutzt werden.  

**Zu welchen Geräten gehörten die anderen MAC-Adressen?**  
✅ Um dies herauszufinden, müsste man die MAC-Adressen mit einer Herstellerdatenbank abgleichen.  

**Haben sich die sendenden und empfangenden IPv4-Adressen in irgendeiner PDU geändert?**  
✅ Innerhalb eines Netzwerks bleiben IPv4-Adressen konstant. Beim Routing zwischen Netzwerken können sie sich jedoch ändern, insbesondere wenn NAT (Network Address Translation) verwendet wird.  

**Wechseln die sendenden und empfangenden IPv4-Adressen beim Ping-Antwortprozess?**  
✅ Ja, bei der Antwort (Pong) tauschen die Quell- und Ziel-IPv4-Adressen ihre Position, da das Ziel die Antwort an den ursprünglichen Sender zurückschickt.  

**Welches IPv4-Adressierungsmuster wurde in dieser Simulation verwendet?**  
✅ Das Muster folgt den reservierten privaten IPv4-Adressbereichen für interne Netzwerke.  

**Warum benötigen verschiedene IP-Netzwerke unterschiedliche Router-Ports?**  
✅ Router verbinden verschiedene Netzwerke und nutzen separate Ports für jedes Netzwerk, um den Datenverkehr korrekt zu leiten und zu verwalten.  

**Was wäre anders, wenn die Simulation mit IPv6 anstelle von IPv4 konfiguriert wäre?**  
✅ IPv6 nutzt längere Adressen, bietet eine bessere Routing-Effizienz, verbesserte Sicherheitsfunktionen und eliminiert die Notwendigkeit von NAT aufgrund des grösseren Adressraums.  