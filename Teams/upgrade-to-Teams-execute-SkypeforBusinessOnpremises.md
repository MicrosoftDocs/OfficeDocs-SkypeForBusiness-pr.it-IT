---
title: Aggiornare Skype for Business locale a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come eseguire la transizione dell'organizzazione a Microsoft Teams da una distribuzione locale di Skype for Business.
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820946"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Eseguire l'aggiornamento da una distribuzione locale di Skype for Business a Teams

![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Integrare gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità comprensibili di Skype for Business e Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Organizzazione preparata](https://aka.ms/SkypeToTeams-UserReadiness)
- [Ha diretto un pilota](https://aka.ms/SkypeToTeams-Pilot)

Seguire le indicazioni in questo articolo se è stato distribuito Skype for Business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft Teams in modo selettivo, utilizzando più modalità di coesistenza, o all-in. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Passaggio 1: Distribuire la connettività ibrida

Il prerequisito fondamentale per l'aggiornamento degli utenti a Teams è la distribuzione della connettività ibrida.

Per ulteriori informazioni, consulta [Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Passaggio 2: Implementare il percorso di aggiornamento scelto per l'organizzazione

Dopo aver completato la configurazione ibrida, è possibile pianificare lo spostamento degli utenti in Microsoft 365 o Office 365.

Per ulteriori informazioni, vedere:

- [TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)

- [Spostare gli utenti dalla distribuzione locale a Skype for Business online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di Sistema telefonico e Teams

La transizione dai sistemi telefonici locali a Teams ti consentirà di sfruttare l'instradamento diretto del sistema telefonico ("Routing diretto") o dei Piani per chiamate forniti da Microsoft per Microsoft 365 o Office 365.

Se non si usano i Piani per chiamate, è necessario eseguire la transizione della distribuzione voIP aziendale all'instradamento diretto del sistema telefonico nell'ambito dell'aggiornamento a Teams.

Per ulteriori informazioni, consulta [ulteriori considerazioni sull'instradamento diretto del sistema telefonico.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing) Se stai pianificando di utilizzare i Piani per chiamate, consulta le nostre indicazioni per il trasferimento dei numeri [di telefono in Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)