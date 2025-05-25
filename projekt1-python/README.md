# Projekt 1 Python

## Übersicht

| | Bitte ausfüllen |
| -------- | ------- |
| Variante | Eigenes Projekt|
| Datenherkunft | HTML |
| Datenherkunft | [URL](https://www.flughafen-zuerich.ch/de/passagiere/fliegen/fluginformation/ankunft) |
| ML-Algorithmus | RandomForestClassifier |
| Repo URL | [URL](https://github.com/abelasdf/flight-delay-predictor) |

##  Data Scraping

Die Flugdaten wurden automatisiert mithilfe von **Selenium** direkt von der Ankunftsseite des Flughafens Zürich extrahiert. Dabei wurde der HTML-Inhalt live analysiert und verarbeitet.

**Besonderheiten:**
- Scraping im Zeitbereich und gesamter Tagesbereich
- Nur die erste Flugnummer eines Listeneintrags wird als eindeutige ID behandelt
- Speicherung und Verwaltung in **MongoDB Atlas**

![Screenshot 1 – Scraping-Ausgabe](images/Bildschirmfoto%202025-05-25%20um%2022.26.44.png)

---

##  Training

Das Vorhersagemodell wurde mit einem **Random Forest** trainiert. Als Features dienten u. a.:
- geplante Ankunftszeit (`scheduled_hour`)
- Flugnummer (numerisch kodiert)
- Airline (kodiert)
- Wochentag
- Wetterdaten (live via OpenWeatherMap)
- Herkunftsflughafen (kodiert)

Trainingsdaten wurden aus der MongoDB-Datenbank geladen und verarbeitet.

![Screenshot 2 – Trainingsvorgang oder Featureübersicht](images/Bildschirmfoto%202025-05-25%20um%2022.28.18.png)

---

## ModelOps Automation

Das Projekt enthält Skripte zur:
- automatischen Modellaktualisierung
- Modell-Export in `.pkl`
- Upload des Modells in **Azure Blob Storage**

![Screenshot 3 – Modellvorhersage oder UI](images/Bildschirmfoto%202025-05-25%20um%2022.29.59.png)

---

## 🖥 UI / Backend

Die Web-App basiert auf **Flask** und erlaubt:
- Eingabe der Flugnummer
- Abfrage der aktuellen Wetterdaten
- Vorhersage der Verspätung
- Visualisierung des Ergebnisses in HTML

---

##  Deployment

Die App wurde über **Docker** containerisiert und mit **Azure App Service** bereitgestellt.

- Dockerfile beschreibt Abhängigkeiten
- Deployment erfolgte via Azure CLI (`az webapp up`)
- Screencast zeigt vollständig funktionierendes Deployment

- ![Screenshot Analyse/Ergebnis](images/Bildschirmfoto%202025-05-25%20um%2022.35.04.png)


---
