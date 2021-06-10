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
description: Guida introduttiva per la configurazione dei piani di chiamata in Microsoft Teams per consentire l'avvio e l'esecuzione di un set di utenti.
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
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="56673-103">Guida introduttiva: Configurazione dei piani di chiamata su Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="56673-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="56673-104">Questa guida ti aiuterà a far entrare in funzione un set di utenti in modo che possano esplorare i Piani per chiamate in Teams.</span><span class="sxs-lookup"><span data-stu-id="56673-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="56673-105">Leggi l'annuncio del 12 dicembre 2017 dei Piani per chiamate in Teams: Intelligent Communications fa il prossimo passo con [le chiamate in Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="56673-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="56673-106">In parallelo a questa guida introduttiva, è [](calling-plan-landing-page.md) consigliabile leggere Sistema telefonico piani per chiamate e [FastTrack](https://aka.ms/cloudvoice) per pianificare e guidare un'implementazione corretta.</span><span class="sxs-lookup"><span data-stu-id="56673-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="56673-107">Con l'aggiunta di Piani per le chiamate, una funzionalità di Microsoft 365 e Office 365 basata su Skype for Business, ora è possibile usare Teams per effettuare e ricevere chiamate telefoniche da o verso linee di terra e telefoni cellulari tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="56673-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Schermata che mostra la pagina Contatti in Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="56673-109">Prerequisiti per l'abilitazione **della scheda** Chiamate in Teams</span><span class="sxs-lookup"><span data-stu-id="56673-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="56673-110">Per abilitare  la scheda Chiamate in Teams gli utenti devono avere le chiamate 1:1 abilitate in Teams e usare un client Teams che supporta le chiamate 1:1 Teams chiamate.</span><span class="sxs-lookup"><span data-stu-id="56673-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="56673-111">Per informazioni su come gestire le chiamate 1:1 in Teams, vedere [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="56673-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="56673-112">Per informazioni sui client che supportano le chiamate, leggere [Limiti e specifiche per](./limits-specifications-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="56673-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="56673-113">Attualmente, la segreteria telefonica non sarà disponibile nella scheda Chiamate a meno che l'utente non sia abilitato per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="56673-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="56673-114">Prerequisiti per l'abilitazione **della tastiera del** telefono in Teams</span><span class="sxs-lookup"><span data-stu-id="56673-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="56673-115">Per abilitare la **scheda** Tastiera del telefono in Teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario effettuare il provisioning degli utenti per i piani Sistema telefonico chiamate.</span><span class="sxs-lookup"><span data-stu-id="56673-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="56673-116">Per informazioni su come configurare i piani per chiamate, vedere [Configurare i piani per chiamate.](./set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="56673-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="56673-117">Inoltre, per Teams solo gli utenti, è necessario assicurarsi che "Consenti chiamate private" sia abilitato nel criterio Teams chiamate.</span><span class="sxs-lookup"><span data-stu-id="56673-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="56673-118">Per altre Teams, vedere Gestire i Teams durante la transizione alla nuova [interfaccia Microsoft Teams di amministrazione.](./manage-teams-skypeforbusiness-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="56673-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="56673-119">È anche possibile usare Il routing diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="56673-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="56673-120">Per informazioni su come configurare il routing diretto, vedere [Configurare il routing diretto.](./direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="56673-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="56673-121">Uso di TeamsUpgradePolicy per controllare dove atterrano le chiamate</span><span class="sxs-lookup"><span data-stu-id="56673-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="56673-122">Per controllare se le chiamate in arrivo (e le chat) atterrano in Teams o Skype for Business, gli amministratori usano TeamsUpgradePolicy, usando l'interfaccia di amministrazione di [Microsoft Teams](https://aka.ms/teamsadmincenter) o una sessione di Windows PowerShell remota con i cmdlet [Skype for Business.](/powershell/module/skype)</span><span class="sxs-lookup"><span data-stu-id="56673-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="56673-123">La configurazione predefinita di TeamsUpgradePolicy è la modalità Isole, progettata per garantire che i flussi di lavoro aziendali esistenti non siano interrotti durante una Teams distribuzione.</span><span class="sxs-lookup"><span data-stu-id="56673-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="56673-124">Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for Business finché non si aggiorna il criterio per abilitare le chiamate in ingresso a Teams.</span><span class="sxs-lookup"><span data-stu-id="56673-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="56673-125">Quando i destinatari sono in modalità isole:</span><span class="sxs-lookup"><span data-stu-id="56673-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="56673-126">Le chiamate VOIP in arrivo originate Skype for Business sempre nel client Skype for Business destinatario.</span><span class="sxs-lookup"><span data-stu-id="56673-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="56673-127">Le chiamate VOIP in arrivo originate in Teams atterrano in Teams, se il mittente e il destinatario sono *nello stesso tenant.*</span><span class="sxs-lookup"><span data-stu-id="56673-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="56673-128">Le chiamate VOIP federate in arrivo (indipendentemente dal client di origine) e le chiamate PSTN vengono sempre effettuate nel client Skype for Business destinatario.</span><span class="sxs-lookup"><span data-stu-id="56673-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="56673-129">Per assicurarsi che le chiamate VOIP e PSTN in arrivo siano sempre presenti nel client Teams di un utente, aggiornare la modalità di coesistenza dell'utente in TeamsOnly, ovvero assegnarle l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="56673-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="56673-130">Per altre informazioni sulle modalità di coesistenza e TeamsUpgradePolicy, vedere Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams [insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="56673-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="56673-131">**NOTE**</span><span class="sxs-lookup"><span data-stu-id="56673-131">**NOTES**</span></span>
 - <span data-ttu-id="56673-132">Skype for Business I telefoni IP riceveranno chiamate, anche se l'utente è in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="56673-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="56673-133">Gli utenti a cui è stato eseguito il provisioning con licenze di Sistema telefonico e Piani per chiamate per l'uso con Skype for Business Online (ad esempio, a cui è stato assegnato il valore OnlineVoiceRoutingPolicy) avranno la scheda Chiamate abilitata in Teams e potranno effettuare chiamate PSTN in uscita da Teams senza che gli amministratori possano eseguire alcuna azione amministrativa.</span><span class="sxs-lookup"><span data-stu-id="56673-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="56673-134">Come configurare gli utenti in modo che ricevano tutte le chiamate VOIP e PSTN in Teams</span><span class="sxs-lookup"><span data-stu-id="56673-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="56673-135">Per assicurarsi che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in Teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft Teams oppure usare una sessione di Windows PowerShell remota Skype for Business per aggiornare TeamsUpgradePolicy nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="56673-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="56673-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56673-136">See also</span></span>
[<span data-ttu-id="56673-137">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="56673-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="56673-138">Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="56673-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="56673-139">Phone System e Piani di Chiamata</span><span class="sxs-lookup"><span data-stu-id="56673-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="56673-140">Skype for Business Informazioni di riferimento sul cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="56673-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)