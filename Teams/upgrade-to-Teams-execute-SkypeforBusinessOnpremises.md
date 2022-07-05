---
title: Aggiornare Skype for Business locale a Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come eseguire la transizione dell'organizzazione a Microsoft Teams da una distribuzione locale Skype for Business.
ms.localizationpriority: medium
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
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615442"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Eseguire l'aggiornamento da una distribuzione Skype for Business locale a Teams

![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione.](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Ha raggruppato gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definito l'ambito del progetto](./upgrade-define-project-scope.md)
- [Coesistenza e interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Scelta del percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)
- [Ha condotto un progetto pilota](./pilot-essentials.md)

Seguire le indicazioni in questo articolo se si è distribuito Skype for Business o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Microsoft Teams in modo selettivo, usando più modalità di coesistenza, o all-in. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Passaggio 1: Distribuire la connettività ibrida

Il prerequisito fondamentale per aggiornare gli utenti a Teams è distribuire la connettività ibrida.

Per altre informazioni, vedere [Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Passaggio 2: Implementare il percorso di aggiornamento scelto per l'organizzazione

Dopo aver completato la configurazione ibrida, è possibile pianificare lo spostamento degli utenti in Microsoft 365 o Office 365.

Per ulteriori informazioni, vedere:

- [TeamsUpgradePolicy: gestione della migrazione e della coesistenza](upgrade-to-teams-on-prem-tools.md).

- [Spostare gli utenti da locale a Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di Sistema telefonico e Teams

La transizione da sistemi telefonici locali a Teams ti consentirà di sfruttare il routing diretto del sistema telefonico ("Routing diretto") o i Piani per chiamate forniti da Microsoft per Microsoft 365 o Office 365.

Se non usi i Piani per chiamate, devi passare la distribuzione voIP aziendale al Routing diretto del sistema telefonico nell'ambito dell'aggiornamento a Teams.

Per ulteriori informazioni, vedi [considerazioni aggiuntive per il routing diretto del sistema telefonico](./direct-routing-landing-page.md). Se prevedi di utilizzare i Piani per chiamate, consulta le nostre indicazioni per [il trasferimento dei numeri di telefono in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).