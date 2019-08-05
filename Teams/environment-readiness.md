---
title: Verificare la disponibilità dell'ambiente per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Informazioni su cosa cercare quando si verifica la disponibilità dell'ambiente per Microsoft teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1794b87beb1c6b1f1e499c214cde8d3e0b9b0a34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181660"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Verificare la disponibilità dell'ambiente per Microsoft Teams
===========================================

La transizione al cloud varia da ogni organizzazione e lo stato corrente può avere un impatto sul funzionamento dei team.

Gli istituti di istruzione sono fortemente incoraggiati a [distribuire School Data Sync](https://docs.microsoft.com/schooldatasync/) prima di distribuire Microsoft teams. School Data Sync usa i dati del roster SIS della scuola per creare automaticamente classi e gruppi per Microsoft teams e altre applicazioni.

Per ottenere l'esperienza migliore in teams, è necessario che l'organizzazione abbia distribuito Exchange Online e SharePoint Online. Devi anche assicurarti che l'ambiente corrente sia pronto per i team.  Fare riferimento a questi collegamenti per assistenza:

-   Se l'organizzazione non ha distribuito i carichi di lavoro di Office 365, vedere [Introduzione a office 365 for business.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

-   Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Office 365, vedere [verificare il dominio di office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Se l'organizzazione non ha sincronizzato le identità con Azure Active Directory, vedere [modelli di identità e autenticazione in Microsoft teams](identify-models-authentication.md).

-   Se l'organizzazione non ha Exchange Online, vedere [informazioni su come interagire con Exchange e Microsoft teams](Exchange-Teams-interact.md).

-   Se l'organizzazione non ha SharePoint Online, vedere [informazioni sul modo in cui SharePoint Online e OneDrive for business interagiscono con Microsoft teams](SharePoint-OneDrive-interact.md).

- Se l'organizzazione è un Istituto di istruzione e si usa un sistema di informazioni per studenti (SIS), [distribuire School Data Sync](https://docs.microsoft.com/schooldatasync/) prima di distribuire Microsoft teams.

- Se l'organizzazione ha una distribuzione locale di Skype for Business Server (o Lync Server) esistente, è necessario configurare Azure AD Connect per sincronizzare la directory locale con Office 365.  Per altre informazioni, vedere [configurare Azure ad Connect per Teams e Skype for business](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).