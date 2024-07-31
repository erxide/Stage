# Étude de Marché : Solutions de Monitoring pour une Infrastructure Kubernetes (K8s)

## Introduction

Ce document a pour objectif de présenter une étude de marché sur les différentes solutions de monitoring adaptées à une infrastructure Kubernetes (K8s) sous Ubuntu. Il compare les fonctionnalités, les coûts et les avantages des principales solutions disponibles.

## Les Différentes Technologies Possibles pour une Infrastructure K8s

### Technologies Natifs Kubernetes

Pour une infrastructure Kubernetes, il est souvent préférable d'utiliser des programmes de monitoring spécifiquement conçus pour s'intégrer de manière optimale avec Kubernetes. Ces outils sont adaptés pour gérer les spécificités des environnements conteneurisés et offrent des fonctionnalités avancées pour le monitoring des pods, des services, des nœuds, et des clusters Kubernetes.

### Pourquoi se concentrer sur Prometheus + Grafana, Datadog, Sysdig et cAdvisor ?

Ces quatre solutions sont les plus recommandées pour les infrastructures Kubernetes en raison de leur intégration native, de leur flexibilité et de leur popularité dans la communauté DevOps.

**Autres solutions de monitoring pour Kubernetes** :

- **New Relic** : Bonnes fonctionnalités de monitoring et APM, mais coût élevé.
- **ELK Stack (Elasticsearch, Logstash, Kibana)** : Puissant pour la gestion des logs, mais complexe à mettre en œuvre et maintenir.
- **Zabbix** : Open-source et flexible, mais nécessite une configuration initiale complexe.
- **Splunk** : Excellentes capacités d'analyse des logs, mais très coûteux.
- **SolarWinds** : Très complet, mais peut être surdimensionné et coûteux pour des petites à moyennes infrastructures.

### Prometheus + Grafana

**Prometheus** est une solution open-source de monitoring et d'alerting développée par la Cloud Native Computing Foundation. Il est particulièrement bien adapté pour Kubernetes grâce à ses capacités de découverte de services et à sa flexibilité.

**Grafana** est un outil de visualisation et d'analytique de données souvent utilisé avec Prometheus pour afficher les métriques de Kubernetes.

**Avantages** :

- Coût : Gratuit (open-source)
- Mise en place rapide via Helm
- Adaptabilité : Bonne adaptabilité pour ajouter des nœuds, auto-discovery des services Kubernetes
- Flexibilité : Puissant langage de requête (PromQL) et tableaux de bord personnalisables avec Grafana
- Support et communauté : Large communauté open-source offrant une vaste documentation et de nombreux plugins

**Inconvénients** :

- Complexité initiale : Peut nécessiter une certaine courbe d'apprentissage pour la configuration initiale
- Maintenance : Nécessite une gestion et une maintenance continues
- Scalabilité : Nécessite des configurations supplémentaires (comme Thanos) pour le stockage long terme et le scaling horizontal

### Datadog

Datadog est une plateforme de monitoring SaaS qui offre une intégration native avec Kubernetes et une interface utilisateur intuitive.

**Abonnements et Tarification** :

## Infrastructure Monitoring

- **Pro Plan** :
  - $15 par hôte par mois (annuel) ou $18 par hôte par mois (mensuel)
  - Fonctionnalités : Monitoring centralisé, plus de 600 intégrations, tableaux de bord personnalisables, rétention des métriques de 15 mois, alertes avancées

- **Enterprise Plan** :
  - $23 par hôte par mois (annuel) ou $27 par hôte par mois (mensuel)
  - Fonctionnalités : Toutes les fonctionnalités du Pro Plan, alertes basées sur l'IA, surveillance en temps réel des processus, contrôles administratifs avancés, SLA de disponibilité de 99,9%

### APM (Application Performance Monitoring)

- **APM Pro** :
  - $31 par hôte par mois (annuel) ou $37 par hôte par mois (mensuel)
  - Fonctionnalités : Surveillance des traces distribuées, métriques de service, découverte automatique des services, rétention des traces de 15 jours

- **APM Enterprise** :
  - $45 par hôte par mois (annuel) ou $54 par hôte par mois (mensuel)
  - Fonctionnalités : Toutes les fonctionnalités de l'APM Pro, rétention des traces de 30 jours, cartes de service détaillées, outils d'analyse des causes racines

### Pourquoi Datadog Enterprise Plan ?

Le **Datadog Enterprise Plan** a été choisi comme la meilleure option payante pour les raisons suivantes :

- **Fonctionnalités avancées** : En plus des fonctionnalités du plan Pro, ce plan inclut des alertes basées sur l'IA et la surveillance en temps réel des processus, cruciales pour les infrastructures complexes.
- **SLA de disponibilité** : Garantie de 99,9%, offrant une haute disponibilité.
- **Contrôles administratifs** : Options de gestion et de contrôle avancées qui peuvent être essentielles pour les grandes entreprises.
- **Support et assistance** : Support premium avec SLA, assistance technique et des options de formation.

### Sysdig

Sysdig est une solution de monitoring et de sécurité conçue pour les conteneurs et Kubernetes.

**Abonnements et Tarification** :

### Sysdig Monitor

