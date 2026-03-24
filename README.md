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
