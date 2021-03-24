---
title: Aggiornare la distribuzione ibrida di Skype for Business a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Scopri come aggiornare la tua organizzazione a Microsoft Teams da una distribuzione ibrida di Skype for Business.
localization_priority: Normal
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104022"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Eseguire l'aggiornamento da una distribuzione ibrida di Skype for Business a Teams

![Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)
- [Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)
- [Ha condotto un progetto pilota](./pilot-essentials.md)

Seguire le istruzioni di questo articolo se Skype for Business o Microsoft Lync è stato distribuito in locale e configurato in una distribuzione ibrida con l'organizzazione di Microsoft 365 o Office 365 e l'organizzazione vuole eseguire l'aggiornamento a Teams in modo selettivo, usando più modalità di coesistenza o all-in. Per entrambi i percorsi di aggiornamento, è necessario spostare gli utenti in Skype for Business online (se non sono già ospitati online) e quindi assegnare loro la modalità di coesistenza e aggiornamento appropriata.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Passaggio 1: Spostare gli utenti in Skype for Business online

Questo passaggio si applica agli utenti attualmente ospitati in locale. Per altre informazioni sullo spostamento di questi utenti in Skype for Business online, vedere Spostare gli utenti da locale a [Skype for Business online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Passaggio 2: Assegnare una modalità di coesistenza e aggiornamento

Dopo aver spostato gli utenti in Skype for Business online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere Impostazione delle impostazioni di [coesistenza](./setting-your-coexistence-and-upgrade-settings.md) e aggiornamento e [TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> Con Skype for Business Server 2019 e un aggiornamento cumulativo futuro di Skype for Business Server 2015, sarà possibile eseguire i passaggi 1 (spostamento degli utenti in Skype for Business online) e Passaggio 2 (aggiornare gli utenti a Teams) in un unico passaggio. Ulteriori informazioni verranno fornite dopo il rilascio di Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di Sistema telefonico e Teams

Se stai eseguendo la transizione della distribuzione ibrida di Skype for Business a Sistema telefonico con piani per chiamate e Microsoft sarà il tuo provider di rete PSTN (Public Switched Telephone Network) e presupponendo che tu abbia completato la portabilità del numero di telefono, l'aggiornamento degli utenti a Teams esegue automaticamente la transizione delle chiamate PSTN in ingresso a Teams.

Se Piani di chiamata non è disponibile o si prevede di usare il provider di connettività PSTN esistente, è necessario eseguire la transizione della distribuzione voIP aziendale, o della distribuzione vocale ibrida che usa la distribuzione locale esistente o Cloud Connector Edition, a Microsoft Phone System Direct Routing. Per aggiornare gli utenti a Teams, vedere le [considerazioni aggiuntive su Phone System Direct Routing](./direct-routing-landing-page.md).