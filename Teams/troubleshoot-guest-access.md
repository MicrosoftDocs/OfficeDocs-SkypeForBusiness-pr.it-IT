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
description: Assistenza per la risoluzione dei problemi relativi all'accesso guest in Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 7e4db423d262f939362400cdec489ca065b5d5c1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086203"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="48c6c-103">Risolvere i problemi relativi all'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48c6c-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

- <span data-ttu-id="48c6c-104">Per verificare se si conosce il problema, vedere [team di supporto nell'organizzazione](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="48c6c-104">To see whether we know about your problem, check out [Support Teams in your organization](Known-issues.md).</span></span>
- <span data-ttu-id="48c6c-105">Per verificare gli attuali problemi di supporto tecnico con l'accesso guest in Team, passare a [Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="48c6c-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="48c6c-106">I guest sono utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="48c6c-106">Guests are users outside your organization.</span></span> <span data-ttu-id="48c6c-107">Se qualcuno si trova all'interno dell'organizzazione (tra cui dipendenti, terzisti o agenti sul posto), non può essere aggiunto come guest.</span><span class="sxs-lookup"><span data-stu-id="48c6c-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="48c6c-108">Lo stesso vale per le consociate.</span><span class="sxs-lookup"><span data-stu-id="48c6c-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="48c6c-109">Sono presenti informazioni riguardanti le nuove o aggiornate prossime funzionalità di accesso guest nella [Roadmap di Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="48c6c-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="48c6c-110">Inviare il proprio feedback in [UserVoice di Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="48c6c-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="48c6c-111">I guest visualizzano errori di licenza.</span><span class="sxs-lookup"><span data-stu-id="48c6c-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="48c6c-112">L'accesso guest in Teams utilizza Azure Active Directory (Azure AD) Business to Business (B2B) e il relativo modello di licenza.</span><span class="sxs-lookup"><span data-stu-id="48c6c-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="48c6c-113">L'accesso guest è incluso in tutti gli abbonamenti di Microsoft 365 Business Standard, Office 365 Enterprise e Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="48c6c-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="48c6c-114">Non sono necessarie altre licenze di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="48c6c-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="48c6c-115">I team devono essere abilitati nel tenant di un Guest per consentire agli utenti di accedere e usare i team come guest in un altro tenant (risorsa).</span><span class="sxs-lookup"><span data-stu-id="48c6c-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="48c6c-116">Se si verificano errori di gestione delle licenze, leggere le [istruzioni per la licenza B2B di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) per determinare i requisiti di licenza per soddisfare le proprie esigenze per l'accesso guest nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="48c6c-116">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="48c6c-117">Le licenze guest vengono conteggiate rispetto all'organizzazione che invita:</span><span class="sxs-lookup"><span data-stu-id="48c6c-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="48c6c-118">tenerlo presente quando si calcola il numero di licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="48c6c-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="48c6c-119">Le licenze vengono conteggiate in base all'organizzazione se gli ospiti invitati provengono da un'altra organizzazione Microsoft 365 o Office 365 o usano gli indirizzi di posta elettronica personali.</span><span class="sxs-lookup"><span data-stu-id="48c6c-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 or Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="48c6c-120">Supporto per i tipi di utente B2B</span><span class="sxs-lookup"><span data-stu-id="48c6c-120">Support for B2B User types</span></span>
<span data-ttu-id="48c6c-121">Attualmente, Teams prevede il supporto solo per i tipi di utenti guest Stato1 e Stato 2 [come definiti da Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="48c6c-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="48c6c-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="48c6c-122">Related topics</span></span>

[<span data-ttu-id="48c6c-123">Accesso guest in Teams</span><span class="sxs-lookup"><span data-stu-id="48c6c-123">Guest access in Teams</span></span>](guest-access.md)


[<span data-ttu-id="48c6c-124">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="48c6c-124">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)