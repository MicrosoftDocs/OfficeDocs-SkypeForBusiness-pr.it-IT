---
title: Case Study di teams Voice contoso
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
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786018"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Case Study di Contoso: piano di aggiornamento Teams

Nella decisione di eseguire la migrazione da Skype for business a teams, Contoso ha voluto creare un'esperienza di transizione semplice per gli utenti finali. Invece di cambiare tutti i team contemporaneamente, hanno deciso di configurare la connettività ibrida e di usare il metodo di funzionalità sovrapposte per trasferire gli utenti in teams. In questo articolo sono stati consentiti utenti in teams e Skype for business locali per condividere la presenza e comunicare. Quando gli utenti hanno inserito il sistema pilota per telefono, sono stati spostati in modalità solo teams.

Per comprendere i concetti fondamentali sull'aggiornamento, i metodi e le modalità, Contoso ha letto gli articoli seguenti:

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Aggiornamento da Skype for Business a Teams](upgrade-to-teams-on-prem-overview.md) 
- [Linee guida per la migrazione e l'interoperabilità](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso ha partecipato anche alla sessione Ignite 2019 [che ha progettato il percorso da Skype for business a teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions). Contoso ha imparato a conoscere:

- Concetti fondamentali come l'interoperabilità, la Federazione e il comportamento di aggiornamento 

- Modalità di coesistenza e gestione basate su TeamsUpgradePolicy 

- Esperienza utente finale per: 

  - Chat e chiamate 

  - Pianificazione delle riunioni 

  - Disponibilità della funzionalità di collaborazione nei client di Teams 

Per pianificare e configurare la connettività ibrida, il primo passaggio per spostare l'ambiente locale nel cloud, contoso leggere il [piano di connettività ibrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) e [configurare la connettività ibrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) per comprendere come: 

  - Configurare il servizio di ambiente locale per la Federazione con Office 365. 

  - Configurare l'ambiente locale per considerare attendibile Office 365 e abilitare lo spazio di indirizzi SIP condiviso con Office 365 

  - Abilitare lo spazio di indirizzi SIP condiviso nel tenant di Office 365.

  - Usare la modalità isole durante il Pilot tecnico.

  - Passare gli utenti alla modalità TeamsOnly una volta che l'utente è abilitato per il sistema telefonico. La modalità TeamsOnly è necessaria per chiamare il piano e il routing diretto. 
