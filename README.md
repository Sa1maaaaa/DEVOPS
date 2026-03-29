# THM DevOps Projekt – Java Spring Boot Application

## Projektbeschreibung

Dieses Projekt demonstriert eine vollständige DevOps-Struktur fuer eine Java-basierte Spring-Boot-Anwendung. Ziel ist es, den kompletten Software-Lifecycle von Entwicklung und Tests ueber Containerisierung und CI/CD bis zum Deployment in Kubernetes automatisiert und nachvollziehbar abzubilden.

## Features

- Java 17 und Spring Boot fuer eine moderne Backend-Architektur
- Automatisierte Tests mit JUnit 5
- CI/CD-Pipeline mit GitHub Actions
- Docker-Containerisierung mit produktionsnaher Laufzeitumgebung
- Kubernetes-Deployment fuer den Betrieb im Cluster

## Team und Rollen

- Faris: Application Development mit Java und Spring Boot
- Amin: Infrastructure und Containerization mit Docker
- Melisa: CI/CD-Pipeline und Automatisierung mit GitHub Actions
- Alina: Quality Assurance und Teststrategie
- Salma: Projektkoordination, Repository-Management und Dokumentation

## Architektur-Entscheidungen

- Java 17 als LTS-Version fuer Stabilitaet und moderne Sprachfeatures
- Spring Boot fuer schnellen Aufbau einer produktionsreifen Webanwendung
- Docker fuer konsistente Laufzeitumgebungen in Entwicklung und Deployment
- GitHub Actions als integrierte CI/CD-Loesung

## DevOps-Workflow-Strategie

In unserem Projekt trennen wir bewusst die lokale Entwicklung von der automatisierten CI/CD-Pipeline auf GitHub, um zentrale DevOps-Prinzipien sichtbar zu machen.

### Lokaler Workflow (Verifikation)

Anstatt auf fehleranfaelliges Hot-Reloading zu setzen, verwenden wir lokal manuelle Rebuilds mit Docker:

```bash
docker build --no-cache -t devops-app .
```

So stellen wir sicher, dass der Code in einem isolierten Container exakt so gebaut und ausgefuehrt wird, wie spaeter in der Cloud. Das reduziert die typischen Umgebungsabweichungen nach dem Motto: "Auf meinem Rechner hat es funktioniert".

### Automatisierung (CI/CD auf GitHub)

Nach dem Push uebernimmt GitHub Actions vollautomatisch Build, Tests und Paketierung der Anwendung. Dabei folgt die Pipeline dem Prinzip der Immutable Infrastructure: Jede Aenderung erzeugt ein neues, unveraenderliches Docker-Image.

### DevOps-Ziel

Durch diesen Ablauf erreichen wir eine hohe Paritaet zwischen Entwicklung und Produktion. Fehler werden durch die automatisierte Pipeline frueh erkannt (Fail-Fast), bevor sie Endnutzer erreichen.

## Projektstatus

- [x] Repository-Setup
- [x] Java-Code im Repository
- [x] Dockerfile vorhanden
- [x] Kubernetes-Deployment vorhanden
- [x] Tests im Projekt angelegt

## Projektstruktur

```text
DEVOPS
├── .github/workflows/main.yml
├── src/
├── Dockerfile
├── k8s_deployment.yaml
├── pom.xml
└── README.md
```

## Lokales Starten

Voraussetzungen:

- Java 17
- Maven

Build ausfuehren:

```bash
mvn clean package
```

Anwendung lokal starten:

```bash
mvn spring-boot:run
```
