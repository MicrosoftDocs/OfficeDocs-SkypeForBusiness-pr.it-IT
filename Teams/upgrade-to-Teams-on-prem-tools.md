---
title: Strumenti per l'aggiornamento a Teams da una distribuzione locale di Skype for Business
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Strumenti per l'aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5585a2d2995b2f7d470c4d07eab3f5bb7f1934c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097502"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="e5ce1-103">Strumenti per l'aggiornamento a Teams &mdash; per amministratori IT</span><span class="sxs-lookup"><span data-stu-id="e5ce1-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="e5ce1-104">Questo articolo descrive gli strumenti per l'aggiornamento a Teams da Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="e5ce1-105">Prima di iniziare l'aggiornamento, Microsoft consiglia gli articoli seguenti che descrivono i concetti importanti per l'aggiornamento e i comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="e5ce1-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="e5ce1-106">Coesistenza di Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e5ce1-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="e5ce1-107">Modalità di coesistenza - Riferimento</span><span class="sxs-lookup"><span data-stu-id="e5ce1-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="e5ce1-108">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="e5ce1-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="e5ce1-109">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e5ce1-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="e5ce1-110">Indipendentemente dal metodo di aggiornamento scelto, per gli utenti che hanno già Skype for Business online, è possibile gestire la transizione a TeamsOnly usando [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)che controlla la modalità di coesistenza di un utente.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="e5ce1-111">Per gli utenti con un account locale in Skype for Business Server, è anche possibile `Move-CsUser` [spostarli nel cloud.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="e5ce1-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="e5ce1-112">Per altre informazioni su ognuna delle modalità, vedere [Modalità di coesistenza.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="e5ce1-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e5ce1-113">Se attualmente si usa Skype for Business Online Connector per gestire i servizi, è necessario passare al modulo di PowerShell di Teams e aggiornare gli script di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="e5ce1-114">Per [altre informazioni, vedere Passare da Skype for Business Online Connector al modulo di PowerShell](teams-powershell-move-from-sfbo.md) di Teams.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="e5ce1-115">TeamsUpgradePolicy è lo strumento principale per gli utenti che hanno già Skype for Business online, sia che tu eserti una transizione di funzionalità selezionate usando le modalità Skype for Business o semplicemente la modalità TeamsOnly dalla configurazione predefinita isole.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="e5ce1-116">Come qualsiasi altro criterio in Teams, è possibile assegnare TeamsUpgradePolicy direttamente a un utente.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-116">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="e5ce1-117">È anche possibile impostare il criterio come predefinito a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-117">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="e5ce1-118">Qualsiasi assegnazione a un utente ha la precedenza sull'impostazione predefinita del tenant.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-118">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="e5ce1-119">È possibile gestire i criteri nella Console di amministrazione di Teams e in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-119">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="e5ce1-120">È anche possibile assegnare qualsiasi modalità di TeamsUpgradePolicy, ad eccezione della modalità TeamsOnly, agli utenti ospitati in Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-120">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="e5ce1-121">**La modalità TeamsOnly può essere assegnata solo a un utente già ospitato in Skype for Business online.**</span><span class="sxs-lookup"><span data-stu-id="e5ce1-121">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="e5ce1-122">Questo perché l'interoperabilità con gli utenti di Skype for Business e la federazione e la funzionalità Sistema telefonico Microsoft 365 sono possibili solo se l'utente è ospitata in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-122">This is because interop with Skype for Business users and federation and Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="e5ce1-123">Inoltre, non è possibile assegnare la modalità **TeamsOnly** come impostazione predefinita a livello di tenant se si ha una distribuzione locale di Skype for Business ,che viene rilevata dalla presenza di un record DNS di lyncdiscover che punta a una posizione diversa da Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-123">In addition, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="e5ce1-124">Gli utenti con account Skype for Business ospitati in locale devono essere spostati [online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (su Skype for Business online o direttamente a Teams) usando Move-CsUser nel set di strumenti locale di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="e5ce1-125">Questi utenti possono essere spostati in TeamsOnly in 1 o 2 passaggi:</span><span class="sxs-lookup"><span data-stu-id="e5ce1-125">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="e5ce1-126">1 passaggio: specificare l'opzione -MoveToTeams in Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-126">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="e5ce1-127">Questa operazione richiede Skype for Business Server 2019 o Skype for Business Server 2015 con CU8 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-127">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="e5ce1-128">2 passaggi: dopo aver eseguito Move-CsUser, concedere la modalità TeamsOnly all'utente usando TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-128">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="e5ce1-129">A differenza di altri criteri, non è possibile creare nuove istanze di TeamsUpgradePolicy in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-129">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e5ce1-130">Tutte le istanze esistenti sono incorporate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-130">All the existing instances are built into the service.</span></span>  <span data-ttu-id="e5ce1-131">Si noti che la modalità è una proprietà all'interno di TeamsUpgradePolicy, anziché il nome di un'istanza dei criteri. In alcuni casi, ma non in tutti, il nome dell'istanza dei criteri corrisponde alla modalità.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-131">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="e5ce1-132">In particolare, per assegnare la modalità TeamsOnly a un utente, si concede l'istanza "UpgradeToTeams" di TeamsUpgradePolicy a tale utente.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-132">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="e5ce1-133">Per visualizzare un elenco di tutte le istanze, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e5ce1-133">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="e5ce1-134">Per aggiornare un utente online alla modalità TeamsOnly, assegnare l'istanza "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="e5ce1-134">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="e5ce1-135">Per aggiornare un utente Skype for Business locale alla modalità TeamsOnly, Move-CsUser nel set di strumenti locale:</span><span class="sxs-lookup"><span data-stu-id="e5ce1-135">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="e5ce1-136">Per cambiare la modalità per tutti gli utenti del tenant, ad eccezione di quelli che hanno una concessione esplicita per utente (che ha la precedenza), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e5ce1-136">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="e5ce1-137">Se si hanno utenti con account Skype for Business locali, non è possibile assegnare la modalità TeamsOnly a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-137">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="e5ce1-138">È necessario spostare questi utenti singolarmente nel cloud usando Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-138">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="e5ce1-139">Uso delle notifiche nei client Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e5ce1-139">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="e5ce1-140">Gli amministratori hanno la possibilità di fornire notifiche agli utenti finali nel client Skype for Business per informare gli utenti che presto verranno aggiornati a Teams, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-140">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="e5ce1-141">Ad esempio, una settimana prima che l'amministratore pianichi di aggiornare un gruppo di utenti alla modalità TeamsOnly, l'amministratore potrebbe voler attivare queste notifiche per quel gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-141">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="e5ce1-142">Queste notifiche vengono abilitate usando un'istanza di TeamsUpgradePolicy con NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-142">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="e5ce1-143">Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, corrispondenti ai due valori di NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-143">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="e5ce1-144">Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, corrispondenti ai due valori di NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagramma che mostra le notifiche](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="e5ce1-146">Se gli utenti sono ospitati in Skype for Business online, è sufficiente assegnare l'istanza del criterio che ha la stessa modalità dell'utente, ma con NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-146">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="e5ce1-147">Se gli utenti sono ospitati in Skype for Business Server locale, sarà necessario usare il set di strumenti locale e sarà necessario Skype for Business Server 2019 o CU8 per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-147">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="e5ce1-148">Per gli utenti ospitati in Skype for Business Server locale, viene rispettata la proprietà mode dell'istanza online di TeamsUpgradePolicy, ma la proprietà NotifySfbUsers non lo è.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-148">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="e5ce1-149">Se si desidera ricevere notifiche, è necessario creare un'istanza locale di TeamsUpgradePolicy per controllare il comportamento del client.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-149">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="e5ce1-150">Nella finestra di PowerShell locale creare una nuova istanza di TeamsUpgradePolicy con NotifySfbUsers=true:</span><span class="sxs-lookup"><span data-stu-id="e5ce1-150">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="e5ce1-151">Quindi, usando la stessa finestra di PowerShell locale, assegnare il nuovo criterio agli utenti desiderati:</span><span class="sxs-lookup"><span data-stu-id="e5ce1-151">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="e5ce1-152">Migrazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="e5ce1-152">Meeting migration</span></span>

<span data-ttu-id="e5ce1-153">Quando un utente viene migrato in modalità TeamsOnly, per impostazione predefinita le riunioni Skype for Business esistenti che hanno organizzato verranno convertite in Teams.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-153">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="e5ce1-154">Facoltativamente, è possibile disabilitare il comportamento predefinito quando si assegna la modalità TeamsOnly a un utente.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-154">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="e5ce1-155">Quando si spostano utenti dall'ambiente locale, è necessario eseguire la migrazione delle riunioni nel cloud per funzionare con l'account utente online, ma se non si specifica -MoveToTeams, le riunioni verranno migrate come riunioni Skype for Business anziché convertite in Teams.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-155">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="e5ce1-156">Quando si assegna la modalità TeamsOnly a livello di tenant, la migrazione delle riunioni non viene attivata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-156">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="e5ce1-157">Se si vuole assegnare la modalità TeamsOnly a livello di tenant ed eseguire la migrazione delle riunioni, è possibile usare PowerShell per ottenere un elenco di utenti nel tenant , ad esempio usando Get-CsOnlineUser con tutti i filtri necessari, e quindi scorrere ognuno di questi utenti per avviare la migrazione delle riunioni con Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="e5ce1-157">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="e5ce1-158">Per informazioni dettagliate, vedere [Uso del servizio di migrazione delle riunioni (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="e5ce1-158">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="e5ce1-159">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="e5ce1-159">Related links</span></span>

[<span data-ttu-id="e5ce1-160">Modalità di coesistenza - Riferimento</span><span class="sxs-lookup"><span data-stu-id="e5ce1-160">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="e5ce1-161">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="e5ce1-161">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="e5ce1-162">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="e5ce1-162">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="e5ce1-163">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e5ce1-163">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="e5ce1-164">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e5ce1-164">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="e5ce1-165">Uso del servizio di migrazione delle riunioni (MMS)</span><span class="sxs-lookup"><span data-stu-id="e5ce1-165">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)