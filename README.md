 Rapport d’analyse statique – Application Android `app-debug.apk`

**Plateforme** : Mobexler VM  
**Outil** : Mobile Security Framework (MobSF) v4.0.6  
**Date** : Sun 08 Mar 2026  
**Contexte** : Évaluation de sécurité mobile – Laboratoire d’analyse statique (SAST)

---

            Table des matières

1. [Introduction et objectifs](#1-introduction-et-objectifs)
2. [Préparation de l’environnement et traçabilité](#2-préparation-de-lenvironnement-et-traçabilité)
3. [Lancement de MobSF](#3-lancement-de-mobsf)
4. [Import et analyse de l’APK](#4-import-et-analyse-de-lapk)
5. [Analyse du manifeste et des permissions](#5-analyse-du-manifeste-et-des-permissions)
6. [Analyse de la configuration réseau](#6-analyse-de-la-configuration-réseau)
7. [Analyse du code et des ressources](#7-analyse-du-code-et-des-ressources)
8. [Corrélation avec OWASP MASVS](#8-corrélation-avec-owasp-masvs)
9. [Conclusion et livrables](#9-conclusion-et-livrables)

---

 1. Introduction et objectifs

       Contexte académique

Ce laboratoire s’inscrit dans un module de **sécurité des applications mobiles**. L’objectif est de maîtriser les techniques d’**analyse statique** (SAST) en environnement contrôlé, sans exécution du code, afin d’identifier des vulnérabilités potentielles.

         Objectifs principaux

- **Étudier la surface d’attaque** : composants exposés, permissions, configuration du manifeste.
- **Détecter les vulnérabilités** : mauvaises pratiques de développement, bibliothèques non sécurisées.
- **Extraire des données sensibles** : clés API, URLs, identifiants en clair.
- **Appliquer une méthodologie rigoureuse** : traçabilité, documentation, corrélation avec OWASP MASVS.

          2. Préparation de l’environnement et traçabilité

### Organisation de l’espace de travail

Un répertoire dédié a été créé pour isoler les artefacts de l’analyse :

```bash
mkdir -p ~/labs/2026-03-08_apk_analysis
cd ~/labs/2026-03-08_apk_analysis
cp /path/to/app-debug.apk .
