---
title: Aggiornare la distribuzione ibrida di Skype for Business a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione ibrida di Skype for Business.
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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802346"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Eseguire l'aggiornamento da una distribuzione ibrida di Skype for Business a Teams

![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Integrare gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità comprensibili di Skype for Business e Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Organizzazione preparata](https://aka.ms/SkypeToTeams-UserReadiness)
- [Ha diretto un pilota](https://aka.ms/SkypeToTeams-Pilot)

Seguire le istruzioni fornite in questo articolo se Skype for Business o Microsoft Lync è stato distribuito in locale e configurato in una distribuzione ibrida con l'organizzazione di Microsoft 365 o Office 365 e l'organizzazione vuole eseguire l'aggiornamento a Teams in modo selettivo, utilizzando più modalità di coesistenza, o all-in. Per entrambe le modalità di aggiornamento, è necessario spostare gli utenti su Skype for Business online (se non sono già ospitati online) e quindi assegnare loro la modalità di coesistenza e aggiornamento appropriata.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Passaggio 1: Spostare gli utenti in Skype for Business online

Questo passaggio si applica agli utenti ospitati in locale. Per ulteriori informazioni su come spostare questi utenti in Skype for Business online, consulta Spostare utenti dalla distribuzione [locale a Skype for Business online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Passaggio 2: Assegnare una modalità di coesistenza e aggiornamento

Dopo aver spostato gli utenti in Skype for Business online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere Impostazione delle impostazioni di [coesistenza](https://aka.ms/SkypeToTeams-SetCoexistence) e aggiornamento [e TeamsUpgradePolicy: gestione della migrazione e della coesistenza.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> Con Skype for Business Server 2019 e un futuro aggiornamento cumulativo di Skype for Business Server 2015, sarà possibile eseguire i passaggi 1 (spostamento degli utenti in Skype for Business online) e Passaggio 2 (aggiornare gli utenti a Teams) in un unico passaggio. Altre informazioni verranno fornite dopo il rilascio di Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di Sistema telefonico e Teams

Se stai effettuando la transizione della tua distribuzione ibrida di Skype for Business al Sistema telefonico con Piani per chiamate e Microsoft sarà il tuo provider PSTN (Public Switched Telephone Network) (PSTN) e supponendo che tu abbia completato la portabilità del numero di telefono, l'aggiornamento degli utenti a Teams esegue automaticamente la transizione delle chiamate PSTN in ingresso a Teams.

Se i Piani per chiamate non sono disponibili o se intendi utilizzare il provider di connettività PSTN esistente, devi eseguire la transizione della distribuzione VoIP aziendale, o della distribuzione vocale ibrida che usa la distribuzione locale esistente o Cloud Connector Edition, al routing diretto del sistema telefonico Microsoft. Per aggiornare gli utenti a Teams, vedere le considerazioni aggiuntive sull'instradamento diretto [del sistema telefonico.](2-envision-make-my-service-decisions-direct-routing.md)
