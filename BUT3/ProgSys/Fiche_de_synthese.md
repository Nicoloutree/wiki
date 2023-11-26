---
title: Fiche de synthèse
description: 
published: true
date: 2023-11-26T10:08:03.325Z
tags: but3, adds, windows server, prog sys
editor: markdown
dateCreated: 2023-11-26T09:42:20.971Z
---

# Fiche de synthèse ADDS

##  Installation création et gestion de l'ADDS (Windows server)

### Installation

Installer les rôles et fonctionnalités nécessaires pour créer un contrôleur de domaine:

```Powershell
Install-WindowsFeature -Name AD-Domain-Services -IncludeManagementTools
```

Vérifier que le rôle AD-Domain-Services est bien installé :

```Powershell
Get-WindowsFeature -Name *AD*
```

Lorsque le rôle est bien installer, il est ensuite possible d'utiliser les cmdlets du module ADDSDeployment pour déployer un nouveau domaine, une forêt ou un contrôleur de domaine supplémentaire.

> Afin de lister les cmdlets du module :
> 
> ```Powershell
> Get-Command -Module ADDSDeployment
> ```
> {.is-info}



## Création et gestion d'utilisateurs

### Création d'un utilisateur

### Suppression d'un utilisateur

## Gestion des ordinateurs coté client