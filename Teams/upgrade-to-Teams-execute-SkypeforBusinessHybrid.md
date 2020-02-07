---
title: Aggiornare la distribuzione ibrida di Skype for business a Microsoft Teams | PSTN
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerazioni per l'aggiornamento ai team da una distribuzione ibrida di Skype for business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a9f75e6f9e1d0465af56b49df86010697edbd3
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837076"
---
![Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con enfasi sulla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del viaggio di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

- [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)
- [Scelto il viaggio di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparare l'ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparare l'organizzazione](https://aka.ms/SkypeToTeams-UserReadiness)
- [Condotto un pilota](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Eseguire l'aggiornamento da una distribuzione ibrida di Skype for business a teams

Seguire le indicazioni di questo articolo se è stata distribuita in locale Skype for business o Microsoft Lync e la si è configurata in una distribuzione ibrida con il tenant di Office 365 e l'organizzazione vuole eseguire l'aggiornamento ai team in modo selettivo, usando più modalità di coesistenza-o all-in. Per entrambi i percorsi di aggiornamento, è necessario trasferire gli utenti a Skype for business online (se non sono già stati ospitati online) e quindi assegnare loro la modalità di coesistenza e di aggiornamento appropriata.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Passaggio 1: trasferire gli utenti in Skype for business online

Questo passaggio si applica agli utenti attualmente residenti in locale. Per altre informazioni sullo spostamento di questi utenti in Skype for business online, vedere [spostare gli utenti da locale a Skype for business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Passaggio 2: assegnare una modalità di coesistenza e aggiornamento

Dopo aver spostato gli utenti in Skype for business online, è possibile assegnare loro la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere [impostazione delle impostazioni di coesistenza e aggiornamento](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: gestione della migrazione e della coesistenza](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Con Skype for Business Server 2019 e un futuro aggiornamento cumulativo di Skype for Business Server 2015, sarà possibile eseguire il passaggio 1 (spostando gli utenti in Skype for business online) e il passaggio 2 (aggiornare gli utenti ai team) in un unico passaggio. Altre informazioni verranno fornite dopo il rilascio di Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Aggiornamento di sistema telefonico e teams

Se si sta eseguendo la transizione della distribuzione ibrida di Skype for business al sistema telefonico con i piani per le chiamate e Microsoft sarà il provider PSTN (Public Switched Telephone Network) e supponendo di aver completato la portabilità del numero di telefono, aggiornare gli utenti a I team eseguiranno automaticamente la transizione delle chiamate PSTN in ingresso ai team.

Se i piani di chiamata non sono disponibili o si intende usare il provider di connettività PSTN esistente, è necessario eseguire la transizione della distribuzione vocale aziendale oppure una distribuzione vocale ibrida che usa la distribuzione locale esistente o il Cloud Connector Edition, per Routing diretto di Microsoft Phone System. Per aggiornare gli utenti a teams, vedere le [considerazioni aggiuntive per il routing diretto del sistema telefonico](2-envision-make-my-service-decisions-direct-routing.md).
