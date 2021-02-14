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
description: Guida introduttiva per la configurazione di piani per chiamate in Microsoft Teams per consentire l'esecuzione di un set di utenti.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799766"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="a87ad-103">Guida introduttiva: Configurazione dei piani di chiamata su Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a87ad-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="a87ad-104">Questa guida ti aiuterà a far iniziare un set di utenti in modo che possano esplorare i Piani per chiamate in Teams.</span><span class="sxs-lookup"><span data-stu-id="a87ad-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="a87ad-105">Leggere l'annuncio dei piani per chiamate in Teams del 12 dicembre 2017: La comunicazione intelligente fa il passo successivo con [le chiamate in Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="a87ad-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="a87ad-106">Si consiglia di leggere, in parallelo, questa [](calling-plan-landing-page.md) guida introduttiva sistema telefonico con piani per chiamate e [FastTrack](https://aka.ms/cloudvoice) per pianificare e guidare un'implementazione corretta.</span><span class="sxs-lookup"><span data-stu-id="a87ad-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="a87ad-107">Con l'aggiunta di Piani per chiamate, una funzionalità di Microsoft 365 e Office 365 basata su Skype for Business, è ora possibile utilizzare Teams per effettuare e ricevere chiamate da e verso rete fissa e cellulari tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="a87ad-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Schermata che mostra la pagina Contatti in Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="a87ad-109">Prerequisiti per l'abilitazione **della scheda** Chiamate in Teams</span><span class="sxs-lookup"><span data-stu-id="a87ad-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="a87ad-110">Per abilitare la **scheda** Chiamate in Teams, gli utenti devono avere le chiamate 1:1 abilitate in Teams e l'uso di un client Teams che supporta le chiamate 1:1 Teams.</span><span class="sxs-lookup"><span data-stu-id="a87ad-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="a87ad-111">Per informazioni su come gestire le chiamate 1:1 in Teams, leggi [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a87ad-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="a87ad-112">Per informazioni sui client che supportano le chiamate, leggere [limiti e specifiche per Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)</span><span class="sxs-lookup"><span data-stu-id="a87ad-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="a87ad-113">Attualmente, la segreteria telefonica non sarà disponibile nella scheda Chiamate a meno che l'utente non sia abilitato per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="a87ad-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="a87ad-114">Prerequisiti per l'abilitazione della **tastiera del** telefono in Teams</span><span class="sxs-lookup"><span data-stu-id="a87ad-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="a87ad-115">Per abilitare la **scheda della tastiera** del telefono in Teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario effettuare il provisioning degli utenti per Sistema telefonico e Piani per chiamate.</span><span class="sxs-lookup"><span data-stu-id="a87ad-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="a87ad-116">Per informazioni su come configurare i Piani per chiamate, vedere [Configurare i Piani per chiamate.](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="a87ad-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="a87ad-117">Inoltre, per gli utenti di Teams, è necessario assicurarsi che l'opzione "Consenti chiamate private" sia abilitata nel criterio di chiamata di Teams.</span><span class="sxs-lookup"><span data-stu-id="a87ad-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="a87ad-118">Per [altre informazioni, vedere](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) Gestire Teams durante la transizione alla nuova interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a87ad-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="a87ad-119">È anche possibile usare l'instradamento diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="a87ad-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="a87ad-120">Per informazioni su come configurare il routing diretto, vedere [Configurare il routing diretto.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)</span><span class="sxs-lookup"><span data-stu-id="a87ad-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="a87ad-121">Uso di TeamsUpgradePolicy per controllare l'arrivo delle chiamate</span><span class="sxs-lookup"><span data-stu-id="a87ad-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="a87ad-122">Per controllare se le chiamate in arrivo (e le chat) vengono effettuate in Teams o Skype for Business, gli amministratori usano TeamsUpgradePolicy, utilizzando l'interfaccia di amministrazione di [Microsoft Teams](https://aka.ms/teamsadmincenter) o una sessione di Windows PowerShell remota con i cmdlet di Skype [for Business.](https://docs.microsoft.com/powershell/module/skype)</span><span class="sxs-lookup"><span data-stu-id="a87ad-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="a87ad-123">La configurazione predefinita di TeamsUpgradePolicy è la modalità Isole, che è progettata per garantire che i flussi di lavoro aziendali esistenti non si interruppeno durante una distribuzione di Teams.</span><span class="sxs-lookup"><span data-stu-id="a87ad-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="a87ad-124">Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for Business fino a quando non si aggiorna il criterio per abilitare le chiamate in ingresso a Teams.</span><span class="sxs-lookup"><span data-stu-id="a87ad-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="a87ad-125">Quando i destinatari sono in modalità isole:</span><span class="sxs-lookup"><span data-stu-id="a87ad-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="a87ad-126">Le chiamate VOIP in arrivo provenienti da Skype for Business vengono sempre effettuate nel client Skype for Business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="a87ad-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="a87ad-127">Le chiamate VOIP in arrivo provenienti da Teams vengono effettuate in Teams, se il mittente e il destinatario *sono nello stesso tenant.*</span><span class="sxs-lookup"><span data-stu-id="a87ad-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="a87ad-128">Le chiamate VOIP federate in arrivo (indipendentemente dal client di origine) e le chiamate PSTN vengono sempre effettuate nel client Skype for Business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="a87ad-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="a87ad-129">Per fare in modo che le chiamate VOIP e PSTN in arrivo siano sempre effettuate nel client Teams di un utente, aggiornare la modalità di coesistenza dell'utente in modo che sia TeamsOnly (quindi assegnargli l'istanza "UpgradeToTeams" di TeamsUpgradePolicy).</span><span class="sxs-lookup"><span data-stu-id="a87ad-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="a87ad-130">Per ulteriori informazioni sulle modalità di coesistenza e su TeamsUpgradePolicy, consulta le indicazioni sulla migrazione e [l'interoperabilità](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) per le organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a87ad-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="a87ad-131">**NOTE**</span><span class="sxs-lookup"><span data-stu-id="a87ad-131">**NOTES**</span></span>
 - <span data-ttu-id="a87ad-132">I telefoni IP di Skype for Business riceveranno le chiamate, anche se l'utente è in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="a87ad-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="a87ad-133">Gli utenti che hanno effettuato il provisioning con licenze Sistema telefonico e Piani per chiamate per l'uso con Skype for Business online (ad esempio, a cui è stato assegnato un valore OnlineVoiceRoutingPolicy), avranno la scheda Chiamate abilitata in Teams e possono effettuare chiamate PSTN in uscita da Teams senza che gli amministratori devono eseguire alcuna azione amministrativa.</span><span class="sxs-lookup"><span data-stu-id="a87ad-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="a87ad-134">Come configurare gli utenti per la ricezione di tutte le chiamate VOIP e PSTN in arrivo in Teams</span><span class="sxs-lookup"><span data-stu-id="a87ad-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="a87ad-135">Per assicurare che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in Teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft Teams oppure usare la sessione di Windows PowerShell remota di Skype for Business per aggiornare TeamsUpgradePolicy come segue:</span><span class="sxs-lookup"><span data-stu-id="a87ad-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="a87ad-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a87ad-136">See also</span></span>
[<span data-ttu-id="a87ad-137">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="a87ad-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="a87ad-138">Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a87ad-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="a87ad-139">Phone System e Piani di Chiamata</span><span class="sxs-lookup"><span data-stu-id="a87ad-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="a87ad-140">Informazioni di riferimento per i cmdlet di PowerShell per Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a87ad-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