- **Standard Plan** :
  - Il faut demander un devis personnalisé sur leur site.
  - Fonctionnalités : Monitoring de l'infrastructure et des applications, tableaux de bord personnalisables, alertes de base, intégrations avec des outils DevOps, rétention des données à court terme

- **Enterprise Plan** :
  - Il faut demander un devis personnalisé sur leur site.
  - Fonctionnalités : Toutes les fonctionnalités du plan Standard, monitoring avancé pour Kubernetes, rétention des données à long terme, alertes avancées, intégration avec des outils de sécurité et de conformité

### Pourquoi Sysdig Monitor Enterprise Plan ?

Le **Sysdig Monitor Enterprise Plan** a été choisi comme la meilleure option payante pour les raisons suivantes :

- Offre un monitoring avancé spécifiquement conçu pour Kubernetes, ce qui est crucial pour une infrastructure K8s.
- Inclut des fonctionnalités de sécurité et de conformité robustes.
- Bien que les prix ne soient pas spécifiés, il fournit une solution tout-en-un sans nécessiter des modules complémentaires pour la sécurité.
- Rétention des données à long terme et alertes avancées basées sur des politiques.
- Support commercial et assistance personnalisée, crucial pour des configurations complexes et des environnements à grande échelle.

### cAdvisor

**cAdvisor (Container Advisor)** est un outil open-source développé par Google pour analyser les performances des conteneurs.

**Avantages** :

- Gratuit et open-source.
- Installation et configuration simples.
- Collecte des métriques sur l'utilisation des ressources (CPU, mémoire, réseau) des conteneurs en temps réel.
- Prend en charge Docker et d'autres moteurs de conteneurs.
- Intégration facile avec d'autres outils de monitoring et d'alerting.

**Inconvénients** :

- Fonctionnalités limitées par rapport à des solutions de monitoring plus complètes comme Datadog ou Sysdig.
- Principalement axé sur le monitoring des ressources et non sur la sécurité ou la conformité.

**Utilisation dans Kubernetes** :

- Souvent utilisé comme une base pour collecter des métriques dans des environnements Kubernetes.
- Peut être intégré avec Prometheus pour des capacités de monitoring plus avancées.

Pour plus d'informations sur cAdvisor, vous pouvez visiter son dépôt GitHub.

## Tableau Comparatif des Meilleurs Abonnements et des Solutions Gratuites

| **Critères**                   | **Prometheus + Grafana (Gratuit)** | **Datadog Enterprise**                        | **Sysdig Monitor Enterprise**                | **cAdvisor (Gratuit)**                        |
|--------------------------------|------------------------------------|----------------------------------------------|----------------------------------------------|----------------------------------------------|
| **Coût**                       | Gratuit                            | $23/hôte/mois (annuel), $27/hôte/mois (mensuel) | Devis personnalisé requis                    | Gratuit                                      |
| **Monitoring centralisé**      | Oui                                | Oui                                          | Oui                                          | Non (limité aux métriques des conteneurs)    |
| **Rétention des métriques**    | Personnalisable avec Thanos        | 15 mois                                      | Long terme                                   | Limitée                                      |
| **Alertes**                    | Basique, personnalisable           | Basées sur l'IA                              | Avancées et basées sur des politiques        | Non (intégration nécessaire)                 |
| **Surveillance des processus** | Non                                | Oui, en temps réel                           | Oui                                          | Non                                          |
| **Intégrations**               | Nombreuses avec exporters          | 600+ intégrations                            | Intégrations optimisées pour DevOps et conteneurs | Oui, via Prometheus                          |
| **Contrôles administratifs**   | Limité                             | Avancés                                      | Avancés                                      | Non                                          |
| **SLA de disponibilité**       | Non spécifié                       | 99,9%                                        | Non spécifié                                 | Non spécifié                                 |
| **Sécurité**                   | Personnalisable avec des outils tiers | Intégrations disponibles                     | Sysdig Secure intégré pour les conteneurs    | Non                                          |
| **Conformité**                 | Personnalisable avec des outils tiers | Modules complémentaires                      | Intégrée                                     | Non                                          |
| **Support**                    | Communautaire                      | Premium, assistance technique, SLA           | Support commercial et personnalisé           | Communautaire                                |
| **Documentation et Communauté**| Large et active                    | Étendue et active                            | Détails pour les environnements conteneurisés | Large et active                              |

### Explication des Critères

- **Coût** : Le montant à payer pour utiliser le service.
- **Monitoring centralisé** : Capacité à centraliser le monitoring pour une vue unifiée de l'infrastructure.
- **Rétention des métriques** : Durée pendant laquelle les métriques sont conservées pour l'analyse.
- **Alertes** : Capacité à configurer des notifications en cas d'anomalies.
- **Surveillance des processus** : Surveillance en temps réel des processus système et des applications.
- **Intégrations** : Capacité à se connecter à d'autres outils et services.
- **Contrôles administratifs** : Fonctions avancées de gestion des utilisateurs et des permissions.
- **SLA de disponibilité** : Garantie de disponibilité du service.
- **Sécurité** : Fonctionnalités de sécurité intégrées pour protéger les données et les applications.
- **Conformité** : Capacités à répondre aux exigences réglementaires et de conformité.
- **Support** : Niveau d'assistance technique fourni.
- **Documentation et Communauté** : Qualité et quantité des ressources disponibles et de la communauté d'utilisateurs.
