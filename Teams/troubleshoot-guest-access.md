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
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837636"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="2cf6c-103">Risolvere i problemi relativi all'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2cf6c-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="2cf6c-104">Possono essere necessarie fino a 24 ore prima che le modifiche diventino effettive.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="2cf6c-105">Per verificare gli attuali problemi di supporto tecnico con l'accesso guest in Team, passare a [Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="2cf6c-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="2cf6c-106">Per sapere se questo problema è stato già riscontrato, vedere [Problemi noti di Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2cf6c-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="2cf6c-107">I guest sono utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-107">Guests are users outside your organization.</span></span> <span data-ttu-id="2cf6c-108">Se qualcuno si trova all'interno dell'organizzazione (tra cui dipendenti, terzisti o agenti sul posto), non può essere aggiunto come guest.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="2cf6c-109">Lo stesso vale per le consociate.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="2cf6c-110">Sono presenti informazioni riguardanti le nuove o aggiornate prossime funzionalità di accesso guest nella [Roadmap di Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="2cf6c-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="2cf6c-111">Inviare il proprio feedback in [UserVoice di Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="2cf6c-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="2cf6c-112">I guest visualizzano errori di licenza.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="2cf6c-113">L'accesso guest in Teams utilizza Azure Active Directory (Azure AD) Business to Business (B2B) e il relativo modello di licenza.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="2cf6c-114">L'accesso guest è incluso in tutti gli abbonamenti di Office 365 Business Premium, Office 365 Enterprise e Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="2cf6c-115">Non sono necessarie altre licenze di Office 365.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="2cf6c-116">Se vengono visualizzati errori di licenza, leggere la [Guida alle licenze Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) per determinare i requisiti di licenza necessari per soddisfare le esigenze di accesso guest nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="2cf6c-117">Le licenze guest vengono conteggiate rispetto all'organizzazione che invita:</span><span class="sxs-lookup"><span data-stu-id="2cf6c-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="2cf6c-118">tenerlo presente quando si calcola il numero di licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="2cf6c-119">Le licenze vengono conteggiate rispetto all'organizzazione, indipendentemente dal fatto che i guest invitati provengano da un altro tenant di Office 365 o utilizzino i loro indirizzi di posta elettronica personali.</span><span class="sxs-lookup"><span data-stu-id="2cf6c-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="2cf6c-120">Supporto per i tipi di utente B2B</span><span class="sxs-lookup"><span data-stu-id="2cf6c-120">Support for B2B User types</span></span>
<span data-ttu-id="2cf6c-121">Attualmente, Teams prevede il supporto solo per i tipi di utenti guest Stato1 e Stato 2 [come definiti da Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="2cf6c-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2cf6c-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2cf6c-122">Related topics</span></span>

[<span data-ttu-id="2cf6c-123">Accesso guest in Teams</span><span class="sxs-lookup"><span data-stu-id="2cf6c-123">Guest access in Teams</span></span>](guest-access.md)


