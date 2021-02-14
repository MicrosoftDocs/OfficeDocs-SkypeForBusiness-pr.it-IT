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
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620722"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="d57da-103">Condivisione delle chiamate e ritiro di chiamate di gruppo in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d57da-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="d57da-104">Le funzionalità di condivisione delle chiamate e di ritiro chiamate di gruppo di Microsoft Teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano quando l'utente non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d57da-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="d57da-105">Il ritiro di una chiamata di gruppo è meno disturbante per i destinatari rispetto ad altre forme di condivisione delle chiamate (come l'inoltro di chiamata o lo squillo simultaneo), perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visivo o banner nell'app di Teams) e possono decidere se rispondere.</span><span class="sxs-lookup"><span data-stu-id="d57da-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="d57da-106">Per condividere le chiamate con altri utenti, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vogliono condividere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="d57da-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="d57da-107">Quindi sceglie un'impostazione di inoltro o squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="d57da-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="d57da-108">Per [informazioni dettagliate, vedere Inoltro di chiamata e squillo simultaneo in Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="d57da-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="d57da-109">Tieni presente che i dispositivi mobili riceveranno una notifica solo se sono impostati per banner e suonerie.</span><span class="sxs-lookup"><span data-stu-id="d57da-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d57da-110">Gli utenti, il proprietario del gruppo di chiamata e i membri del gruppo di chiamata devono essere in modalità di distribuzione solo di Teams.</span><span class="sxs-lookup"><span data-stu-id="d57da-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="d57da-111">Per maggiori dettagli sulle modalità di distribuzione di Teams, consulta Informazioni sulla coesistenza e [l'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) di Microsoft Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d57da-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="d57da-112">Licenza richiesta</span><span class="sxs-lookup"><span data-stu-id="d57da-112">License required</span></span>

<span data-ttu-id="d57da-113">Gli utenti devono essere VoIP aziendale abilitati per configurare e usare la condivisione delle chiamate e il ritiro delle chiamate di gruppo.</span><span class="sxs-lookup"><span data-stu-id="d57da-113">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="d57da-114">Per ulteriori dettagli sul modello di licenza, vedere la descrizione [del servizio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="d57da-114">For additional details on the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="d57da-115">Configurare il ritiro delle chiamate di gruppo</span><span class="sxs-lookup"><span data-stu-id="d57da-115">Configure group call pickup</span></span>

<span data-ttu-id="d57da-116">Per impostare il ritiro delle chiamate di gruppo, un utente configura prima un gruppo di chiamata (non corrisponde a un gruppo di sicurezza o a un gruppo di Microsoft 365) e quindi aggiunge gli utenti con cui vuole condividere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="d57da-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="d57da-117">In questo modo sceglie un'impostazione per lo squillo o l'inoltro di chiamata simultaneo.</span><span class="sxs-lookup"><span data-stu-id="d57da-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="d57da-118">Per altre informazioni e procedure dettagliate, vedere Inoltro di chiamata e [squillo simultaneo in Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="d57da-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="d57da-119">Le preferenze per la creazione di gruppi di chiamate e le notifiche sono caratteristiche guidate dall'utente; gli amministratori non devono configurare queste caratteristiche per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d57da-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="d57da-120">Non è possibile creare gruppi di chiamate da gruppi di sicurezza o gruppi di Microsoft 365; devono essere create in Teams.</span><span class="sxs-lookup"><span data-stu-id="d57da-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="d57da-121">Gli amministratori devono abilitare i gruppi di chiamata tramite **l'impostazione AllowCallingPolicy AllowCallGroups** per un utente.</span><span class="sxs-lookup"><span data-stu-id="d57da-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="d57da-122">Gli amministratori possono anche abilitare questa funzionalità tramite il portale di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="d57da-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="d57da-123">Inoltre, l'utente configurato può anche configurare i propri gruppi di chiamate direttamente dal client.</span><span class="sxs-lookup"><span data-stu-id="d57da-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="d57da-124">Gli amministratori o gli utenti finali non possono bloccare la configurazione tra loro, ma il portale di amministrazione di Teams e il client di Teams devono mostrare questa relazione in modo accurato in entrambe le posizioni.</span><span class="sxs-lookup"><span data-stu-id="d57da-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="d57da-125">Importante: quando gli amministratori disattivano i gruppi di chiamata per gli utenti (dopo l'attivazione e aver configurato le relazioni tra gruppi di chiamate), gli amministratori devono pulire le relazioni dei gruppi di chiamata per gli utenti nell'interfaccia di amministrazione di Teams per evitare un instradamento errato delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="d57da-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="d57da-126">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="d57da-126">Limitations</span></span>

<span data-ttu-id="d57da-127">Un tenant può contenere al massimo 32.768 gruppi di chiamate.</span><span class="sxs-lookup"><span data-stu-id="d57da-127">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="d57da-128">Ogni gruppo di chiamata può contenere al massimo 25 utenti.</span><span class="sxs-lookup"><span data-stu-id="d57da-128">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="d57da-129">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="d57da-129">More information</span></span>

[<span data-ttu-id="d57da-130">Inoltro di chiamata e squillo simultaneo in Teams</span><span class="sxs-lookup"><span data-stu-id="d57da-130">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
