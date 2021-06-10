---
title: Aggiornare Skype for Business locale a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come eseguire la transizione dell'organizzazione a Microsoft Teams da una distribuzione Skype for Business locale.
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115554"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Eseguire l'aggiornamento da Skype for Business distribuzione locale a Teams

![Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)
- [Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)
- [Ha condotto un progetto pilota](./pilot-essentials.md)

Seguire le indicazioni di questo articolo se è stato distribuito Skype for Business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft Teams in modo selettivo, usando più modalità di coesistenza o all-in. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Passaggio 1: Distribuire la connettività ibrida

Il prerequisito fondamentale per l'aggiornamento degli utenti a Teams è la distribuzione della connettività ibrida.

Per altre informazioni, vedere [Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Passaggio 2: Implementare il percorso di aggiornamento scelto per l'organizzazione

Dopo aver completato la configurazione ibrida, è possibile pianificare lo spostamento degli utenti in Microsoft 365 o Office 365.

Per ulteriori informazioni, vedere:

- [TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)

- [Spostare gli utenti da locale a Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Sistema telefonico e Teams aggiornamento

La transizione dai sistemi telefonici locali a Teams consente di sfruttare Sistema telefonico Direct Routing ("Direct Routing") o i Piani per le chiamate forniti da Microsoft per Microsoft 365 o Office 365.

Se non si usa Piani per chiamate, è necessario eseguire la transizione della distribuzione voIP aziendale a Sistema telefonico Routing diretto nell'ambito dell'aggiornamento a Teams.

Per altre informazioni, vedere [considerazioni aggiuntive per Sistema telefonico routing diretto](./direct-routing-landing-page.md). Se stai pianificando di usare Piani per chiamate, consulta le nostre indicazioni per trasferire i tuoi numeri di telefono a [Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).