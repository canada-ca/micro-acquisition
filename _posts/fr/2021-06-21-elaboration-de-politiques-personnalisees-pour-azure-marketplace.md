---
layout: post
title: Élaboration de politiques personnalisées pour Azure marketplace  
ref: opportunity1
lang: fr
skills:  Azure Policies et Azure Runbooks (via Powershell)
value: 6 500$ (hors les taxes)
closing_date: 2021-07-05T23:59:59-04:00
start_date: 2021-07-09
delivery_date: 2021-07-16T23:59:59-04:00
selected_bidder:
selected_bidder-link:
submitted_work-link:
last_modified: 2021-06-21
short_desc: "Élaborer des scripts pour établir automatiquement des politiques dans Azure Marketplace/Private Marketplace (marché Azure, marché privé) qui régiront les offres de tierces parties qui seront utilisées par les clients d’EDSC."
---

## Description

### Contexte

L’équipe administrative des Opérations infonuagiques d’EDSC demande le travail lié à cette possibilité.  

Les technologies infonuagiques facilitent la transformation au sein du gouvernement et améliorent la prestation des services aux Canadiens.
Dans le cadre du déploiement de infonuagiques à EDSC, un certain nombre d’instances Azure sont utilisées à EDSC.

Ces instances utilisent un [modèle de type en étoile](hhttps://docs.microsoft.com/fr-ca/azure/architecture/reference-architectures/hybrid-networking/hub-spoke?tabs=cli){:target="_blank"} (Hub and Spoke) pour regrouper les services communs essentiels à tous les déploiements de nuages.
Le carrefour (hub) représente un ensemble de services communs qui offrent des capacités pour les rayons.

Chaque client Azure à EDSC est identifié de façon unique par un abonnement Azure ou un groupe de ressources.
Au début, le rayon (spoke) a été mis en œuvre comme groupe de ressources, mais il est maintenant modifié pour utiliser les groupes de gestion et les abonnements comme pratiques exemplaires de l’industrie.
Les clients d’EDSC sur les instances Azure peuvent utiliser les offres des premières et de tierces parties d’Azure Marketplace (le marché Azur).
L’utilisation de ces offres, tout comme l’utilisation d’instances Azure, est gérée centralement à EDSC en collaboration avec d’autres organismes gouvernementaux pour simplifier l’administration et à des fins de sécurité.

La plupart des offres de première partie du marché sont approuvées par défaut et les clients d’EDSC peuvent les utiliser sans autre approbation.
Les offres de tierces parties doivent être approuvées par l’administrateur et les organismes gouvernementaux externes à EDSC avant d’être ajoutées au marché privé d’EDSC.
À l’heure actuelle, 45 offres de tierces parties ont été approuvées dans le cadre de ce processus à l’intention des clients Azure d’EDSC.
Parmi les offres approuvées par des tierces parties, mentionnons SendGrid, Fortinet FortiGate Next-Generation Firewall, Cisco Cloud Services Router (CSR) 1000V, CIS Ubuntu Linux 18.04 LTS Benchmark L1, etc.
Voici un échantillon des offres de tierces parties qui n’ont pas été approuvées (et qui n’apparaissent pas sur le marché privé d’EDSC) : VIAcode Managed Services for Azure, Nasuni Cloud File Services (NMC), Sycomp Storage Fueled de IBM Spectrum Scale, etc.

Si un client Azure d’EDSC souhaite utiliser une offre de tierce partie qui n’est pas encore approuvée (et donc pas sur le marché privé), le client peut demander qu’elle soit ajoutée.
Cela signifie que la liste des offres de tierces parties approuvées sur le marché privé changera au fil du temps.
Si une offre de tierce partie est approuvée pour un client d’EDSC, elle peut être achetée par tous les clients d’EDSC – tout le monde voit le même marché privé.

Si un client Azure d’EDSC souhaite utiliser une offre de tierce partie sur le marché privé qui porte une mention « Le prix commence à  » > 0,00 $, il doit demander l’approbation financière des fonds pour acheter cette offre de tierce partie.
Une fois qu’un client d’EDSC a obtenu l’approbation financière pour acheter l’offre de la tierce partie, une communication est envoyée par le client à l’équipe des opérations de l’informatique en nuage avec le nom de l’offre de la tierce partie.
(Remarque : Cette communication est hors du champ d’application de cette opportunité.)

Ce processus de financement nous amène au problème que nous devons résoudre et avons besoin d’aide pour le faire.
Bien que des politiques intégrées existent dans Azure, aucune politique n’empêche les clients d’installer des offres de tierces parties une fois qu’elles ont été incluses dans les offres de marché privé.

### Le travail

Pour répondre à cette opportunité, vous devez fournir :

1. un script (ou des scripts) écrit dans PowerShell qui permet :
   - de créer un fichier JSON pour mettre en œuvre une politique personnalisée Azure laquelle empêchera tous les clients d’Azure d’EDSC d’installer n’importe quelle offre de tierce partie du marché (y compris le marché privé) dont le prix commence à > 0,00 $/h.  
   - d’activer un filtre pour déterminer les offres autorisées ou refusées par l’éditeur, l’offre et le plan. Le filtre devrait permettre des caractères génériques.
   - S’assurer que seuls les clients qui obtiennent l’autorisation financière d’utiliser une offre approuvée (sur le marché privé) peuvent installer cette offre.
   - Empêcher un client ayant un abonnement qui n’a pas l’autorisation financière d’utiliser une offre de tierce partie approuvée d’installer une telle offre. Si le client tente d’installer l’offre, il devrait recevoir le message suivant en anglais ou en français selon la langue de son interface utilisateur.
     - Message en français « Vous devez obtenir l’approbation financière pour utiliser cette offre du marché Azure avant de pouvoir l’installer. »
     - Message en anglais : " You must seek financial approval to use this Azure Marketplace offering before you can install it."
2. Documentation (commentaires en ligne et document distinct) sur ce que vous fournissez et son fonctionnement. Assurez-vous que votre documentation ou vos commentaires décrivent la logique ou les règles opérationnelles utilisées par votre script ou section d’un script. De plus, veuillez utiliser des noms de variable descriptifs et insérer des espaces entre de grands blocs de commentaires.

<hr/>

## Évaluation de la demande

Votre demande sera évaluée en fonction des critères suivants :

1. Confirmez que vous possédez les compétences nécessaires pour effectuer ce travail. Veuillez fournir une courte déclaration écrite (250 mots ou moins, une demi-page) démontrant que vous possédez les compétences requises relativement à Azure Policies et Azure Runbooks (via Powershell). Précisez quand vous avez acquis ces compétences, ce que vous avez fait et comment vous l’avez fait. Exemples : expérience de travail antérieure, travaux scolaires, projets Civic Tech, etc.

Vous devrez également confirmer que vous répondez aux critères d’admissibilité suivants :

- vous avez atteint l’âge de la majorité et avez la capacité de contracter
  
ET

- vous êtes canadien, membre des Premières Nations, Métis ou Inuit

OR

- vous êtes travailleur étranger et avez [les permis de travail](https://www.canada.ca/fr/immigration-refugies-citoyennete/services/travailler-canada/permis.html){:target="_blank"} appropriés pour travailler au Canada.

## Critères d'acceptation de travail

Il s’agit d’une opportunité à prix fixe régie par les modalités du projet pilote de micro-acquisition. Pour recevoir le prix fixe, vous devez :

1. Fournir un code source qui satisfait à toutes les exigences de la description de l’opportunité ci-dessus. De plus :

   - Le code doit être livré avec une licence MIT.
   - Le code doit passer les tests automatisés suivants :
     - [PowerShell Script Analyzer (analyseur de script)](https://github.com/PowerShell/PSScriptAnalyzer){:target="_blank"} – toutes les règles par défaut (tous les avertissements, alertes et suppressions de ces avertissements ou alertes dans le code doivent être inclus dans la documentation avec une justification)
     - Le fournisseur retenu aura accès à un bac à sable non sécurisé sur Azure afin d’effectuer les essais fonctionnels suivants pour s’assurer que les scripts fonctionnent :
       - Un client ayant un abonnement qui a obtenu une approbation financière pour une offre de tierce partie approuvée : « CIS Microsoft Windows Server 2016 Benchmark L1 » sur le marché privé obtient la validation et peut procéder à l’installation.
       - Un client dont l’abonnement n’a PAS d’approbation financière pour l’offre d’une tierce partie approuvée « CIS Microsoft Windows Server 2016 Benchmark L2 » sur le marché privé échouera à la validation lorsqu’il tentera d’installer cette offre d’une tierce partie approuvée.
       - Un client ayant un abonnement qui a obtenu une approbation financière pour une offre de tierce partie approuvée : « CIS Microsoft Windows Server 2008 R2 Benchmark L1 » sur le marché privé ne peut pas obtenir la validation pour installer une offre de tierce partie approuvée : « Serveur RPV sécurisé », car il n’a pas d’approbation financière pour cette offre.
       - Un client ayant un abonnement qui n’a pas d’approbation financière pour une offre de tierce partie ne peut obtenir la validation pour installer une offre de tierce partie sur le marché privé.
       - Si l’offre d’une tierce partie est approuvée pour tous les abonnements à Azure d’EDSC et qu’elle est ajoutée au marché privé, les clients ne peuvent tenter d’obtenir la validation tant qu’ils n’ont pas obtenu l’approbation financière.

*Veuillez noter que le bac à sable sera préalablement rempli avec des abonnements et certaines offres sur le marché privé.*
