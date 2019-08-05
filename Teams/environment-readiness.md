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
<a name="check-your-environments-readiness-for-microsoft-teams"></a><span data-ttu-id="1196c-103">Verificare la disponibilità dell'ambiente per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1196c-103">Check your environment’s readiness for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="1196c-104">La transizione al cloud varia da ogni organizzazione e lo stato corrente può avere un impatto sul funzionamento dei team.</span><span class="sxs-lookup"><span data-stu-id="1196c-104">The transition to the cloud will vary by each organization, and current state may have an impact on how Teams will function.</span></span>

<span data-ttu-id="1196c-105">Gli istituti di istruzione sono fortemente incoraggiati a [distribuire School Data Sync](https://docs.microsoft.com/schooldatasync/) prima di distribuire Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="1196c-105">Educational institutions are strongly encouraged to [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span> <span data-ttu-id="1196c-106">School Data Sync usa i dati del roster SIS della scuola per creare automaticamente classi e gruppi per Microsoft teams e altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1196c-106">School Data Sync uses your school’s SIS roster data to automatically create classes and groups for Microsoft Teams and other applications.</span></span>

<span data-ttu-id="1196c-107">Per ottenere l'esperienza migliore in teams, è necessario che l'organizzazione abbia distribuito Exchange Online e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1196c-107">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="1196c-108">Devi anche assicurarti che l'ambiente corrente sia pronto per i team.</span><span class="sxs-lookup"><span data-stu-id="1196c-108">You must also ensure that your current environment is ready for Teams.</span></span>  <span data-ttu-id="1196c-109">Fare riferimento a questi collegamenti per assistenza:</span><span class="sxs-lookup"><span data-stu-id="1196c-109">Refer to these links for help:</span></span>

-   <span data-ttu-id="1196c-110">Se l'organizzazione non ha distribuito i carichi di lavoro di Office 365, vedere [Introduzione a office 365 for business.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="1196c-110">If your organization has not deployed any Office 365 workloads, see [Getting Started with Office 365 for business.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span></span>

-   <span data-ttu-id="1196c-111">Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Office 365, vedere [verificare il dominio di office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="1196c-111">If your organization has not added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="1196c-112">Se l'organizzazione non ha sincronizzato le identità con Azure Active Directory, vedere [modelli di identità e autenticazione in Microsoft teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1196c-112">If your organization has not synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="1196c-113">Se l'organizzazione non ha Exchange Online, vedere [informazioni su come interagire con Exchange e Microsoft teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="1196c-113">If your organization does not have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="1196c-114">Se l'organizzazione non ha SharePoint Online, vedere [informazioni sul modo in cui SharePoint Online e OneDrive for business interagiscono con Microsoft teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="1196c-114">If your organization does not have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="1196c-115">Se l'organizzazione è un Istituto di istruzione e si usa un sistema di informazioni per studenti (SIS), [distribuire School Data Sync](https://docs.microsoft.com/schooldatasync/) prima di distribuire Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="1196c-115">If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="1196c-116">Se l'organizzazione ha una distribuzione locale di Skype for Business Server (o Lync Server) esistente, è necessario configurare Azure AD Connect per sincronizzare la directory locale con Office 365.</span><span class="sxs-lookup"><span data-stu-id="1196c-116">If your organization has an existing on-premises Skype for Business Server (or Lync Server) deployment, you must configure Azure AD Connect to synchronize your on-premises directory with Office 365.</span></span>  <span data-ttu-id="1196c-117">Per altre informazioni, vedere [configurare Azure ad Connect per Teams e Skype for business](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="1196c-117">For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span></span>