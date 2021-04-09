---
title: Condivisione delle chiamate e risposta alle chiamate di gruppo
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: La condivisione delle chiamate e il ritiro delle chiamate di gruppo consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che le chiamate possano essere acquisite quando l'utente non è disponibile.
ms.openlocfilehash: 88c8d41eb0cf58413df995274bb9accd50b897c9
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637828"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="c75b8-103">Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c75b8-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="c75b8-104">Le funzionalità di condivisione delle chiamate e di ritiro delle chiamate di gruppo di Microsoft Teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano mentre l'utente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="c75b8-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="c75b8-105">Il ritiro delle chiamate di gruppo è meno dannoso per i destinatari rispetto ad altre forme di condivisione delle chiamate (ad esempio inoltro di chiamata o squillo simultaneo), perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visivo o banner nell'app Teams) e possono decidere se rispondere.</span><span class="sxs-lookup"><span data-stu-id="c75b8-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="c75b8-106">Per condividere le chiamate con altri utenti, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vogliono condividere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="c75b8-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="c75b8-107">Quindi scelgono un anello simultaneo o un'impostazione in avanti.</span><span class="sxs-lookup"><span data-stu-id="c75b8-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="c75b8-108">Per [informazioni dettagliate, vedere Inoltro di chiamata e squillo simultaneo in Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="c75b8-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="c75b8-109">Tieni presente che i dispositivi mobili riceveranno una notifica solo se sono impostati per banner e suonerie.</span><span class="sxs-lookup"><span data-stu-id="c75b8-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c75b8-110">Gli utenti, il proprietario del gruppo di chiamate e i membri del gruppo di chiamata devono essere in modalità di distribuzione Solo Teams.</span><span class="sxs-lookup"><span data-stu-id="c75b8-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="c75b8-111">Per maggiori dettagli sulle modalità di distribuzione di Teams, vedi Informazioni sulla coesistenza e [l'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) di Microsoft Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c75b8-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="c75b8-112">Licenza richiesta</span><span class="sxs-lookup"><span data-stu-id="c75b8-112">License required</span></span>

<span data-ttu-id="c75b8-113">Agli utenti deve essere assegnata una licenza Di sistema telefonico di Microsoft Teams per configurare e usare la condivisione delle chiamate e il ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="c75b8-113">Users must be assigned a Microsoft Teams Phone System license to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="c75b8-114">Per altri dettagli sul modello di licenza, vedere Ecco cosa [si ottiene con Sistema telefonico.](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)</span><span class="sxs-lookup"><span data-stu-id="c75b8-114">For additional details on the licensing model, see [Here's what you get with Phone System](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="c75b8-115">Configurare il ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="c75b8-115">Configure group call pickup</span></span>

<span data-ttu-id="c75b8-116">Per configurare il ritiro delle chiamate di gruppo, un utente configura prima di tutto un gruppo di chiamate (non corrisponde a un gruppo di sicurezza o a un gruppo di Microsoft 365) e quindi aggiunge gli utenti con cui vogliono condividere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="c75b8-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="c75b8-117">Quindi, scelgono un'impostazione di inoltro di chiamata o squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="c75b8-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="c75b8-118">Per altre informazioni e procedure dettagliate, vedere Inoltro di chiamata e [squillo simultaneo in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="c75b8-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="c75b8-119">Le preferenze per la creazione di gruppi di chiamate e le notifiche sono caratteristiche guidate dall'utente. gli amministratori non devono configurare queste funzionalità per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c75b8-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="c75b8-120">I gruppi di chiamata non possono essere creati da gruppi di sicurezza o da gruppi di Microsoft 365. devono essere creati in Teams.</span><span class="sxs-lookup"><span data-stu-id="c75b8-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="c75b8-121">Gli amministratori devono abilitare i gruppi di chiamate tramite **l'impostazione TeamsCallingPolicy AllowCallGroups per** un utente.</span><span class="sxs-lookup"><span data-stu-id="c75b8-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="c75b8-122">Gli amministratori possono abilitarla anche tramite il portale di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="c75b8-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="c75b8-123">Inoltre, l'utente configurato può anche configurare i gruppi di chiamate direttamente dal client.</span><span class="sxs-lookup"><span data-stu-id="c75b8-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="c75b8-124">Gli amministratori o gli utenti finali non possono bloccare la configurazione reciproca, ma il portale di amministrazione di Teams e il client di Teams devono mostrare questa relazione in modo accurato in entrambe le posizioni.</span><span class="sxs-lookup"><span data-stu-id="c75b8-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="c75b8-125">Importante: quando gli amministratori disattivano i gruppi di chiamate per gli utenti (dopo l'attivazione e la configurazione delle relazioni tra i gruppi di chiamate), gli amministratori devono pulire le relazioni del gruppo di chiamate per gli utenti nell'interfaccia di amministrazione di Teams per evitare un instradamento non corretto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="c75b8-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="c75b8-126">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="c75b8-126">Limitations</span></span>

<span data-ttu-id="c75b8-127">Un tenant può contenere un massimo di 32.768 gruppi di chiamate.</span><span class="sxs-lookup"><span data-stu-id="c75b8-127">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="c75b8-128">In ogni gruppo di chiamate possono essere presenti al massimo 25 utenti.</span><span class="sxs-lookup"><span data-stu-id="c75b8-128">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="c75b8-129">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="c75b8-129">More information</span></span>

[<span data-ttu-id="c75b8-130">Inoltro di chiamata e squillo simultaneo in Teams</span><span class="sxs-lookup"><span data-stu-id="c75b8-130">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
