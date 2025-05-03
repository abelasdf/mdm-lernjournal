# Lernjournal 2 Container

## Docker Web-Applikation

### Verwendete Docker Images

| | Bitte ausfüllen |
| -------- | ------- |
| Image 1 |abelasdf/mini-blog-web:latest  |
| Image 1 |https://hub.docker.com/r/abelasdf/mini-blog  |
| Image 2 |mysql:8.0  |
| Image 2 |https://hub.docker.com/_/mysql  |
| Docker Compose |https://github.com/abelasdf/lernjournal/blob/main/lernjournal2-container/docker-compose.yml |

### Dokumentation manuelles Deployment
Für das manuelle Deployment der Web-Applikation wurden die Images lokal via Dockerfile (Python Flask App) und direkt aus Docker Hub (MySQL 8.0) erstellt. Die App besteht aus einem Webserver (Flask) und einer MySQL-Datenbank.
<img width="424" alt="Bildschirmfoto 2025-05-03 um 15 33 29" src="https://github.com/user-attachments/assets/3f36f429-fd9f-4698-9812-2296cbe12e07" />

Die MySQL-Datenbank wurde separat mit Umgebungsvariablen gestartet:
<img width="453" alt="Bildschirmfoto 2025-05-03 um 15 34 14" src="https://github.com/user-attachments/assets/7fcae12b-b854-4152-8a18-64493d646e99" />

Es wurden Ports gemappt und die Anwendung war lokal auf http://localhost:5050 erreichbar.


### Dokumentation Docker-Compose Deployment
Mit Docker Compose wurde die Web-Applikation effizienter verwaltet. Es wurde eine docker-compose.yml mit zwei Services erstellt: web (Flask) und db (MySQL).
Start der gesamten Applikation:
<img width="362" alt="Bildschirmfoto 2025-05-03 um 15 38 09" src="https://github.com/user-attachments/assets/bba3cbde-15e8-497f-8ec2-dc5ba79410e8" />

Dies startete automatisch beide Container und ermöglichte die Kommunikation über ein gemeinsames internes Docker-Netzwerk. Das Web-Frontend war anschliessend unter localhost:5050 erreichbar.

## Deployment ML-App

### Variante und Repository

| Gewähltes Beispiel | Bitte ausfüllen |
| -------- | ------- |
| onnx-sentiment-analysis |  |
| onnx-image-classification |  |
| Repo URL Fork | URL |
| Docker Hub URL | URL |

### Dokumentation lokales Deployment



### Dokumentation Deployment Azure Web App




### Dokumentation Deployment ACA



### Dokumentation Deployment ACI

