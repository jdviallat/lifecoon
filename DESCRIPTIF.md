# Lifecoon — Suivi Santé

**Carnet de santé numérique personnel**, par **Bengacoon**.
Application mobile **Android** et **iOS** — 100 % gratuite, 100 % locale et chiffrée.

---

## 1. Présentation

Lifecoon est un carnet de santé de poche pensé pour les **patients chroniques**, les **seniors** et les **aidants**. Il centralise vos constantes, vos traitements, vos ordonnances, vos rendez-vous et vos documents médicaux, et sait en produire un **rapport PDF « pour mon médecin »** — le différenciateur n°1 du produit.

Principes directeurs :

- **Rassurant et lisible** : gros boutons, gros texte, code couleur clair (lisibilité senior).
- **Jamais de diagnostic médical** : Lifecoon signale seulement les dépassements des seuils **que vous définissez**, et invite à consulter.
- **Vie privée d'abord** : tout reste **sur l'appareil**, chiffré. Aucun cloud, aucun compte, aucune donnée envoyée (le suivi santé n'est pas un service en ligne → pas de sujet HDS).

---

## 2. Plateformes

| | Android | iOS |
|---|---|---|
| Stack | Kotlin · Jetpack Compose · Room (SQLCipher) · Hilt | SwiftUI · SwiftData |
| Identifiant | `com.lifecoon.sante` | `com.lifecoon.sante` |
| Distribution | APK direct + Google Play | App Store |
| Version actuelle | **1.7.4** (versionCode 39) | **1.7.4** (build 18) |

Les deux plateformes suivent **le même numéro de version** et offrent la **même** liste de fonctions (parité).

---

## 3. Fonctionnalités

### Constantes & suivi
- **Tension** (systolique / diastolique / **pouls**), avec catégories ESH/ESC 2023 et moyennes matin / soir.
- **Glycémie** (unité **g/L**, **mmol/L** ou **mg/dL** selon la région), avec moment de la mesure, insuline et repas.
- **Poids / IMC** (taille mémorisée), **SpO₂**, **température**, **fréquence cardiaque au repos**.
- **HbA1c estimée** (formule ADAG) sur 90 jours.
- Graphiques interactifs (infobulle au toucher, périodes 7 / 30 / 90 jours), carte **Tendances**, **temps dans la cible** (glycémie).
- **Saisie vocale** (« tension 12 8 »), reprise de la dernière valeur, **liste complète et éditable** de tous les relevés.

### Traitements & observance
- Médicaments avec **dosage, fréquence, horaires précis éditables**, photo de la boîte.
- **Rappels de prise** (AlarmManager / notifications), notification actionnable **« Pris ✓ »**, **snooze**.
- Suivi d'**observance sur 30 jours** (pris / oublié) et **séries (streaks)**.

### Ordonnances, appareils & pharmacie
- **Ordonnances renouvelables** : validité, photos, médicaments liés, **journal de délivrance**, alerte d'expiration.
- **Appareils de mesure** et **consommables** (aiguilles, bandelettes, lancettes…) : fiches, photos, **stock et alertes**, **scan du code-barres**.
- **Liste de courses pharmacie** (médicaments à retirer + consommables à racheter), partageable.
- **Carnet de pharmacies** (téléphone et adresse cliquables).

### Rendez-vous, documents & carte d'urgence
- **Rendez-vous** médicaux (médecin, spécialité, adresse, rappel, synchro **calendrier / CalDAV**).
- **Documents** médicaux (photo ou PDF) avec **OCR embarqué** (extraction de texte hors-ligne).
- **Bouton Scan** : photographier une ordonnance → choisir la destination (ordonnance, médicament, rendez-vous ou document), écran **pré-rempli par OCR**.
- **Carte d'urgence / Medical ID** : groupe sanguin, allergies, personne à prévenir, **et traitements en cours ajoutés automatiquement**. Option **« Afficher sans déverrouiller »** → un bouton sur l'écran de verrouillage montre la carte **en lecture seule**, sans ouvrir l'app.

### Export & rapports
- **Rapport PDF « pour mon médecin »** (période au choix) : résumé min / max / moyenne, graphiques, **pouls** et **relevés bruts**.
- **Tableaux en grille** (glycémie, tension, poids, global) façon carnet hospitalier.
- Export **Excel (.xlsx)** multi-feuilles.
- **Sauvegarde / restauration** chiffrée `.lifecoon` (manuelle **et** automatique).

### Confort & sécurité
- **9 langues** : français, anglais, allemand, espagnol, italien, portugais, suédois, norvégien, finnois.
- **Fiche utilisateur** avec photo de profil (avatar sur l'accueil), accueil personnalisé.
- **Multi-profils** (famille).
- Verrouillage **biométrique + code PIN**, délai de verrouillage, masquage dans le sélecteur d'apps.
- **Photos en plein écran** avec zoom et **recadrage** avant enregistrement.
- **Raccourcis d'accueil**, **objectifs** personnels, **journal** symptômes / humeur / douleur, **rappels d'examens** récurrents.
- **Assistant santé** (conseils non médicaux), **tour guidé** + aide / FAQ.
- **Écriture Santé / Health Connect** et import glycémie (capteur).
- **Gestion des mises à jour** intégrée (vérifie une nouvelle version et propose de la télécharger).

---

## 4. Confidentialité & conformité

- Données **stockées uniquement sur l'appareil**, base **chiffrée** (SQLCipher / SwiftData), secrets en zone sécurisée (EncryptedSharedPreferences / Keychain).
- **Aucune collecte**, aucun traceur, aucun compte.
- Consentement **RGPD (UE) + nLPD (Suisse)** à l'installation, droit d'**effacement total** en un geste.
- **Aucun diagnostic médical** : seuils définis par l'utilisateur, invitation à consulter.

---

## 5. Historique des versions

### Version majeure en cours

| Version | Date | Points clés |
|---|---|---|
| **1.7.4** | Juil. 2026 | Carte d'urgence : traitements en cours ajoutés automatiquement · option « Afficher la carte d'urgence sans déverrouiller » (bouton sur l'écran de verrouillage, lecture seule) · vérification des mises à jour corrigée |
| **1.7.3** | Juil. 2026 | Plus de verrouillage à l'ouverture de l'appareil photo / d'un scan (corrige la photo OCR perdue) · fiche utilisateur avec photo · page dédiée « Appareils & consommables » · photos plein écran + recadrage |
| **1.7.2** | Juil. 2026 | Bouton « Scanner une ordonnance » → choix de la destination · OCR de pré-remplissage · export enrichi (pouls, SpO₂, température, FC, relevés bruts) · tout devient modifiable · horaires de prise éditables · liste éditable des relevés |
| **1.7.0** | Juil. 2026 | Ordonnances renouvelables · appareils & consommables (scan code-barres) · liste de courses pharmacie · carnet de pharmacies |
| **1.6.3** | Juil. 2026 | Réglages & accueil relookés · graphiques interactifs + carte Tendances · saisie vocale · stabilité |
| **1.6.0** | Juil. 2026 | Application entièrement traduite en **9 langues** |
| **1.5.0** | Juil. 2026 | Journal symptômes/humeur/douleur · SpO₂/température/FC repos · séries · rappels d'examens · raccourcis d'accueil · rapport médecin enrichi (graphes) · sauvegarde chiffrée auto · aide/FAQ · Santé/Health Connect · options de sécurité |
| **1.0.0** | Juin 2026 | Première version publiée : tension, glycémie, poids, traitements · ordonnances (photos), RDV, documents, multi-profils · rappels, export PDF/Excel, carte d'urgence · 100 % local et chiffré |

### Genèse (versions 0.x)

| Version | Date | Points clés |
|---|---|---|
| 0.15.0 | Juin 2026 | Essai gratuit 7 j + déblocage par achat unique *(modèle abandonné depuis : app 100 % gratuite)* |
| 0.14.0 | Juin 2026 | Choix de l'unité de glycémie · moyennes tension matin / soir |
| 0.13.0 | Juin 2026 | Synchronisation des rendez-vous vers un compte agenda (CalDAV) |
| 0.12.0 | Juin 2026 | Tableaux en grille tension / poids / global (PDF + Excel) |
| 0.11.0 | Juin 2026 | Tableau de glycémie façon carnet hospitalier |
| 0.10.0 | Juin 2026 | Tableau de bord : cartes cliquables vers le détail |
| 0.9.0 | Juin 2026 | Import des pesées depuis Health Connect |
| 0.8.0 | Juin 2026 | Assistant santé + conseil du jour |
| 0.7.0 | Juin 2026 | OCR : extraction du texte d'un document photographié (hors-ligne) |
| 0.6.0 | Juin 2026 | Documents médicaux (photo / PDF) |
| 0.5.1 | Juin 2026 | Ajout d'un rendez-vous au calendrier du téléphone |
| 0.5.0 | Juin 2026 | Résumé des tendances · bannière de vigilance · seuils personnalisables · rappels de mesure · sauvegarde/restauration · photo de médicament |
| 0.4.1 | Juin 2026 | Section À propos + journal des versions |
| 0.4.0 | Juin 2026 | Signature « by Bengacoon » · gestion automatisée des builds |
| 0.3.0 | Juin 2026 | Profil patient (date de naissance / âge) · édition des mesures a posteriori |
| 0.2.0 | Juin 2026 | Rendez-vous médicaux avec rappels · export Excel |
| 0.1.0 | Juin 2026 | Version initiale : verrouillage biométrique + PIN · tension / glycémie / poids (IMC) · graphiques · traitements + rappels · export PDF · onboarding RGPD/nLPD |

> Le journal complet est aussi consultable **dans l'application** (Réglages → À propos → Journal des versions).

---

## 6. Mises à jour

L'application vérifie les nouvelles versions via le dépôt public **[lifecoon](https://github.com/jdviallat/lifecoon)** (`latest.json` + APK dans les *Releases*). Aucune donnée personnelle n'est transmise lors de cette vérification.

- **Android** : dernier APK → https://github.com/jdviallat/lifecoon/releases/latest
- **iOS** : via l'App Store.

---

*Lifecoon — un produit **Bengacoon**. Vos données de santé vous appartiennent.*
