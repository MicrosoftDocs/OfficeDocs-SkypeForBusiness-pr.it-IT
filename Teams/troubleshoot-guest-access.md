---
title: Risolvere i problemi relativi all'accesso guest in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Informazioni sulla risoluzione dei problemi relativi all'accesso guest in Microsoft teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: eefaece55876bc66905716526884fd21303c630e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754362"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="d9012-103">Risolvere i problemi relativi all'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d9012-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="d9012-104">Potrebbe essere necessario attendere fino a 24 ore affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="d9012-104">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="d9012-105">Per verificare se sono presenti problemi di supporto corrente con l'accesso guest in teams, vedere [risoluzione dei problemi relativi ai team](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="d9012-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="d9012-106">Per scoprire se si conosce il problema, vedere [problemi noti di Microsoft teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d9012-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="d9012-107">Gli ospiti sono utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9012-107">Guests are users outside your organization.</span></span> <span data-ttu-id="d9012-108">Se un utente si trova all'interno dell'organizzazione (inclusi i dipendenti, gli appaltatori onsite o gli agenti onsite), non può essere aggiunto come Guest.</span><span class="sxs-lookup"><span data-stu-id="d9012-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="d9012-109">Lo stesso vale per gli affiliati.</span><span class="sxs-lookup"><span data-stu-id="d9012-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="d9012-110">Informazioni sulle prossime funzionalità di accesso Guest nuove o aggiornate nella roadmap per i [Team](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="d9012-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="d9012-111">Dirci cosa si vuole in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="d9012-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="d9012-112">Se i clienti vedono gli errori di licenza</span><span class="sxs-lookup"><span data-stu-id="d9012-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="d9012-113">L'accesso guest in teams USA Azure Active Directory (Azure AD) business to business (B2B) e il relativo modello di licenza.</span><span class="sxs-lookup"><span data-stu-id="d9012-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="d9012-114">L'accesso Guest è incluso in tutti gli abbonamenti a Office 365 Business Premium, Office 365 Enterprise e Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="d9012-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="d9012-115">Non sono necessarie altre licenze di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9012-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="d9012-116">Se si verificano errori di gestione delle licenze, leggere le [istruzioni per la licenza B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) per determinare i requisiti di licenza per soddisfare le proprie esigenze per l'accesso guest nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9012-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="d9012-117">Le licenze Guest vengono conteggiate con l'organizzazione invitante.</span><span class="sxs-lookup"><span data-stu-id="d9012-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="d9012-118">Considerate questa operazione quando si calcola il numero di licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="d9012-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="d9012-119">Le licenze vengono conteggiate in base all'organizzazione se gli ospiti invitati provengono da un altro tenant di Office 365 o usano gli indirizzi di posta elettronica personali.</span><span class="sxs-lookup"><span data-stu-id="d9012-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9012-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d9012-120">Related topics</span></span>

[<span data-ttu-id="d9012-121">Accesso guest in teams</span><span class="sxs-lookup"><span data-stu-id="d9012-121">Guest access in Teams</span></span>](guest-access.md)


