---
title: Prerequisiti di Microsoft Teams | Aggiornamento delle dipendenze di adozione
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Usare queste indicazioni per informazioni sui prerequisiti e sulle dipendenze ambientali per la distribuzione di team nell'organizzazione
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
ms.openlocfilehash: ec634105f87c548ed962bdf9f098298f01f1e93e
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706866"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Prerequisiti e dipendenze ambientali per i team

![Aggiornare il diagramma di viaggio, enfatizzando la fase di preparazione tecnica](media/upgrade-banner-tech-readiness.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di preparazione tecnica")

Questo articolo fa parte della fase di preparazione tecnica del viaggio di aggiornamento, un'attività completata in parallelo con la fase di preparazione degli utenti. Prima di procedere, verificare di aver completato queste attività dalle fasi precedenti:

- [Elenco delle parti interessate del progetto](upgrade-enlist-stakeholders.md)
- [Definizione dell'ambito del progetto](https://aka.ms/SkypetoTeams-Scope)
- [Coesistenza e interoperabilità intesa di Skype for business e teams](https://aka.ms/SkypeToTeams-Coexist)
- [Scelto il viaggio di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combina più servizi di Office 365 e dipende quindi dall'implementazione e dal funzionamento corretti di questi servizi. Questi servizi includono, ma non sono limitati a, SharePoint Online, Exchange Online e OneDrive for business.

Anche se non tutti i servizi sono obbligatori, ti consigliamo di implementarli tutti. Se si sceglie di non implementare determinati servizi, verranno influenzati dalla funzionalità che i team possono offrire alla propria organizzazione. Ad esempio, anche se non è necessario implementare SharePoint Online, i team si basano su SharePoint Online per alcune funzionalità, come la condivisione di file in conversazioni di gruppo, quindi non l'implementazione di questo servizio ridurrà le funzionalità offerte tramite il client.

Vedere gli articoli seguenti per informazioni sui prerequisiti e sul modo in cui i team interagiscono con altre tecnologie:

- Se l'organizzazione non ha distribuito i carichi di lavoro di Office 365, vedere [Introduzione a office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Office 365, vedere [verificare il dominio di office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Se l'organizzazione non ha sincronizzato le identità con Azure Active Directory, vedere [modelli di identità e autenticazione in Microsoft teams](identify-models-authentication.md).

- Se l'organizzazione non ha<sup>una</sup>t di Exchange Online, vedere [informazioni su come interagire con Exchange e Microsoft teams](Exchange-Teams-interact.md).

- Se l'organizzazione non ha SharePoint Online, vedere [informazioni sul modo in cui SharePoint Online e OneDrive for business interagiscono con Microsoft teams](SharePoint-OneDrive-interact.md).

- Informazioni su come [interagire con i gruppi di Office 365 e Microsoft teams](Office-365-groups.md).

- Se l'organizzazione è un Istituto di istruzione e si usa un sistema di informazioni per studenti, [distribuire School Data Sync](https://docs.microsoft.com/schooldatasync) prima di distribuire Microsoft teams.

Dopo aver verificato che l'ambiente soddisfi tutti i prerequisiti applicabili, [valutare l'ambiente corrente per i team](upgrade-plan-journey-evaluate-environment.md).
