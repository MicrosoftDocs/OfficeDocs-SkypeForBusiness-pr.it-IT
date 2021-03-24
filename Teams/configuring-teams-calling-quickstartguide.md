---
title: Guida introduttiva - Configurazione dei piani per chiamate
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guida introduttiva per la configurazione dei piani di chiamata in Microsoft Teams per consentire l'avvio di un set di utenti.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101182"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="322ec-103">Guida introduttiva: Configurazione dei piani di chiamata su Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="322ec-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="322ec-104">Questa guida ti aiuterà a far entrare in funzione un set di utenti in modo che possano esplorare i Piani per le chiamate in Teams.</span><span class="sxs-lookup"><span data-stu-id="322ec-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="322ec-105">Leggi l'annuncio del 12 dicembre 2017 dei piani per chiamate [in Teams: Intelligent Communications](https://aka.ms/ipyqus) fa il prossimo passo con le chiamate in Teams</span><span class="sxs-lookup"><span data-stu-id="322ec-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="322ec-106">In parallelo a questa guida introduttiva, è [](calling-plan-landing-page.md) consigliabile leggere Sistema telefonico con piani per chiamate e [FastTrack](https://aka.ms/cloudvoice) per pianificare e guidare un'implementazione corretta.</span><span class="sxs-lookup"><span data-stu-id="322ec-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="322ec-107">Con l'aggiunta di Piani per le chiamate, una funzionalità di Microsoft 365 e Office 365 basata su Skype for Business, è ora possibile usare Teams per effettuare e ricevere chiamate telefoniche da o verso linee di terra e telefoni cellulari tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="322ec-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Schermata che mostra la pagina Contatti in Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="322ec-109">Prerequisiti per l'abilitazione **della scheda** Chiamate in Teams</span><span class="sxs-lookup"><span data-stu-id="322ec-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="322ec-110">Per abilitare la **scheda** Chiamate in Teams, gli utenti devono avere le chiamate 1:1 abilitate in Teams e usare un client teams che supporta le chiamate 1:1 Teams.</span><span class="sxs-lookup"><span data-stu-id="322ec-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="322ec-111">Per informazioni su come gestire le chiamate 1:1 in Teams, vedere [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="322ec-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="322ec-112">Per informazioni sui client che supportano le chiamate, leggere [Limiti e specifiche per Microsoft Teams.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="322ec-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="322ec-113">Attualmente, la segreteria telefonica non sarà disponibile nella scheda Chiamate a meno che l'utente non sia abilitato per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="322ec-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="322ec-114">Prerequisiti per l'abilitazione della **tastiera del** telefono in Teams</span><span class="sxs-lookup"><span data-stu-id="322ec-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="322ec-115">Per abilitare la **scheda Tastiera** del telefono in Teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario effettuare il provisioning degli utenti per Sistema telefonico e Piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="322ec-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="322ec-116">Per informazioni su come configurare i piani per chiamate, vedere [Configurare i piani per chiamate.](./set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="322ec-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="322ec-117">Inoltre, per gli utenti di Teams, è necessario assicurarsi che "Consenti chiamate private" sia abilitato nei criteri di chiamata di Teams.</span><span class="sxs-lookup"><span data-stu-id="322ec-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="322ec-118">Per [altre informazioni, vedere](./manage-teams-skypeforbusiness-admin-center.md) Gestire Teams durante la transizione alla nuova interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="322ec-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="322ec-119">È anche possibile usare Il routing diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="322ec-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="322ec-120">Per informazioni su come configurare il routing diretto, vedere [Configurare il routing diretto.](./direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="322ec-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="322ec-121">Uso di TeamsUpgradePolicy per controllare dove atterrano le chiamate</span><span class="sxs-lookup"><span data-stu-id="322ec-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="322ec-122">Per controllare se le chiamate in arrivo (e le chat) atterrano in Teams o Skype for Business, gli amministratori usano TeamsUpgradePolicy, usando l'interfaccia di amministrazione di [Microsoft Teams](https://aka.ms/teamsadmincenter) o una sessione di Windows PowerShell remota con i cmdlet di Skype [for Business.](/powershell/module/skype)</span><span class="sxs-lookup"><span data-stu-id="322ec-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="322ec-123">La configurazione predefinita di TeamsUpgradePolicy è la modalità Isole, progettata per garantire che i flussi di lavoro aziendali esistenti non siano interrotti durante una distribuzione di Teams.</span><span class="sxs-lookup"><span data-stu-id="322ec-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="322ec-124">Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for Business finché non si aggiorna il criterio per abilitare le chiamate in ingresso a Teams.</span><span class="sxs-lookup"><span data-stu-id="322ec-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="322ec-125">Quando i destinatari sono in modalità isole:</span><span class="sxs-lookup"><span data-stu-id="322ec-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="322ec-126">Le chiamate VOIP in arrivo originate in Skype for Business vengono sempre effettuate nel client Skype for Business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="322ec-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="322ec-127">Le chiamate VOIP in arrivo originate in Teams vengono effettuate in Teams, se il mittente e il destinatario sono *nello stesso tenant.*</span><span class="sxs-lookup"><span data-stu-id="322ec-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="322ec-128">Le chiamate VOIP federate in arrivo (indipendentemente dal client di origine) e le chiamate PSTN vengono sempre effettuate nel client Skype for Business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="322ec-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="322ec-129">Per assicurarsi che le chiamate VOIP e PSTN in arrivo siano sempre presenti nel client Teams di un utente, aggiornare la modalità di coesistenza dell'utente in TeamsOnly, ovvero assegnarle l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="322ec-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="322ec-130">Per altre informazioni sulle modalità di coesistenza e TeamsUpgradePolicy, vedere Indicazioni sulla migrazione e [l'interoperabilità](./migration-interop-guidance-for-teams-with-skype.md) per le organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="322ec-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="322ec-131">**NOTE**</span><span class="sxs-lookup"><span data-stu-id="322ec-131">**NOTES**</span></span>
 - <span data-ttu-id="322ec-132">I telefoni IP Skype for Business riceveranno chiamate, anche se l'utente è in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="322ec-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="322ec-133">Gli utenti a cui è stato eseguito il provisioning con licenze Sistema telefonico e Piani di chiamata per l'uso con Skype for Business Online (ad esempio, a cui è stato assegnato un valore di OnlineVoiceRoutingPolicy), avranno la scheda Chiamate abilitata in Teams e potranno effettuare chiamate PSTN in uscita da Teams senza che gli amministratori devono eseguire alcuna azione amministrativa.</span><span class="sxs-lookup"><span data-stu-id="322ec-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="322ec-134">Come configurare gli utenti per la ricezione di tutte le chiamate VOIP e PSTN in arrivo in Teams</span><span class="sxs-lookup"><span data-stu-id="322ec-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="322ec-135">Per assicurarsi che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in Teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft Teams oppure usare la sessione di Windows PowerShell remota di Skype for Business per aggiornare TeamsUpgradePolicy nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="322ec-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="322ec-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="322ec-136">See also</span></span>
[<span data-ttu-id="322ec-137">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="322ec-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="322ec-138">Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="322ec-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="322ec-139">Phone System e Piani di Chiamata</span><span class="sxs-lookup"><span data-stu-id="322ec-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="322ec-140">Informazioni di riferimento sul cmdlet di PowerShell per Skype for Business</span><span class="sxs-lookup"><span data-stu-id="322ec-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)