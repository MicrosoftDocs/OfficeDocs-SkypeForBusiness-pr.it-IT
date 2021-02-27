---
title: Prerequisiti e dipendenze ambientali per l'aggiornamento a Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Usare queste indicazioni per informazioni sui prerequisiti e sulle dipendenze ambientali per la distribuzione di Teams nell'organizzazione
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
ms.openlocfilehash: b0ad5716dbbe1925a93f4fbfadca7084e39a9599
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347807"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Prerequisiti e dipendenze ambientali per Teams

![Diagramma percorso di aggiornamento, enfatizzando la fase Technical Readiness](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con enfasi sulla fase Technical Readiness")

Questo articolo fa parte della fase Technical Readiness del percorso di aggiornamento, un'attività che viene completata in parallelo con la fase Di conformità degli utenti. Prima di procedere, verificare di aver completato queste attività dalle fasi precedenti:

- [Integrare gli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità comprensibili di Skype for Business e Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combina più servizi di Microsoft 365 e Office 365 e quindi dipende dall'implementazione e dal funzionamento corretti di questi servizi. Questi servizi includono, ma non limitati, SharePoint Online, Exchange Online e OneDrive for Business.

Anche se non tutti i servizi sono necessari, è consigliabile implementarli tutti. Se si sceglie di non implementare determinati servizi, ciò influirà sulle funzionalità che Teams può offrire all'organizzazione. Ad esempio, anche se non è necessario implementare SharePoint Online, Teams si basa su SharePoint Online per alcune funzionalità come la condivisione di file nelle conversazioni di gruppo, quindi non implementare questo servizio ridurrà le funzionalità offerte dal client.

Vedere gli articoli seguenti per informazioni sui prerequisiti e su come Teams interagisce con altre tecnologie:

- Se l'organizzazione non ha distribuito carichi di lavoro di Microsoft 365 o Office 365, vedere [Introduzione.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, vedere [le domande frequenti sui domini.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Se l'organizzazione non ha sincronizzato le identità con Azure Active Directory, vedere i modelli di identità e [l'autenticazione in Microsoft Teams.](identify-models-authentication.md)

- Se l'organizzazione non ha Exchange Online, vedere Informazioni [sull'interazione tra Exchange e Microsoft Teams.](Exchange-Teams-interact.md)

- Se l'organizzazione non ha SharePoint Online, vedere Informazioni sull'interazione tra SharePoint Online e [OneDrive for Business con Microsoft Teams.](SharePoint-OneDrive-interact.md)

- Per informazioni [sull'interazione tra Microsoft 365 e Microsoft Teams.](Office-365-groups.md)

- Se l'organizzazione è un istituto di istruzione e si usa un sistema SIS, vedere [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) prima di distribuire Microsoft Teams.

- Se la tua organizzazione sta valutando l'opzione per le chiamate PSTN (Public Switched Telephone Network), consulta l'opzione Voce - Sistema telefonico e connettività [PSTN,](cloud-voice-landing-page.md)il piano per le chiamate più per te e l'instradamento diretto [](calling-plan-landing-page.md) [del](direct-routing-landing-page.md)sistema telefonico.

- Per assicurarsi che tutti i requisiti di rete siano stati soddisfatti prima dell'implementazione di Teams, vedere Preparare la rete [dell'organizzazione per Microsoft Teams.](prepare-network.md)

- Se attualmente si usa Skype for Business Online Connector per gestire i servizi, è necessario passare al modulo Di PowerShell di Teams e aggiornare gli script di PowerShell esistenti. Per altre informazioni, vedere Passare [da Skype for Business Online Connector al modulo Di PowerShell](teams-powershell-move-from-sfbo.md) di Teams.

Dopo aver verificato che l'ambiente soddisfi tutti i prerequisiti applicabili, valutare [l'ambiente corrente per Teams.](upgrade-plan-journey-evaluate-environment.md)
