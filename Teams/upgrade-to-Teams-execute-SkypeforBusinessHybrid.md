---
title: Aggiornare Skype for Business distribuzione ibrida a Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione ibrida Skype for Business.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615602"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Eseguire l'aggiornamento da una distribuzione ibrida Skype for Business a Teams

![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione.](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Ha raggruppato gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definito l'ambito del progetto](./upgrade-define-project-scope.md)
- [Coesistenza e interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Scelta del percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)
- [Ha condotto un progetto pilota](./pilot-essentials.md)

Seguire le indicazioni in questo articolo se è stato distribuito Skype for Business o Microsoft Lync locale e configurato in una distribuzione ibrida con Microsoft 365 o Office 365 organizzazione e l'organizzazione vuole eseguire l'aggiornamento a Teams in modo selettivo, usando più modalità di coesistenza, o all-in. Per entrambi i percorsi di aggiornamento, è necessario spostare gli utenti in Skype for Business Online (se non sono già ospitati online) e quindi assegnare loro la coesistenza e la modalità di aggiornamento appropriate.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Passaggio 1: Spostare gli utenti in Skype for Business Online

Questo passaggio si applica agli utenti attualmente ospitati in locale. Per altre informazioni sullo spostamento di questi utenti in Skype for Business Online, vedere [Spostare gli utenti da locale a Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Passaggio 2: Assegnare una modalità di coesistenza e aggiornamento

Dopo aver spostato gli utenti in Skype for Business Online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere [Impostazione delle impostazioni di coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md) e [TeamsUpgradePolicy: gestione della migrazione e coesistenza](upgrade-to-teams-on-prem-tools.md).

> [!NOTE]
> Con Skype for Business Server 2019 e un aggiornamento cumulativo futuro di Skype for Business Server 2015, sarà possibile eseguire il passaggio 1 (spostare gli utenti a Skype for Business online) e il passaggio 2 (aggiornare gli utenti a Teams) in un unico passaggio. Altre informazioni verranno fornite dopo il rilascio di Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di Sistema telefonico e Teams

Se stai eseguendo la transizione della distribuzione ibrida Skype for Business a Sistema telefonico con Piani per chiamate e Microsoft sarà il tuo provider PSTN (Public Switched Telephone Network) e supponendo di aver completato la portabilità del numero di telefono, l'aggiornamento degli utenti a Teams eseguirà automaticamente la transizione delle chiamate PSTN in ingresso a Teams.

Se Piani per chiamate non è disponibile o si intende utilizzare il provider di connettività PSTN esistente, è necessario eseguire la transizione della distribuzione voIP aziendale, o della distribuzione vocale ibrida che usa la distribuzione locale esistente o Cloud Connector Edition, a Microsoft Phone System Direct Routing. Per aggiornare gli utenti a Teams, vedere le [considerazioni aggiuntive per il routing diretto del sistema telefonico](./direct-routing-landing-page.md).