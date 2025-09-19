# SYT Projekt: Digitaler Rasentraktor

## Ziel:

In dem Projekt wollen wir einen Rasenmäher-Traktor digitalisieren. Das stellen wir uns so vor.  

Er soll:  
- fernstartbar sein,  
- alle möglichen Daten monitoren,  
- über eine WebApp verwendbar sein,  
- das Mähwerk ein- und ausschalten können,  
- Motortemperatur messen,  
- Motordrehzahl messen,  
- den Gashahn stellen,  
- die Drehzahl regeln,  
- beleuchtet sein,  
- Geschwindigkeit messen,  
- Sicherheitssensor für Sitz haben,  
- Sicherheitssensor für Kupplung/Bremse haben.  

## Bauteile/Systeme:
Was wir alles für dieses Projekt benötigen und wie die Punkte umgesetzt werden.  

### Microcontroller: 
- ESP32: verbunden via WLAN  
- DC-DC 12V zu 5V Spannungswandler  

### Sensoren:
- Drehzahlsensor  
  + entweder optisch oder mit induktivem Magnetmesser. Optisch wäre von der Spannung besser.  
- Temperatursensor  
  + kompliziertes Thema  

### Aktoren:
- Servomotor für den Gashahn; Spannung 5 Volt, Steuerung auf 3 Volt  
- Beleuchtung, LED?  
- Mähwerk AN/AUS  
  + Treiber + 12V Relais  
- Motorstart  
  + Treiber + 12V Relais  

---

### Docker, Services:
- Laptop, auf dem Docker läuft  
- Datenbank MySQL: dient zur Verwaltung der zahlreichen Sensordaten  
- Backend-Server: auf dem läuft die Business-Logic. Via WLAN stellt er eine Verbindung zum ESP her. Er wartet auf Daten vom ESP und kann ihm Befehle schicken. Das Backend stellt auch die Verbindung zur Datenbank und zum Webinterface her.  
- Website NGINX: stellt die Website bereit. Eine Oberfläche zur Verwendung des Traktors. Graphen der Sensordaten sollen auch da sein.  
- ESP32: ist als Microcontroller zur Datenbeschaffung und Ausführung da. Er schickt regelmäßig Daten ans Backend und wartet auf Befehle vom Backend.  
