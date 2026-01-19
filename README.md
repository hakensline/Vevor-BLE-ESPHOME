# Vevor-BLE-ESPHOME FRENCH VERSION FORKED FROM [@Knutnoh](https://github.com/Knutnoh/Vevor-BLE-ESPHOME) TANKS FOR YOUR JOB

# ESPHome – Vevor Chauffage DIESEL CHINASTO (BLE)

Intégration d'un **chauffage de stationnement diesel Vevor avec Bluetooth (BLE)** à [ESPHome](https://esphome.io).
Ce chauffage peut ainsi être facilement contrôlé et surveillé via Home Assistant ou l'interface web d'ESPHome.

---

## Différences à [Bruciatore_BLE](https://github.com/edwardtfn/Bruciatore_BLE)

Cette implémentation fonctionne avec **trois UUIDs**:

- `fff0` → Service UUID  
- `fff1` → Characteristic (Empfang, Notify)  
- `fff2` → Characteristic (Senden, Write)  

👉 Les valeurs sont définies dans le code et peuvent être ajustées au besoin.
Cela rend la solution plus flexible et adaptable à différents modèles de systèmes de chauffage.

---

## Fonctionnalitées

🔥 Chauffage On/Off (Marche/Arrêt)
🌡️ Température cible (Mode automatique)
💨 Niveaux de ventilation (Mode manuel)
🔄 Changement de mode : Automatique ↔ Manuel
🌬️ Mode ventilation seule (sans chauffage)
🏔️ Mode altitude (High Altitude Mode)
📊 Capteurs / Données :
Mode de fonctionnement (actuellement uniquement du passage manuel vers automatique)
État du chauffage (incluant les phases : préchauffage, allumage, chauffe, etc.)
Température ambiante
Température du corps de chauffe (échangeur)
Tension de la batterie
Valeur cible (consigne)

---

## Prérequis

Carte ESP32 (par ex. esp32dev)
ESPHome installé
Chauffage stationnaire diesel Vevor avec Bluetooth (BLE)
---

## Installation

1. Intégrer le code YAML dans votre projet ESPHome.
2. Ajuster les informations dans la section Substitutions :

   ```yaml
   substitutions:
     name: bt-vevor-ble
     friendly_name: Chauffage Diesel
     heater_mac: "XX:XX:XX:XX:XX:XX"   # MAC-Adresse eintragen
     service_uuid: "0000fff0-0000-1000-8000-00805f9b34fb"
     char_fff1_uuid: "0000fff1-0000-1000-8000-00805f9b34fb"
     char_fff2_uuid: "0000fff2-0000-1000-8000-00805f9b34fb"
