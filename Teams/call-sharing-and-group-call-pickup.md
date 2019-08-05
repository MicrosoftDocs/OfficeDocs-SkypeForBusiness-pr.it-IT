---
title: Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Condivisione chiamate e raccolta chiamate di gruppo consente agli utenti di condividere le chiamate in arrivo con i colleghi in modo che le chiamate possano essere acquisite quando l'utente non è disponibile.
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182272"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="adc07-103">Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="adc07-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="adc07-104">Le funzionalità di condivisione chiamata e raccolta chiamate di gruppo di Microsoft teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano mentre l'utente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="adc07-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="adc07-105">Il ritiro delle chiamate di gruppo è meno distruttivo per i destinatari rispetto ad altre forme di condivisione delle chiamate, ad esempio l'inoltro di chiamata o lo squillo simultaneo, perché gli utenti possono configurare il modo in cui vogliono ricevere una notifica di una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visivo, o banner nell'app Teams), che può decidere se rispondere.</span><span class="sxs-lookup"><span data-stu-id="adc07-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="adc07-106">Per condividere le chiamate con altre persone, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vogliono condividere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="adc07-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="adc07-107">Quindi scelgono un anello o un'impostazione di inoltro simultaneo.</span><span class="sxs-lookup"><span data-stu-id="adc07-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="adc07-108">Per informazioni dettagliate, vedere [inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="adc07-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="adc07-109">Gli utenti, il proprietario del gruppo di chiamate e i membri del gruppo di chiamate devono essere solo in modalità di distribuzione in teams.</span><span class="sxs-lookup"><span data-stu-id="adc07-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="adc07-110">Per altre informazioni sulle modalità di distribuzione dei team, vedere comprendere la coesistenza e l'interoperabilità di [Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="adc07-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="adc07-111">Licenza richiesta</span><span class="sxs-lookup"><span data-stu-id="adc07-111">License required</span></span>

<span data-ttu-id="adc07-112">Gli utenti devono essere abilitati a VoIP aziendale per configurare e usare la condivisione delle chiamate e il pick-up delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="adc07-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="adc07-113">Per altre informazioni sul modello di licenza, vedere [licenze di Office 365 per Microsoft teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="adc07-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="adc07-114">Configurare il ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="adc07-114">Configure group call pickup</span></span>

<span data-ttu-id="adc07-115">Per configurare il ritiro delle chiamate di gruppo, un utente configura prima di tutto un gruppo di chiamate (non è uguale a un gruppo di sicurezza o a un gruppo di Office 365) e quindi aggiunge gli utenti con cui vogliono condividere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="adc07-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="adc07-116">Quindi scelgono un anello simultaneo o un'impostazione di inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="adc07-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="adc07-117">Per altre informazioni e procedure dettagliate, vedere [inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="adc07-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="adc07-118">Le preferenze per la creazione e la notifica di gruppi di chiamate sono caratteristiche guidate dall'utente; gli amministratori non devono configurare queste funzionalità per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="adc07-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="adc07-119">Non è possibile creare gruppi di chiamate da gruppi di sicurezza o gruppi di Office 365; devono essere creati in teams.</span><span class="sxs-lookup"><span data-stu-id="adc07-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="adc07-120">Gli amministratori dovrebbero abilitare i gruppi di chiamate tramite l'impostazione **TeamsCallingPolicy AllowCallGroups** per un utente.</span><span class="sxs-lookup"><span data-stu-id="adc07-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="adc07-121">Gli amministratori possono solo controllare se l'utente può configurare i gruppi di chiamate.</span><span class="sxs-lookup"><span data-stu-id="adc07-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="adc07-122">Quando il bit è impostato su true, gli amministratori non possono impedire all'utente di configurare e aggiungere gli utenti del gruppo di chiamate a loro scelta.</span><span class="sxs-lookup"><span data-stu-id="adc07-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="adc07-123">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="adc07-123">Limitations</span></span>

<span data-ttu-id="adc07-124">Un tenant può contenere un massimo di 32.768 gruppi di chiamate.</span><span class="sxs-lookup"><span data-stu-id="adc07-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="adc07-125">In ogni gruppo di chiamate può essere disponibile un massimo di 5 utenti.</span><span class="sxs-lookup"><span data-stu-id="adc07-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="adc07-126">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="adc07-126">More information</span></span>

[<span data-ttu-id="adc07-127">Inoltro di chiamata e squillo simultaneo in teams</span><span class="sxs-lookup"><span data-stu-id="adc07-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)