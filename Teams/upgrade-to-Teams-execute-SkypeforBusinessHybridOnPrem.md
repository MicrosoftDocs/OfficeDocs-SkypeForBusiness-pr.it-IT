---
title: Aggiornare Skype for Business locale a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Scopri come aggiornare la tua organizzazione a Microsoft Teams da una distribuzione locale di Skype for Business.
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
ms.openlocfilehash: 961ac4f9bcce3c24d62ec1c744d2c9cd15e2ee1b
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578169"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Eseguire l'aggiornamento da Skype for Business locale a Teams

![Diagramma percorso di aggiornamento, enfatizzando distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

-   [Integrare gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
-   [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
-   [Coesistenza e interoperabilità comprensibili di Skype for Business e Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Organizzazione preparata](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Ha diretto un pilota](https://aka.ms/SkypeToTeams-Pilot)

Se è stato distribuito Skype for Business Server o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Teams, seguire le indicazioni in questo articolo. È necessario configurare la connettività ibrida con l'organizzazione di Microsoft 365 o Office 365 e determinare i requisiti di coesistenza se si spostano gli utenti in Teams in fasi. 

> [!IMPORTANT]
> Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato. Per ottimizzare la realizzazione dei vantaggi e garantire alla tua organizzazione il tempo necessario per implementare il tuo aggiornamento, ti consigliamo di iniziare oggi stesso il tuo percorso verso Microsoft Teams. Ricorda che un aggiornamento riuscito allinea la preparazione tecnica e quella degli utenti, quindi assicurati di avvalerti delle indicazioni riportate qui mentre ti snavigare verso Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Passaggio 1: Configurare la connettività ibrida 

Il prerequisito principale per l'aggiornamento degli utenti locali a Teams è la configurazione della connettività ibrida per la distribuzione locale di Skype for Business Server. 

Per iniziare, [vedere Pianificare la connettività](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) ibrida e quindi seguire le attività descritte in [Configurare la connettività ibrida.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Passaggio 2: Impostare la modalità di coesistenza di transizione (facoltativo)

La coesistenza e l'interoperabilità tra client e utenti di Skype for Business e Teams sono definite dalle modalità di aggiornamento di Teams.  Per impostazione predefinita, le organizzazioni sono in modalità Isole, che consente agli utenti di usare client Teams e Skype for Business affiancati.

Per un'organizzazione che sta passando a Teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non è necessario assegnare TeamsOnly a tutti gli utenti (o qualsiasi altra modalità) contemporaneamente.

Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono utilizzare facoltativamente una delle modalità di coesistenza di Skype for Business per garantire una comunicazione prevedibile tra gli utenti in modalità TeamsOnly e gli utenti che non lo sono ancora.  Lo scopo delle modalità di coesistenza di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è fornire un'esperienza semplice e prevedibile per gli utenti finali quando le organizzazioni passano da Skype for Business a Teams. 

Quando un utente è in una delle modalità Skype for Business, tutte le chat e le chiamate in arrivo vengono indirizzate al client Skype for Business dell'utente. Per evitare confusione con l'utente finale e garantire una corretta funzionalità di routing, chiamata e chat nel client Teams viene disabilitata quando un utente è in una delle modalità di Skype for Business. Analogamente, la pianificazione delle riunioni in Teams viene esplicitamente disabilitata quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e esplicitamente abilitata quando un utente è in modalità SfBWithTeamsCollabAndMeetings.

A seconda dei requisiti, è possibile assegnare la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per ulteriori informazioni, consulta Indicazioni sulla migrazione e [l'interoperabilità](migration-interop-guidance-for-teams-with-skype.md) per le organizzazioni che usano Teams insieme a Skype for Business e come impostare le impostazioni di [coesistenza e aggiornamento.](https://aka.ms/SkypeToTeams-SetCoexistence)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Passaggio 3: Spostare gli utenti dalla distribuzione locale di Skype for Business a Teams

In ultima analisi, è necessario spostare gli utenti in modalità TeamsOnly. Questa operazione può richiedere uno o due passaggi a seconda dell'ambiente locale.  

Per altre informazioni, vedere Spostare gli utenti tra l'ambiente locale e il [cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) e Spostare gli utenti dalla [distribuzione locale a Teams.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Passaggio 4: Disabilitare la distribuzione ibrida per completare la migrazione al cloud

Dopo aver spostato tutti gli utenti dalla distribuzione locale al cloud, è possibile rimuovere la distribuzione locale di Skype for Business. Per altre informazioni, vedere [Disabilitare la distribuzione ibrida per completare la migrazione al cloud.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Opzioni di connettività Sistema telefonico e PSTN

Sistema telefonico con Teams è supportato dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità Isole, il Sistema telefonico è supportato solo con Skype for Business. 

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si valutano le opzioni di connettività PSTN (Public Switched Telephone Network), ci sono due possibili scenari per il passaggio dalla modalità locale di Skype for Business alla modalità TeamsOnly:

- Un utente in Skype for Business locale con VoIP aziendale, che si locerà online e utilizzando un piano per le chiamate Microsoft. La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento del trasferimento con A) il trasferimento del numero di telefono dell'utente a un piano per chiamate Microsoft o B) l'assegnazione di un nuovo numero di abbonato dalle aree geografiche disponibili.  Per ulteriori informazioni, consulta Da Skype for Business Server locale, con [VoIP aziendale, al Piano per chiamate Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Un utente in Skype for Business locale con VoIP aziendale, che si locerà online mantenendo la connettività PSTN locale. La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento del trasferimento con la migrazione dell'utente al routing diretto. Per ulteriori informazioni, consulta Da Skype for Business Server locale, con [VoIP aziendale, al routing diretto.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)
