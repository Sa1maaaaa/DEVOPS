THM DevOps Projekt – Java Spring Boot Application

Projektbeschreibung

Dieses Projekt demonstriert eine vollständige DevOps-Struktur für eine Java-basierte Microservice-Anwendung.  
Ziel ist es, den kompletten Software-Lifecycle – von der Entwicklung über Testing, Containerisierung, CI/CD bis hin zum Deployment in Kubernetes – **automatisiert und nachvollziehbar** abzubilden.

---

##  Features

-  **Java 17 & Spring Boot:** Robuste und moderne Backend-Architektur.
-  **Automatisierte Tests:** JUnit 5 Integration für zuverlässige Quality Assurance.
-  **CI/CD Pipeline:** Automatisierter Build- und Test-Prozess mit GitHub Actions.
-  **Docker Containerisierung:** Multi-Stage Builds für schlanke, produktionsreife Images.
-  **Kubernetes Deployment:** Orchestrierung der Anwendung im Cluster.

---

## 👥 Team & Rollen (Gruppe)

Dieses Projekt wurde kollaborativ im Rahmen einer arbeitsteiligen DevOps-Struktur umgesetzt:

- **Faris (Application Development):** Entwicklung der Spring Boot Webanwendung und Konfiguration des Maven-Build-Prozesses (`pom.xml`).
- **Amin (Infrastructure & Containerization):** Erstellung des `Dockerfile` und Optimierung der Container-Umgebung (Multi-Stage Build).
- **Melisa (CI/CD DevOps):** Aufbau und Konfiguration der automatisierten GitHub Actions Pipeline (`main.yml`).
- **Alina (Quality Assurance):** Definition der Teststrategie, Implementierung von Unit-Tests und Überwachung der Pipeline-Test-Reports.
- **Salma (Project Management):** Koordination, GitHub Repository & Board Management, Dokumentation und finale Abnahme.

---

##  Projektstruktur
```text
  DEVOPS
├── .github/workflows/main.yml    # CI/CD-Pipeline Definition (Melisa)
├── src/                          # Java Quellcode & Tests (Faris & Alina)
├── Dockerfile                    # Container Definition (Amin)
├── k8s_deployment.yaml           # Kubernetes Konfiguration
├── pom.xml                       # Maven Build- & Abhängigkeits-Konfiguration
└── README.md                     # Projekt-Dokumentation (Salma)
```


---

##  Installation & Lokales Testen (Java/Maven)

Um das Projekt lokal ohne Docker auszuführen, wird Java 17 und Maven benötigt:

Abhängigkeiten installieren und Projekt bauen:
```bash
mvn clean package

Bash
## App lokal starten:
mvn spring-boot:run
