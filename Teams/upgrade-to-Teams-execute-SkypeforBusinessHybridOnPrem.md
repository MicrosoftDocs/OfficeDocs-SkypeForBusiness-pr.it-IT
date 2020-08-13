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
ms.openlocfilehash: 1981640ab06d00e7895e11c0e15adf7555577908
ms.sourcegitcommit: b23d3d583910aa21a62ea69b554ab614c1ae8079
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648607"
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

Se si è implementato Skype for Business Server o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a teams, seguire le istruzioni in questo articolo. È necessario configurare la connettività ibrida con l'organizzazione Microsoft 365 o Office 365 e determinare i requisiti di coesistenza se si stanno spostando gli utenti in teams in fasi. 

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

In definitiva, vorrai trasferire gli utenti in modalità TeamsOnly. Questo può includere una o due fasi a seconda dell'ambiente locale.  

Per altre informazioni, vedere [trasferire gli utenti tra locale e il cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) e [trasferire gli utenti da locale a teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Passaggio 4: disabilitare l'ibrido per completare la migrazione al cloud

Dopo aver spostato tutti gli utenti dal locale al cloud, è possibile rimuovere la Commissione dalla distribuzione di Skype for business locale. Per altre informazioni, vedere [disabilitare l'ibrido per completare la migrazione al cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).


## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema telefonico e opzioni di connettività PSTN

Il sistema telefonico con teams è supportato dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità isole, il sistema telefonico è supportato solo con Skype for business. 

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si considerano le opzioni di connettività PSTN (Public Switched Telephone Network), esistono due scenari possibili quando si passa da Skype for business in locale alla modalità TeamsOnly:

- Un utente in Skype for business locale con Enterprise Voice, che si sposterà in online e userà un piano di chiamata Microsoft. La migrazione di questo utente a teams richiede lo spostamento dell'account Skype for business locale dell'utente nel cloud e il coordinamento di tale spostamento con una a) la porta del numero di telefono di tale utente in un piano di chiamata Microsoft o B) che assegna un nuovo numero di abbonato dalle aree disponibili.  Per altre informazioni, vedere [da Skype for Business Server locale, con Enterprise Voice, al piano per le chiamate Microsoft](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Un utente in Skype for business locale con Enterprise Voice, che si sposterà in online e continuerà a mantenere la connettività PSTN locale. La migrazione di questo utente a teams richiede lo spostamento dell'account Skype for business locale dell'utente nel cloud e il coordinamento di tale spostamento con la migrazione dell'utente al routing diretto. Per altre informazioni, vedere [da Skype for Business Server locale, con VoIP aziendale, per indirizzare il routing](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).
