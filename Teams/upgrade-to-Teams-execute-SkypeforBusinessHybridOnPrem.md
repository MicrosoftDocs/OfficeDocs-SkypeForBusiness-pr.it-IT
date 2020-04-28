---
title: Aggiornare Skype for Business locale a Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione locale di Skype for business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 491f4132d5f5c4c4e5d8215d0d48277a864cf064
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905218"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Eseguire l'aggiornamento da Skype for business locale a teams

![Aggiornare il diagramma di viaggio, enfatizzando la distribuzione e l'implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

-   [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
-   [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
-   [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Scelto il viaggio di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparare l'organizzazione](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Condotto un pilota](https://aka.ms/SkypeToTeams-Pilot)

Se si è implementato Skype for Business Server o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a teams, seguire le istruzioni in questo articolo. È necessario configurare la connettività ibrida con l'organizzazione di Office 365 e determinare i requisiti di coesistenza se si stanno spostando gli utenti in teams in fasi. 

> [!IMPORTANT]
> Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams. Tieni presente che un aggiornamento corretto allinea la disponibilità tecnica e degli utenti, quindi assicurati di sfruttare le linee guida qui mentre navighi in Microsoft teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Passaggio 1: configurare la connettività ibrida 

Il presupposto chiave per l'aggiornamento degli utenti locali ai team è la configurazione della connettività ibrida per la distribuzione locale di Skype for Business Server. 

Iniziare leggendo il [piano di connettività ibrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e quindi seguire le attività descritte in [configurare la connettività ibrida](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Passaggio 2: impostare la modalità di coesistenza transitoria (facoltativo)

La coesistenza e l'interoperabilità tra i client e gli utenti di Skype for business e teams sono definiti dalle modalità di aggiornamento dei team.  Per impostazione predefinita, le organizzazioni sono in modalità isole, che consente agli utenti di usare entrambi i team e i client Skype for business affiancati.

Per un'organizzazione che si sposta in teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati TeamsOnly (o qualsiasi altra modalità) allo stesso tempo.

Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono facoltativamente usare una qualsiasi delle modalità di coesistenza di Skype for business per garantire una comunicazione prevedibile tra gli utenti che si trovano in modalità TeamsOnly e gli utenti che non sono ancora stati.  Lo scopo delle modalità di coesistenza di Skype for business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è quello di creare un'esperienza semplice e prevedibile per gli utenti finali come organizzazioni di transizione da Skype for business a teams. 

Quando un utente si trova in una delle modalità Skype for business, tutte le chat in arrivo e le chiamate vengono instradate al client Skype for business dell'utente. Per evitare confusione per gli utenti finali e garantire un corretto routing, le funzionalità di chiamata e chat nel client teams vengono disabilitate quando un utente si trova in una delle modalità Skype for business. Analogamente, la pianificazione delle riunioni in teams viene disabilitata esplicitamente quando gli utenti si trovano nelle modalità SfBOnly o SfBWithTeamsCollab e abilitata esplicitamente quando un utente si trova in modalità SfBWithTeamsCollabAndMeetings.

A seconda dei requisiti, è possibile assegnare la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, Vedi [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) e per [impostare le impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Passaggio 3: trasferire gli utenti da Skype for business locale a teams only

In definitiva, vorrai trasferire gli utenti in modalità TeamsOnly. Questo potrebbe includere uno o due passaggi a seconda dell'ambiente locale corrente.  

Per altre informazioni, vedere [trasferire gli utenti tra locale e il cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) e [trasferire gli utenti da locale a teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 



## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di sistema telefonico e teams

Se si sta passando la distribuzione di Skype for business al sistema telefonico con i piani di chiamata, Microsoft sarà il provider PSTN (Public Switched Telephone Network). Supponendo che tu abbia completato la portabilità del numero di telefono, l'aggiornamento degli utenti a teams eseguirà automaticamente la transizione delle chiamate PSTN in ingresso ai team.

Se si sta eseguendo la transizione alla distribuzione di Skype for business al sistema telefonico, ma non si usano i piani di chiamata, è necessario eseguire la transizione della distribuzione vocale aziendale al routing diretto di Microsoft Phone System. Per altre informazioni, Vedi [routing diretto del sistema telefonico](direct-routing-landing-page.md).
