---
title: Rapport
description: 
published: true
date: 2023-11-12T17:21:01.108Z
tags: 
editor: markdown
dateCreated: 2023-11-12T17:02:12.437Z
---

# Header

```mermaid
  sequenceDiagram
  	participant C as Client
    Participant S as Switch
    Switch->>C: Requête EAP d'identitée
    C->>Switch: Réponse requête EAP d'identitée 
    Switch->>Serveur RADIUS: Requête d'accès RADIUS
    Switch->>Serveur RADIUS: test
    
```