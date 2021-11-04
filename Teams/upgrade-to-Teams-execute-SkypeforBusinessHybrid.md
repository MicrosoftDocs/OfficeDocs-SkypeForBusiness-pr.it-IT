---
title: Aggiornare Skype for Business distribuzione ibrida a Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una Skype for Business ibrida.
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
ms.openlocfilehash: 24dc9deedc23456efcd1dc646ba05bff6ef818d8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777146"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Eseguire l'aggiornamento da Skype for Business distribuzione ibrida a Teams

![Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione.](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)
- [Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](./upgrade-prepare-environment.md)
- [Preparare l'organizzazione](./upgrade-prepare-organization.md)
- [Ha condotto un progetto pilota](./pilot-essentials.md)

Seguire le istruzioni di questo articolo se è stato distribuito Skype for Business o Microsoft Lync locale e lo si è configurato in una distribuzione ibrida con l'organizzazione di Microsoft 365 o Office 365 e l'organizzazione vuole eseguire l'aggiornamento a Teams in modo selettivo, usando più modalità di coesistenza o all-in. Per entrambi i percorsi di aggiornamento, è necessario spostare gli utenti in Skype for Business Online (se non sono già ospitati online) e quindi assegnare loro la modalità di coesistenza e aggiornamento appropriata.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Passaggio 1: Spostare gli utenti in Skype for Business Online

Questo passaggio si applica agli utenti ospitati in locale. Per altre informazioni sullo spostamento di questi utenti in Skype for Business Online, vedere Spostare gli utenti da locale a [Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Passaggio 2: Assegnare una modalità di coesistenza e aggiornamento

Dopo aver spostato gli utenti in Skype for Business Online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere Impostazione delle impostazioni di [coesistenza](./setting-your-coexistence-and-upgrade-settings.md) e aggiornamento e [TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> Con Skype for Business Server 2019 e un aggiornamento cumulativo futuro di Skype for Business Server 2015, sarà possibile eseguire il passaggio 1 (spostare gli utenti in Skype for Business Online) e il passaggio 2 (aggiornare gli utenti a Teams) in un unico passaggio. Altre informazioni verranno fornite dopo il Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Sistema telefonico e Teams aggiornamento

Se stai eseguendo la transizione della distribuzione ibrida di Skype for Business a Sistema telefonico con Piani per le chiamate e Microsoft sarà il tuo provider di rete PSTN (Public Switched Telephone Network) e presupponendo che sia stata completata la portabilità del numero di telefono, l'aggiornamento degli utenti a Teams esegue automaticamente la transizione delle chiamate PSTN in ingresso a Teams.

Se Piani per chiamate non è disponibile o si prevede di usare il provider di connettività PSTN esistente, è necessario eseguire la transizione della distribuzione voIP aziendale o della distribuzione vocale ibrida che usa la distribuzione locale esistente o Cloud Connector Edition per Telefono Microsoft System Direct Routing. Per aggiornare gli utenti a Teams, vedere le considerazioni aggiuntive per [Sistema telefonico routing diretto.](./direct-routing-landing-page.md)