---
title: Aggiornare Skype for Business locale a Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come eseguire la transizione dell'organizzazione a Microsoft Teams da una distribuzione locale di Skype for business.
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
ms.openlocfilehash: 34502fe9883c98179a6b2e23cd8360ae823c1853
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666018"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Eseguire l'aggiornamento da una distribuzione locale di Skype for business a teams

![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)
- [Scelto il viaggio di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparare l'organizzazione](https://aka.ms/SkypeToTeams-UserReadiness)
- [Condotto un pilota](https://aka.ms/SkypeToTeams-Pilot)

Seguire le indicazioni di questo articolo se si è distribuito Skype for business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft teams in modo selettivo, usando più modalità di coesistenza o all-in. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Passaggio 1: distribuire la connettività ibrida

Il presupposto chiave per aggiornare gli utenti ai team consiste nel distribuire la connettività ibrida.

Per altre informazioni, vedere [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Passaggio 2: implementare il viaggio di aggiornamento scelto per l'organizzazione

Dopo aver completato la configurazione ibrida, è possibile pianificare di trasferire gli utenti a Microsoft 365 o Office 365.

Per altre informazioni, vedere:

- [TeamsUpgradePolicy: gestione della migrazione e della coesistenza](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

- [Trasferire utenti da locali a Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di sistema telefonico e teams

La transizione dai sistemi telefonici locali ai team consente di sfruttare il routing diretto del sistema telefonico ("Direct routing") o i piani per le chiamate fornite da Microsoft per Microsoft 365 o Office 365.

Se non si usano i piani di chiamata, è necessario eseguire la transizione della distribuzione di VoIP aziendale al routing diretto del sistema telefonico nell'ambito dell'aggiornamento a teams.

Per altre informazioni, vedere [considerazioni aggiuntive per il routing diretto del sistema telefonico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Se si prevede di usare i piani per le chiamate, vedere le indicazioni per [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).