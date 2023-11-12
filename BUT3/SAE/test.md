---
title: Schéma de séquence 802.1x
description: 
published: true
date: 2023-11-12T18:03:25.157Z
tags: 
editor: markdown
dateCreated: 2023-11-12T17:02:12.437Z
---

# Schéma de séquence 802.1x

Dans notre cas, le client est n'importe quel device qui essaie de se connecter au switch via un cable Ethernet, il s'agit du supplicant (suppliant/demandeur en français). Le switch lui est notre NAS (Network Access Server), les NAS sont tous les composants permettant à un utilisateur de se connecter au réseau, le switch en fait donc partie, un autre exemple serait un point d'accès wifi. En dernier il-y-a le serveur AAA (Authentication, Authorization, Accounting) il se charge de valider ou non l'accès au réseau pour les utilisateurs se connectant, il se charge également de leur attribués les différents accès et il est également capable de faire de la comptabilité i.e. compter le nombre de netdata utilisé par un utilisateur.

Le schéma ci-dessous démarre dès lors qu'un utilisateur se branche en RJ45 sur notre switch Cisco Catalyst 2960 Plus Series.

```mermaid 
  sequenceDiagram
  	participant U as Utilisateur
    Participant S as Switch
    Participant SR as Serveur RADIUS
    S->>U: Requête EAP d'identité
    U->>S: Réponse requête EAP d'identité 
    S->>SR: Requête d'accès RADIUS
    Note over S,SR: Contenant l'identité <br> fournie par le client
    SR->>SR: Vérification de l'identité
    alt identité valide
    	SR->>S: requête d'accès acceptée
      S->>U: requête EAP de réussite
      U-->SR: Port autorisé communication possible
    else identité non valide
    	SR->>S: requête d'accès refusée
      S->>U: requête EAP d'echec
      U-->SR: Port non autorisé communication impossible
    end
    opt déconnexion du client
    U->>S: EAPoL Déconnexion
   	end
```