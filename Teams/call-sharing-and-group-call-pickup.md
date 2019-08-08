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
ms.openlocfilehash: caf472f9829f9cf68ccb87a5081bc0b5cfae28f8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237166"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="6e0fa-103">Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e0fa-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="6e0fa-104">Le funzionalità di condivisione chiamata e raccolta chiamate di gruppo di Microsoft teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano mentre l'utente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="6e0fa-105">Il ritiro delle chiamate di gruppo è meno distruttivo per i destinatari rispetto ad altre forme di condivisione delle chiamate, ad esempio l'inoltro di chiamata o lo squillo simultaneo, perché gli utenti possono configurare il modo in cui vogliono ricevere una notifica di una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visivo, o banner nell'app Teams), che può decidere se rispondere.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="6e0fa-106">Per condividere le chiamate con altre persone, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vogliono condividere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="6e0fa-107">Quindi scelgono un anello o un'impostazione di inoltro simultaneo.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="6e0fa-108">Per informazioni dettagliate, vedere [inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="6e0fa-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e0fa-109">Gli utenti, il proprietario del gruppo di chiamate e i membri del gruppo di chiamate devono essere solo in modalità di distribuzione in teams.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="6e0fa-110">Per altre informazioni sulle modalità di distribuzione dei team, vedere comprendere la coesistenza e l'interoperabilità di [Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6e0fa-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="6e0fa-111">Licenza richiesta</span><span class="sxs-lookup"><span data-stu-id="6e0fa-111">License required</span></span>

<span data-ttu-id="6e0fa-112">Gli utenti devono essere abilitati a VoIP aziendale per configurare e usare la condivisione delle chiamate e il pick-up delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="6e0fa-113">Per altre informazioni sul modello di licenza, vedere [licenze di Office 365 per Microsoft teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6e0fa-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="6e0fa-114">Configurare il ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="6e0fa-114">Configure group call pickup</span></span>

<span data-ttu-id="6e0fa-115">Per configurare il ritiro delle chiamate di gruppo, un utente configura prima di tutto un gruppo di chiamate (non è uguale a un gruppo di sicurezza o a un gruppo di Office 365) e quindi aggiunge gli utenti con cui vogliono condividere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="6e0fa-116">Quindi scelgono un anello simultaneo o un'impostazione di inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="6e0fa-117">Per altre informazioni e procedure dettagliate, vedere [inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="6e0fa-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="6e0fa-118">Le preferenze per la creazione e la notifica di gruppi di chiamate sono caratteristiche guidate dall'utente; gli amministratori non devono configurare queste funzionalità per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="6e0fa-119">Non è possibile creare gruppi di chiamate da gruppi di sicurezza o gruppi di Office 365; devono essere creati in teams.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="6e0fa-120">Gli amministratori dovrebbero abilitare i gruppi di chiamate tramite l'impostazione **TeamsCallingPolicy AllowCallGroups** per un utente.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="6e0fa-121">Gli amministratori possono anche abilitare questo tramite il portale di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-121">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="6e0fa-122">Inoltre, l'utente configurato può anche configurare i gruppi di chiamate direttamente tramite il client.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-122">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="6e0fa-123">L'amministratore o gli utenti finali non possono bloccare la configurazione a vicenda, ma il portale di amministrazione di teams e il client teams devono mostrare questa relazione accuratamente in entrambe le posizioni.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-123">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="6e0fa-124">Importante: quando gli amministratori disattivano i gruppi di chiamate per gli utenti (dopo che sono stati attivati e sono configurate le relazioni di gruppo delle chiamate), gli amministratori devono pulire le relazioni di gruppo delle chiamate per gli utenti nell'interfaccia di amministrazione del team per evitare il routing delle chiamate non corretto.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-124">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="6e0fa-125">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="6e0fa-125">Limitations</span></span>

<span data-ttu-id="6e0fa-126">Un tenant può contenere un massimo di 32.768 gruppi di chiamate.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-126">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="6e0fa-127">In ogni gruppo di chiamate può essere disponibile un massimo di 25 utenti.</span><span class="sxs-lookup"><span data-stu-id="6e0fa-127">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="6e0fa-128">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="6e0fa-128">More information</span></span>

[<span data-ttu-id="6e0fa-129">Inoltro di chiamata e squillo simultaneo in teams</span><span class="sxs-lookup"><span data-stu-id="6e0fa-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
