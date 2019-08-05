---
title: Aggiornare Skype for business locale a Microsoft Teams | Deploy | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerazioni per l'aggiornamento a teams da una distribuzione locale di Skype for business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b41de8f54eb0e2a09e7e3700b25cba1e5564f0a
ms.sourcegitcommit: a47f0841b9a14ede65171a817ecb7ebc72f209e5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "36182239"
---
![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione] (media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)
- [Scelto il viaggio di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparare l'organizzazione](https://aka.ms/SkypeToTeams-UserReadiness)
- [Condotto un pilota](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Eseguire l'aggiornamento da una distribuzione locale di Skype for business a teams

Seguire le indicazioni di questo articolo se si è distribuito Skype for business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft teams in modo selettivo, usando più modalità di coesistenza o all-in. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Passaggio 1: distribuire la connettività ibrida

Il presupposto chiave per aggiornare gli utenti ai team consiste nel distribuire la connettività ibrida.

Per altre informazioni, vedere [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Passaggio 2: implementare il viaggio di aggiornamento scelto per l'organizzazione

Dopo aver completato la configurazione ibrida, è possibile pianificare la migrazione degli utenti a Office 365.

Per altre informazioni, vedere:

- [TeamsUpgradePolicy: gestione della migrazione e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)della coesistenza.

- [Trasferire utenti da locali a Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di sistema telefonico e teams

La transizione dai sistemi telefonici locali ai team consente di sfruttare il routing diretto del sistema telefonico ("Direct routing") o i piani di chiamata forniti da Microsoft per Office 365.

Se non si usano i piani per le chiamate in Office 365, è necessario eseguire la transizione della distribuzione vocale aziendale al routing diretto del sistema telefonico nell'ambito dell'aggiornamento a teams.

Per altre informazioni, vedere [considerazioni aggiuntive per il routing diretto del sistema telefonico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Se si prevede di usare i piani per le chiamate in Office 365, vedere le indicazioni per [trasferire i numeri di telefono in office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).