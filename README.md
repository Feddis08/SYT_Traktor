# SYT Projekt: Digitaler Rasentraktor

**Microcontroller:**  
- ESP32, Verbunden via WLAN  

**Sensoren:**  
- Drehzahlsensor  
- Temperatursensor  

**Aktoren:**  
- Servomotor für den Gashahn  
- Beleuchtung  
- Mähwerk AN/AUS  
- Motorstart  

---

**Docker, Services:**  
- Laptop, auf dem Docker rennt.  
- Ein Container, auf dem der Code läuft, um Verbindung mit dem ESP32 aufzunehmen.  
- Alle Daten, die via einem Poll gezogen sind, werden in einer Datenbank gespeichert.  
- Diese ist als Container im Docker.  
- Abschließend ein Webserver, über den man sich alle Daten visuell ansehen kann und den ESP steuern kann.  
