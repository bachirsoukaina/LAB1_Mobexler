# 🔐 Lab 1 — Mise en place de l'environnement Mobexler

## 📌 Description

Dans ce lab, on prépare un environnement de pentest mobile complet.
On importe la VM Mobexler, on configure le réseau et on connecte une cible Android pour pouvoir lancer des analyses de sécurité.

---

## 🎯 Objectifs

- Importer et démarrer la VM Mobexler sous VMware
- Configurer les interfaces réseau (NAT + Host-Only)
- Valider la connectivité Internet depuis la VM
- Créer un snapshot de référence (baseline)
- Connecter un appareil Android via ADB

---

## 🚀 Étapes réalisées

### 1️⃣ Connexion à Mobexler

Après import de l'OVA et démarrage de la VM, connexion avec les identifiants par défaut :

| Champ | Valeur |
|-------|--------|
| Username | `mobexler` |
| Password | `mobexler` |

<img width="406" height="180" alt="Capture d’écran 2026-05-02 165250" src="https://github.com/user-attachments/assets/e2ff4790-e030-49b9-8bdc-3a6af615837e" />


---

### 2️⃣ Test de connectivité réseau

Vérification que la VM accède bien à Internet via l'interface NAT.

```bash
ping -c 2 8.8.8.8
```
<img width="958" height="138" alt="Capture d’écran 2026-05-02 170541" src="https://github.com/user-attachments/assets/37a25b6b-1f06-40a5-ac0f-56368db55a5e" />



---

### 3️⃣ Snapshot CLEAN

Création d'un point de restauration avant toute manipulation, pour pouvoir revenir à un état propre à tout moment.

> **Nom :** `CLEAN_BASELINE_TP1`

<img width="389" height="275" alt="Capture d’écran 2026-05-02 165350" src="https://github.com/user-attachments/assets/bd72d985-3e39-4a98-a14e-4d6eb438662a" />


---

### 4️⃣ Connexion ADB — Cible Android

Vérification que l'appareil Android est bien reconnu par ADB.

```bash
adb version
adb devices
```

L'outil ADB (Android Debug Bridge) permet d'établir une communication entre Mobexler et la cible Android.
Une fois le débogage USB activé sur l'appareil, celui-ci apparaît avec le statut `device` confirmant
que la connexion est opérationnelle et prête pour les tests de sécurité.
