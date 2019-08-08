---
title: Guida introduttiva-configurazione di piani di chiamata in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Guida introduttiva per la configurazione dei piani per le chiamate in Microsoft teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e043633749e0ef2dba41b5b3b18776cfbe1c497
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236855"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="49236-103">Guida introduttiva: configurazione di piani di chiamata in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49236-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="49236-104">Questa guida consentirà di velocizzare l'uso di un gruppo di utenti in modo che possano esplorare i piani di chiamata in teams.</span><span class="sxs-lookup"><span data-stu-id="49236-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="49236-105">Leggere il 12 dicembre 2017, annuncio dei piani di chiamata in teams: [le comunicazioni intelligenti richiedono il passaggio successivo con le chiamate in teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="49236-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="49236-106">È consigliabile, in parallelo con questa Guida introduttiva, leggere il [sistema telefonico con i piani](calling-plan-landing-page.md) per le chiamate e [FastTrack](https://aka.ms/cloudvoice) per pianificare e guidare un implementazione di successo.</span><span class="sxs-lookup"><span data-stu-id="49236-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="49236-107">Con l'aggiunta di piani di chiamata-una funzionalità di Office 365 alimentata da Skype for business-ora è possibile usare team per effettuare e ricevere chiamate telefoniche da o verso linee terrestri e telefoni cellulari tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="49236-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Screenshot che mostra la pagina dei contatti in teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="49236-109">Prerequisiti per l'abilitazione della scheda **chiamate** in teams</span><span class="sxs-lookup"><span data-stu-id="49236-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="49236-110">Per abilitare la scheda **chiamate** in teams gli utenti devono avere la chiamata di 1:1 abilitata in teams e l'uso di un client teams che supporta 1:1 Teams Calling.</span><span class="sxs-lookup"><span data-stu-id="49236-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="49236-111">Per informazioni su come gestire la chiamata di 1:1 in teams, leggere [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="49236-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="49236-112">Per informazioni sui clienti che supportano la chiamata, leggere i [limiti e le specifiche per Microsoft teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="49236-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="49236-113">Attualmente, la segreteria telefonica non sarà disponibile nella scheda chiamate, a meno che l'utente non sia abilitato per le chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="49236-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="49236-114">Prerequisiti per l'abilitazione della **tastiera del telefono** in teams</span><span class="sxs-lookup"><span data-stu-id="49236-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="49236-115">Per abilitare la scheda **tastiera** del telefono in teams e consentire agli utenti di effettuare e ricevere chiamate PSTN, è necessario eseguire il provisioning degli utenti per il sistema telefonico e per i piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="49236-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="49236-116">Per informazioni su come configurare i piani per le chiamate, vedere [configurare i piani](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="49236-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="49236-117">È anche possibile usare il routing diretto per consentire agli utenti di effettuare e ricevere chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="49236-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="49236-118">Per informazioni su come configurare il routing diretto, vedere [configurare il routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="49236-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="49236-119">Uso di TeamsUpgradePolicy per controllare la posizione delle chiamate</span><span class="sxs-lookup"><span data-stu-id="49236-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="49236-120">Per controllare se le chiamate in arrivo (e le chat) atterrano in teams o in Skype for business, gli amministratori usano TeamsUpgradePolicy, usando l'interfaccia di [amministrazione di Microsoft teams](https://aka.ms/teamsadmincenter) o usando una sessione remota di Windows PowerShell con [Skype for business](https://docs.microsoft.com/powershell/module/skype) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="49236-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="49236-121">La configurazione predefinita di TeamsUpgradePolicy è la modalità Islands, progettata per garantire che i flussi di lavoro aziendali esistenti non vengano interrotti durante la distribuzione di team.</span><span class="sxs-lookup"><span data-stu-id="49236-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="49236-122">Per impostazione predefinita, le chiamate VoIP, PSTN e federate agli utenti continueranno a essere instradate a Skype for business finché non si aggiorna il criterio per abilitare la chiamata in ingresso ai team.</span><span class="sxs-lookup"><span data-stu-id="49236-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="49236-123">Quando i destinatari sono in modalità isole:</span><span class="sxs-lookup"><span data-stu-id="49236-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="49236-124">Le chiamate VOIP in arrivo che sono state originate in Skype for business sempre atterrano nel client Skype for business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="49236-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="49236-125">Le chiamate VOIP in arrivo originate in teams atterrano in teams, *se il mittente e il destinatario si trovano nello stesso tenant*.</span><span class="sxs-lookup"><span data-stu-id="49236-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="49236-126">VOIP federativo in arrivo (indipendentemente dal cliente che ha origine) e chiamate PSTN sempre atterrano nel client Skype for business del destinatario.</span><span class="sxs-lookup"><span data-stu-id="49236-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="49236-127">Per fare in modo che le chiamate VOIP e PSTN in arrivo siano sempre presenti nel client teams di un utente, aggiornare la modalità di coesistenza dell'utente in modo che sia TeamsOnly, assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="49236-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="49236-128">Per altre informazioni sulle modalità di coesistenza e TeamsUpgradePolicy, Vedi [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="49236-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="49236-129">**Note**</span><span class="sxs-lookup"><span data-stu-id="49236-129">**NOTES**</span></span>
 - <span data-ttu-id="49236-130">I telefoni IP di Skype for Business riceveranno le chiamate, anche se l'utente è in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="49236-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="49236-131">Gli utenti che hanno effettuato il provisioning con le licenze per il sistema telefonico e i piani di chiamata per l'uso con Skype for business online (ad esempio, hanno assegnato un valore di OnlineVoiceRoutingPolicy), avranno attivato la scheda chiamate in teams e potranno inserire chiamate PSTN in uscita da I team senza amministratori che devono eseguire qualsiasi azione amministrativa.</span><span class="sxs-lookup"><span data-stu-id="49236-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="49236-132">Come configurare gli utenti per ricevere tutte le chiamate VOIP e PSTN in arrivo in teams</span><span class="sxs-lookup"><span data-stu-id="49236-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="49236-133">Per assicurarsi che gli utenti ricevano tutte le chiamate VOIP e PSTN in arrivo in teams, impostare la modalità di coesistenza dell'utente su TeamsOnly nell'interfaccia di amministrazione di Microsoft teams oppure usare la sessione remota di Windows PowerShell di Skype for business per aggiornare TeamsUpgradePolicy come segue:</span><span class="sxs-lookup"><span data-stu-id="49236-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="49236-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49236-134">See also</span></span>
[<span data-ttu-id="49236-135">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="49236-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="49236-136">Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business</span><span class="sxs-lookup"><span data-stu-id="49236-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="49236-137">Sistema telefonico con piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="49236-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="49236-138">Informazioni di riferimento sui cmdlet di PowerShell per Skype for business</span><span class="sxs-lookup"><span data-stu-id="49236-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

