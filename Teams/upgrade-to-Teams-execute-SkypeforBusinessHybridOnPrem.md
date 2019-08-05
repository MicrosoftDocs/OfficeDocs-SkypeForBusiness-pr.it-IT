---
title: Eseguire l'aggiornamento a teams da una distribuzione ibrida o locale di Skype for Business-Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerazioni per l'aggiornamento a teams da una distribuzione ibrida o locale di Skype for business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 731a6b30fe2476d180198e88f83e80f24c8e8227
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "36185218"
---
![Aggiornare il diagramma di viaggio, enfatizzando la distribuzione e l'implementazione] (media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

-   [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
-   [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
-   [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Scelto il viaggio di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparare l'organizzazione](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Condotto un pilota](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Eseguire l'aggiornamento a teams da una distribuzione ibrida o locale di Skype for business

Seguire le indicazioni di questo articolo se si è distribuito Skype for business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a team in modo selettivo, usando più modalità di coesistenza o all-in. Il primo passaggio consiste nel configurare la connettività ibrida con il tenant di Office 365 e quindi trasferire gli utenti a Skype for business online e assegnare loro la modalità di coesistenza e aggiornamento appropriata. 

> [!IMPORTANT]
> Skype for business online verrà ritirato il 31 luglio 2021, dopodiché non sarà più accessibile o supportato. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti invitiamo a iniziare subito il tuo viaggio in Microsoft teams. Tieni presente che un aggiornamento corretto allinea la disponibilità tecnica e degli utenti, quindi assicurati di sfruttare le linee guida qui mentre navighi in Microsoft teams.

## <a name="step-1-deploy-hybrid-connectivity"></a>Passaggio 1: distribuire la connettività ibrida 

Il presupposto chiave per aggiornare gli utenti ai team consiste nel distribuire la connettività ibrida. Questo potrebbe comportare la distribuzione di una nuova connettività esterna per la distribuzione di Skype for business o Lync esistente oppure semplicemente la configurazione di una relazione ibrida con il tenant di Office 365. 

Per altre informazioni, Vedi [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Passaggio 2: trasferire gli utenti in Skype for business online 

Dopo aver completato la configurazione ibrida, sposta gli utenti in Skype for business online. 

Per altre informazioni, vedere [trasferire utenti da locali a Skype for business online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Passaggio 3: assegnare una modalità di coesistenza e aggiornamento

Dopo aver spostato gli utenti in Skype for business online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: gestione della migrazione e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)della coesistenza.

> [!NOTE]
> Con Skype for Business Server 2019 e un futuro aggiornamento cumulativo di Skype for Business Server 2015, è possibile eseguire il passaggio 2 (spostamento degli utenti in Skype for business online) e il passaggio 3 (aggiornare gli utenti ai team) in un unico passaggio. Altre informazioni verranno fornite dopo il rilascio di Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di sistema telefonico e teams

Se si sta eseguendo la transizione della distribuzione ibrida di Skype for business al sistema telefonico con i piani per le chiamate e Microsoft sarà il provider PSTN (Public Switched Telephone Network) e supponendo di aver completato la portabilità del numero di telefono, aggiornare gli utenti a I team eseguiranno automaticamente la transizione delle chiamate PSTN in ingresso ai team.

Se i piani per le chiamate non sono disponibili, è necessario eseguire la transizione della distribuzione vocale aziendale al routing diretto di Microsoft Phone System. Per aggiornare gli utenti a teams, vedere le [considerazioni aggiuntive per il routing diretto del sistema telefonico](2-envision-make-my-service-decisions-direct-routing.md).
