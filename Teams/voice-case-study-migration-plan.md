---
title: Teams piano di aggiornamento di case study di Contoso vocale
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: "Teams case study vocale per società multinazionali: pianificazione dell'aggiornamento."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39cfd66f0ff34fb0f8792871ddfdcceebb2b9961
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822985"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Case study contoso: piano di aggiornamento Teams

Nella decisione di eseguire la migrazione da Skype for Business a Teams, Contoso voleva offrire un'esperienza di transizione semplice per gli utenti finali. Invece di consentire a tutti di Teams contemporaneamente, hanno deciso di configurare la connettività ibrida e di usare il metodo delle funzionalità sovrapposte per spostare gli utenti in Teams. Ciò ha consentito agli utenti in Teams e Skype for Business locale di condividere la presenza e comunicare. Quando gli utenti sono entrati nel progetto pilota per Sistema telefonico, sono stati spostati nella modalità solo Teams.

Per comprendere i concetti fondamentali sull'aggiornamento, i metodi e le modalità, Contoso legge gli articoli seguenti:

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Strategie di aggiornamento per gli amministratori IT](upgrade-to-teams-on-prem-implement.md) 
- [Linee guida per la migrazione e l'interoperabilità](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso ha partecipato anche alla sessione di progettazione del percorso di Ignite 2019 [da Skype for Business a Teams](https://myignite.microsoft.com/archives/IG20-OD251). Contoso ha appreso quanto:

- Concetti fondamentali come interoperabilità, federazione e comportamento di aggiornamento 

- Modalità di coesistenza e gestione basate su TeamsUpgradePolicy 

- Esperienza utente finale per: 

  - Chat e chiamate 

  - Pianificazione delle riunioni 

  - Disponibilità delle funzionalità di collaborazione nei client Teams 

Per pianificare e configurare la connettività ibrida, il primo passaggio per spostare l'ambiente locale nel cloud, Contoso legge [Pianificare la connettività ibrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) e [Configurare la connettività ibrida](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) per informazioni su come: 

  - Configurare il servizio di ambiente locale per la federazione con Office 365. 

  - Configurare l'ambiente locale in modo che consideri attendibile Office 365 e abiliti lo spazio degli indirizzi SIP condiviso con Office 365 

  - Abilitare lo spazio di indirizzi SIP condiviso nel tenant di Office 365.

  - Usare la modalità Isole durante il progetto pilota tecnico.

  - Passare alla modalità TeamsOnly dopo che l'utente è abilitato per Sistema telefonico. La modalità TeamsOnly è necessaria per il piano per chiamate e il routing diretto.
