# Projekt 2 Java

## Übersicht

| | Bitte ausfüllen |
| -------- | ------- |
| Variante | Vorhandenes Modell / Vorlesungsbeispiel (angepasst)  |
| Datensatz (wenn selbstgewählt) | EMNIST-Bilder (bzw. Testbilder in Ordnerstruktur)|
| Datensatz (wenn selbstgewählt) | PNG (einzelne Klassenordner: happy, sad, etc.) |
| Modell (wenn selbstgewählt) | URL |
| ML-Algorithmus |  Vortrainiertes ONNX-Modell für Emotionserkennung |
| Repo URL | [[URL](https://github.com/abelasdf/emotion-app)](https://github.com/abelasdf/mdmemotionapp) |


## Dokumentation

## Daten

Der verwendete Datensatz basiert auf vordefinierten Testbildern, die lokal in Klassenordnern gespeichert sind. Diese Bilder repräsentieren verschiedene emotionale Zustände (z. B. glücklich, traurig, wütend). Das Ziel ist es, eine automatische Zuordnung der Bilder zu ihrer jeweiligen Klasse über das ONNX-Modell durchzuführen.

![Emotionserkennung – Upload-UI](images/Bildschirmfoto%202025-05-25%20um%2022.49.50.png)

Diese Daten wurden nicht selbst annotiert, aber sorgfältig in das Projekt eingebunden und genutzt, um die ONNX-Inferenz zu evaluieren.

---

## 🧠 Modell & Training

Ein vortrainiertes ONNX-Modell für die Emotionserkennung wurde verwendet. Dieses wurde lokal gespeichert und mit der Bibliothek `onnxruntime` geladen. Es handelt sich um ein CNN-Modell, das Eingabebilder klassifiziert.

Das Modell wurde **nicht selbst trainiert**, sondern diente im Rahmen dieses Projekts zur Demonstration von Inferenz und Modellintegration.



---

## ⚙️ Inferenz / Serving

Zur Umsetzung der Inferenz wurde ein Python-Backend mit **Flask** implementiert. Die App bietet ein Upload-Formular für Benutzer, um PNG- oder JPEG-Bilder auszuwählen. Das Bild wird vorverarbeitet (Skalierung, Umwandlung in NumPy-Array etc.) und an das ONNX-Modell übergeben.

Nach der Verarbeitung zeigt die Web-App die ermittelte Emotion direkt auf der Webseite an.



---

## 📦 Deployment



![Emotionserkennung – Ergebnisanzeige](images/Bildschirmfoto%202025-05-25%20um%2022.51.44.png)

Die Anwendung wurde lokal containerisiert und mit **Docker** ausgeführt. Die Ausführung erfolgte auf Port `5051` via:

```bash
flask run --port=5051




