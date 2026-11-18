# Dokumentation der Übernahme und Überarbeitung des Smart-Campus-Projekts

**Robotikkurs, FH Wiener Neustadt**

Das Team hat sich dazu entschieden, das Projekt Smart Campus nicht nur zu erweitern und zu verbessern, sondern es von Grund auf neu zu entwickeln. Diese Dokumentation dient als Richtlinie und Schritt für Schritt Plan für dieses Vorhaben.
<br>
<br>

**Das Team:**
| Vorname | Nachname |
|---|---|
| Simon | Resetarits |
| Eliah | Posch |
| Raphael | Zangl-Gottwald |
| Laurenz | Rauscher |
| Thomas | Haiden |


## 1. Kommunikation und Dokumentation

- Der Hub des Projekts ist die GitHub-Organisation [**Robotikkurs**](https://github.com/Robotik-Club) mit ihren Repositorys. Dort wird alles kategorisiert und abgelegt.
- OneDrive wird nicht mehr verwendet und durch GitHub ersetzt.
- Alle zugehörigen Repositorys des Projekts werden mit dem Präfix **SC-** benannt, um sie zu kennzeichnen und leicht zu erkennen.
- Zusätzlich werden Tags (Topics) vergeben, damit die Repositorys gefiltert werden können.
- Die WhatsApp-Gruppe bleibt für die schnelle Kommunikation im Team bestehen.

## 2. Zielsetzung

Das Hauptziel ist die Fertigstellung und den praktischen Einsatz des Systems an der FH Wiener Neustadt. Dafür gilt:

- Der Code wird komplett neu geschrieben --> nicht wie bisher in C, sondern umgeschieben in **C++**.
- Es wird eine neue, eigene **API** entwickelt, die für die Kommunikation zwischen den Sensoren und der Datenbank dient.
- Alle Daten werden in einer **Datenbank** gespeichert, damit auch ältere Daten abrufbar sind.
- Die **Webpage** wird neu gestaltet --> moderner, schneller und benutzerfreundlicher.

## 3. Plan zur Umsetzung

1. **Sensorlogik:** Es wird eine neue Sensorlogik in C++ programmiert. Vorerst für jeden Sensor einzeln, erst im späteren Verlauf des Projekts wird der Code zusammengeführt.
2. **Datenbank:** Es wird eine Datenbank erstellt, die die Historie der Messdaten speichert, damit berechnungen und auch bessere Verläufe dargestellt werden können, ebenso der Verlauf der Messdaten über einen Zeitraum.
3. **Webpage:** Die Webpage wird neu geschrieben, damit sie flüssiger, performanter und leichter bedienbar ist. Die Webpage soll intern zugänglich sein, sodass die aktuellen Werte abgelesen werden können.
4. **API:** Eine selbst geschriebene API verbindet alle Elemente und überträgt die Daten:
   - Sensoren --> Datenbank
   - Datenbank --> Webpage

## 4. Langfristige Vision

Langfristig soll **pro Fenster und Tür der FH ein Sensor** installiert sein, sodass das gesamte Gebäude überwacht werden kann. Dieser Ausbau liegt in weiterer Zukunft, wird aber schon jetzt berücksichtigt: Das System wird von Anfang an skalierbar geplant, sodass neue Sensoren ohne Codeänderung hinzugefügt und einem Raum zugeordnet werden können.

## 5. Anforderungen an das System

| Anforderung | Beschreibung |
|---|---|
| Skalierbarkeit | Vom einzelnen Raum bis zum gesamten Gebäude erweiterbar |
| Zuverlässigkeit | Fehlerbehandlung und automatischer Reconnect bei Ausfällen |
| Energieeffizienz | Geringer Stromverbrauch der Sensoren |
| Wartbarkeit | Modularer, gut dokumentierter Code |
| Benutzerfreundlichkeit | Übersichtliche Darstellung der Werte |

## 6. Systemarchitektur

```text
    Sensoren
        │
        │
        ▼

       API  ◄────────►  Datenbank (Historie)
       
        │
        │
        ▼
     Webpage
```


## 7. Tests und Qualitätssicherung

- Unit-Tests für die Sensorlogik und die API.
- Test des Gesamtsystems in einer Testumgebung, bevor das richtige System der FH angeschlossen wird.
- Code-Reviews über Pull Requests auf GitHub.

## 8. Risiken

| Risiko | Gegenmaßnahme |
|---|---|
| Ausfall von Sensoren oder WLAN | Reconnect-Logik, Statusanzeige im Dashboard |
| Hohe Hardwarekosten bei vielen Sensoren | Schrittweiser Ausbau, günstige Mikrocontroller |
| Abstimmung mit der FH (Netzwerk, Genehmigungen) | Frühzeitige Kontaktaufnahme |
| Zeitmangel im Team | Klare Meilensteine und Aufgabenverteilung |

## 9. Mögliche Erweiterungen

- Warnung bei offenem Fenster oder offener Tür
- Empfehlungen für Heizung und Lüftung
- Auswertungen und Statistiken über die Datenhistorie
- Benachrichtigungen per App oder E-Mail