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
ms.openlocfilehash: 6ceca08be6d69a10fe84daa64d0da4e31c61c67c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092194"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Prerequisiti e dipendenze ambientali per Teams

![Diagramma del percorso di aggiornamento, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")

Questo articolo fa parte della fase Technical Readiness del percorso di aggiornamento, un'attività che viene completata in parallelo con la fase Di conformità dell'utente. Prima di procedere, verificare di aver completato queste attività nelle fasi precedenti:

- [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)
- [Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combina più servizi Microsoft 365 e Office 365 e quindi dipende dall'implementazione e dal funzionamento corretti di questi servizi. Questi servizi includono, ma non solo, SharePoint Online, Exchange Online e OneDrive for Business.

Anche se non tutti i servizi sono necessari, è consigliabile implementarli tutti. Se si sceglie di non implementare determinati servizi, questa influisce sulle funzionalità che Teams può offrire all'organizzazione. Ad esempio, anche se non è necessario implementare SharePoint Online, Teams si basa su SharePoint Online per determinate funzionalità, ad esempio la condivisione di file nelle conversazioni di gruppo, quindi la non implementazione di questo servizio ridurrà le funzionalità offerte dal client.

Vedere gli articoli seguenti per informazioni sui prerequisiti e su come Teams interagisce con altre tecnologie:

- Se l'organizzazione non ha distribuito carichi di lavoro di Microsoft 365 o Office 365, vedere [Introduzione.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, vedere [Domande frequenti sui domini.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Se l'organizzazione non ha sincronizzato le identità con Azure Active Directory, vedere Modelli di identità [e autenticazione in Microsoft Teams.](identify-models-authentication.md)

- Se l'organizzazione non ha Exchange Online, vedere Informazioni [sull'interazione tra Exchange e Microsoft Teams.](Exchange-Teams-interact.md)

- Se l'organizzazione non ha SharePoint Online, vedere Informazioni sull'interazione tra SharePoint Online e [OneDrive for Business con Microsoft Teams.](SharePoint-OneDrive-interact.md)

- Per informazioni sull'interazione tra i gruppi [di Microsoft 365 e Microsoft Teams.](Office-365-groups.md)

- Se l'organizzazione è un istituto di istruzione e si usa un sistema di informazioni degli studenti, vedere Introduzione a [Microsoft School Data Sync](/schooldatasync) prima di distribuire Microsoft Teams.

- Se l'organizzazione sta valutando le opzioni per le chiamate PSTN (Public Switched Telephone Network), vedere Voice - Sistema telefonico e connettività [PSTN](cloud-voice-landing-page.md), Quale piano per le chiamate è giusto per [te](calling-plan-landing-page.md)e Routing diretto del sistema telefonico [.](direct-routing-landing-page.md)

- Per assicurarsi che tutti i requisiti di rete siano stati soddisfatti prima della distribuzione di Teams, vedere Preparare la rete [dell'organizzazione per Microsoft Teams.](prepare-network.md)

- Se attualmente si usa Skype for Business Online Connector per gestire i servizi, è necessario passare al modulo di PowerShell di Teams e aggiornare gli script di PowerShell esistenti. Per [altre informazioni, vedere Passare da Skype for Business Online Connector al modulo di PowerShell](teams-powershell-move-from-sfbo.md) di Teams.

Dopo aver verificato che l'ambiente soddisfi tutti i prerequisiti applicabili, valutare [l'ambiente corrente per Teams.](upgrade-plan-journey-evaluate-environment.md)