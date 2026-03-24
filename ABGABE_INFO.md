# DevOps-Abgabe für Prof. Farrenkopf

## Status: ✅ Pipeline erfolgreich

Technische Abgabe erfolgreich. Pipeline umfasst **Build & Test**, **Docker-Image-Erstellung** und **K8s-Validierung**.

---

## 🔧 Wichtigste Korrektionen (heute durchgeführt)

### 1. Upgrade der GitHub Actions auf v4
- `actions/checkout@v3` → `actions/checkout@v4`
- `actions/setup-java@v3` → `actions/setup-java@v4`
- `actions/upload-artifact@v3` → `actions/upload-artifact@v4`
- **Grund:** Veraltete Action-Versionen können zu deprecated warnings und Security-Issues führen

### 2. Fix der Spring Boot Version in der pom.xml
- Hardcoded `version: 3.2.4` statt Variable `${spring-boot.version}`
- **Grund:** Inconsistence beim Maven-Build vermeiden und Version eindeutig festlegen

### 3. Korrektur der Docker-Multi-Stage-Pfade
- **Build-Stage:** `maven:3.8.5` → `maven:3.9.6-eclipse-temurin-17`
- **Runtime-Stage:** `openjdk:17-jdk-slim` → `eclipse-temurin:17-jre-jammy`
- **WORKDIR-Fix:** Build läuft in `/app` statt `/workspace`
- **COPY-Befehl:** `COPY --from=build /app/target/*.jar`
- **Grund:** Stabile, regulär gepflegte Basis-Images

---

## 📊 Pipeline-Struktur

```
.github/workflows/main.yml
├── Job 1: Build & Test (Maven, Java 17)
│   ├── Checkout
│   ├── Set up Java 17
│   ├── Build & Test with Maven
│   └── Upload JAR Artifact
│
├── Job 2: Docker Build (depends on Job 1)
│   ├── Checkout
│   ├── Set up Docker Buildx
│   ├── Build Docker Image
│   └── List Docker Image
│
└── Job 3: Kubernetes Validation (depends on Job 2)
    ├── Checkout
    ├── Check k8s_deployment.yaml
    ├── Display Manifest
    └── Validate YAML Syntax (safe_load_all für Multi-Doc)
```

---

## 🚀 Deployment

- **k8s_deployment.yaml:** 2 Replicas + Service (NodePort)
- **Health Checks:** Liveness & Readiness Probes auf `/` (Port 8080)
- **Container-Image:** `devops-app:latest` (Temurin-basiert)

---

## 📝 Commit-Historie

- Initial DevOps Stack for Prof. Farrenkopf
- Korrektur: CI/CD-Pipeline auf GitHub Actions v4 aktualisiert zur Behebung von Veraltungsfehlern
- Korrektur: Spring Boot Version in pom.xml fest definiert zur Behebung des Build-Fehlers
- Korrektur: Stabilere Docker-Basis-Images (Temurin) gewählt und Pfade im Multi-Stage Build korrigiert
- Korrektur: Kubernetes-Validierung für Multi-Dokument-YAML angepasst
- Fix: Einrückung im Pipeline-Skript korrigiert

---

## 🎯 Nächste Schritte (optional für Erweiterung)

- **Quality Assurance** (Alina): SonarQube Analysis Job in der Pipeline hinzufügen
- **Helm Charts** für vereinfachtes Kubernetes-Deployment
- **ArgoCD** für GitOps-Workflow
- **Terraform** für Infrastructure-as-Code

---

**Abgabe:** 24.03.2026  
**Gruppe:** Faris & Team  
**Repository:** https://github.com/Sa1maaaaa/DEVOPS
