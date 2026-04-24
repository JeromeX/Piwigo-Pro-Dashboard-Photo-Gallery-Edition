# 🖼️ Piwigo Pro Dashboard | Photo Gallery Edition

[![Docker](https://img.shields.io/badge/Docker-supported-blue.svg?logo=docker&logoColor=white)](https://www.docker.com/)
[![PHP](https://img.shields.io/badge/PHP-8.2-777bb4.svg?logo=php&logoColor=white)](https://www.php.net/)
[![Piwigo](https://img.shields.io/badge/Piwigo-v14.x-ff6600.svg?logo=piwigo&logoColor=white)](https://piwigo.org/)
[![Hardware](https://img.shields.io/badge/Hardware-HP--Gen8-orange.svg)](https://www.hpe.com)

Ein spezialisiertes Web-Interface zur Verwaltung und Überwachung deiner **Piwigo Fotogalerie**. Dieses Dashboard wurde für den **HP ProLiant MicroServer Gen8** optimiert, um Docker-basierte Piwigo-Instanzen effizient zu verwalten, Backups zu erstellen und die Performance der Galerie zu überwachen.
<img width="1920" height="1080" alt="2026-04-24 22_52_58-Piwigo Dashboard" src="https://github.com/user-attachments/assets/e61d09b2-ba39-4799-95c5-03a89104e20f" />

---

## 🌟 Kern-Features

* **📸 Gallery Monitoring:** Übersicht über die Anzahl der Fotos, Alben und den belegten Speicherplatz.
* **📦 Smart Backup:** Integrierte Logik zur Sicherung der MariaDB-Datenbank und der physischen Bilddaten.
* **🖼️ Metadata Management:** Schneller Zugriff auf Tools zur Synchronisation der Metadaten und Vorschaubilder.
* **📊 Health-Status:** Live-Überprüfung der Docker-Container (Web-Server & Datenbank).
* **🎛️ Master-Manager Integration:** Nahtlose Anbindung an den zentralen `dashboard-manager.sh` (V8) für System-Wartung.

---

## 📂 Verzeichnisstruktur

Die Instanz ist für den Betrieb unter `/opt` vorkonfiguriert:

```text
/opt/piwigo-dashboard/
├── 🐋 docker-compose.yml   # Orchestrierung von Webserver & DB
├── 🏗️ Dockerfile           # Optimiertes PHP-Image für Bildverarbeitung
├── 🌐 index.php            # Frontend UI (Responsive Design)
├── ⚙️ api.php              # API für Datenbank- & System-Status
├── 🕹️ control.php          # Steuerung der Wartungs-Tasks
└── 🛠️ dashboard-manager.sh # Globaler Master-Manager (CLI)

🚀 Installation & Deployment
1. Voraussetzungen
Docker & Docker-Compose installiert.

MariaDB/MySQL als Backend (wird über Compose mitgestartet).

2. Schnellstart
Klone das Repository nach /opt und wechsle direkt in den Projektordner:
cd /opt && \
git clone [https://github.com/DEIN-PROFIL/piwigo-dashboard.git](https://github.com/DEIN-PROFIL/piwigo-dashboard.git) && \
cd piwigo-dashboard

3. Container starten
Initialisiere die Umgebung und starte die Galerie im Hintergrund:
docker-compose up -d --build
