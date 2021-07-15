---
title: Strumenti per l'aggiornamento a Teams da una distribuzione Skype for Business locale
author: dstrome
ms.author: dstrome
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
ms.openlocfilehash: 677f642bdb940706079370635a5aa9eec87241fb
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437633"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="ea72c-103">Strumenti per l'aggiornamento a Teams &mdash; per gli amministratori IT</span><span class="sxs-lookup"><span data-stu-id="ea72c-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="ea72c-104">Questo articolo descrive gli strumenti per l'aggiornamento a Teams da Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ea72c-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="ea72c-105">Prima di iniziare l'aggiornamento, Microsoft consiglia gli articoli seguenti che descrivono i concetti importanti per l'aggiornamento e i comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="ea72c-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="ea72c-106">Coesistenza di Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea72c-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="ea72c-107">Modalità di coesistenza - Riferimento</span><span class="sxs-lookup"><span data-stu-id="ea72c-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="ea72c-108">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="ea72c-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="ea72c-109">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ea72c-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="ea72c-110">Indipendentemente dal metodo di aggiornamento scelto, per gli utenti che hanno già Skype for Business Online, è possibile gestire la transizione a TeamsOnly usando [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)che controlla la modalità di coesistenza di un utente.</span><span class="sxs-lookup"><span data-stu-id="ea72c-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="ea72c-111">Per gli utenti con un account locale in Skype for Business Server, è anche possibile `Move-CsUser` [spostarli nel cloud.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="ea72c-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="ea72c-112">Per altre informazioni su ognuna delle modalità, vedere [Modalità di coesistenza.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="ea72c-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ea72c-113">Se attualmente si usa Skype for Business Online Connector per gestire i servizi, è necessario passare al modulo di PowerShell di Teams e aggiornare gli script di PowerShell esistenti.</span><span class="sxs-lookup"><span data-stu-id="ea72c-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="ea72c-114">Per altre informazioni, vedere Passare [da Skype for Business Online Connector al Teams di PowerShell.](teams-powershell-move-from-sfbo.md)</span><span class="sxs-lookup"><span data-stu-id="ea72c-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="ea72c-115">TeamsUpgradePolicy è lo strumento principale per eseguire una transizione delle funzionalità selezionate usando le modalità di Skype for Business o semplicemente eseguire l'aggiornamento alla modalità TeamsOnly dalla configurazione predefinita isole. Come qualsiasi altro criterio in Teams, è possibile assegnare TeamsUpgradePolicy direttamente a un utente.</span><span class="sxs-lookup"><span data-stu-id="ea72c-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="ea72c-116">È anche possibile impostare il criterio come predefinito a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="ea72c-116">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="ea72c-117">Qualsiasi assegnazione a un utente ha la precedenza sull'impostazione predefinita del tenant.</span><span class="sxs-lookup"><span data-stu-id="ea72c-117">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="ea72c-118">È possibile gestire i criteri nella console di amministrazione Teams e in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea72c-118">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="ea72c-119">È possibile assegnare qualsiasi modalità di TeamsUpgradePolicy, ad eccezione della modalità TeamsOnly, agli utenti ospitati Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="ea72c-119">You can assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="ea72c-120">Al contrario, agli utenti ospitati nel cloud può essere assegnata solo la modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ea72c-120">Conversely, users homed in the cloud can only be assigned TeamsOnly mode.</span></span> <span data-ttu-id="ea72c-121">La modalità **TeamsOnly** può essere assegnata solo a un utente che si trova già nel cloud perché l'interoperabilità e la federazione con gli utenti di Skype for Business e le funzionalità di Microsoft 365 Sistema telefonico sono possibili solo se l'utente si trova in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ea72c-121">**TeamsOnly mode can only be assigned to a user who is already homed in the cloud** because interop and federation with Skype for Business users as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>  <span data-ttu-id="ea72c-122">Inoltre, non è possibile assegnare la modalità TeamsOnly come impostazione predefinita a livello di tenant se si ha una distribuzione **locale di Skype for Business,** rilevata dalla presenza di un record DNS lyncdiscover che punta a una posizione diversa da Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea72c-122">Further, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span> <span data-ttu-id="ea72c-123">Per informazioni dettagliate, [vedere Disabilitare la configurazione ibrida per completare la migrazione a Teams solo](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span><span class="sxs-lookup"><span data-stu-id="ea72c-123">For details, see [Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>

<span data-ttu-id="ea72c-124">Gli utenti Skype for Business account locali devono essere spostati [online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) in modalità solo Teams usando Move-CsUser nel set di strumenti Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="ea72c-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) to Teams Only mode using Move-CsUser in the Skype for Business on-premises toolset.</span></span> 

<span data-ttu-id="ea72c-125">A differenza di altri criteri, non è possibile creare nuove istanze di TeamsUpgradePolicy in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea72c-125">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ea72c-126">Tutte le istanze esistenti sono incorporate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ea72c-126">All the existing instances are built into the service.</span></span>  <span data-ttu-id="ea72c-127">Si noti che la modalità è una proprietà all'interno di TeamsUpgradePolicy, anziché il nome di un'istanza dei criteri. In alcuni casi, ma non in tutti, il nome dell'istanza dei criteri corrisponde alla modalità.</span><span class="sxs-lookup"><span data-stu-id="ea72c-127">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="ea72c-128">In particolare, per assegnare la modalità TeamsOnly a un utente, si concede l'istanza "UpgradeToTeams" di TeamsUpgradePolicy a tale utente.</span><span class="sxs-lookup"><span data-stu-id="ea72c-128">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="ea72c-129">Per visualizzare un elenco di tutte le istanze, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ea72c-129">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="ea72c-130">Per aggiornare un utente online alla modalità TeamsOnly, assegnare l'istanza "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="ea72c-130">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="ea72c-131">Per aggiornare un utente Skype for Business locale alla modalità TeamsOnly, usare Move-CsUser nel set di strumenti locale:</span><span class="sxs-lookup"><span data-stu-id="ea72c-131">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

<span data-ttu-id="ea72c-132">Per cambiare la modalità per tutti gli utenti del tenant, ad eccezione di quelli che hanno una concessione esplicita per utente (che ha la precedenza), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ea72c-132">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="ea72c-133">Se si hanno utenti con Skype for Business account locali, non è possibile assegnare la modalità TeamsOnly a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="ea72c-133">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="ea72c-134">È necessario spostare questi utenti singolarmente in Teams modalità Solo con Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="ea72c-134">You must move these users individually to Teams Only mode using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="ea72c-135">Uso delle notifiche nei Skype for Business client</span><span class="sxs-lookup"><span data-stu-id="ea72c-135">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="ea72c-136">Gli amministratori hanno la possibilità di fornire notifiche agli utenti finali nel client Skype for Business per informare gli utenti che presto verranno aggiornati a Teams, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="ea72c-136">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="ea72c-137">Ad esempio, una settimana prima che l'amministratore pianichi di aggiornare un gruppo di utenti alla modalità TeamsOnly, l'amministratore potrebbe voler attivare queste notifiche per quel gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="ea72c-137">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="ea72c-138">Queste notifiche vengono abilitate usando un'istanza di TeamsUpgradePolicy con NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="ea72c-138">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="ea72c-139">Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, corrispondenti ai due valori di NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="ea72c-139">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="ea72c-140">Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, corrispondenti ai due valori di NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="ea72c-140">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagramma che mostra le notifiche](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="ea72c-142">Se gli utenti sono ospitati in Skype for Business Online, è sufficiente assegnare l'istanza dei criteri che ha la stessa modalità dell'utente, ma con NotifySfbUsers=true.</span><span class="sxs-lookup"><span data-stu-id="ea72c-142">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="ea72c-143">Se gli utenti sono ospitati in Skype for Business Server locale, è necessario usare il set di strumenti locale e sarà necessario Skype for Business Server 2019 o CU8 per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ea72c-143">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="ea72c-144">Per gli utenti ospitati Skype for Business Server locale, viene rispettata la proprietà mode dell'istanza online di TeamsUpgradePolicy, ma non la proprietà NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="ea72c-144">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="ea72c-145">Se si desidera ricevere notifiche, è necessario creare un'istanza locale di TeamsUpgradePolicy per controllare il comportamento del client.</span><span class="sxs-lookup"><span data-stu-id="ea72c-145">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="ea72c-146">Nella finestra di PowerShell locale creare una nuova istanza di TeamsUpgradePolicy con NotifySfbUsers=true:</span><span class="sxs-lookup"><span data-stu-id="ea72c-146">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="ea72c-147">Quindi, usando la stessa finestra di PowerShell locale, assegnare il nuovo criterio agli utenti desiderati:</span><span class="sxs-lookup"><span data-stu-id="ea72c-147">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="ea72c-148">Migrazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="ea72c-148">Meeting migration</span></span>

<span data-ttu-id="ea72c-149">Quando un utente viene migrato in modalità TeamsOnly, per impostazione predefinita le riunioni Skype for Business che hanno organizzato verranno convertite in Teams.</span><span class="sxs-lookup"><span data-stu-id="ea72c-149">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="ea72c-150">Facoltativamente, è possibile disabilitare il comportamento predefinito quando si assegna la modalità TeamsOnly a un utente.</span><span class="sxs-lookup"><span data-stu-id="ea72c-150">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="ea72c-151">Quando si spostano utenti dall'ambiente locale, è necessario eseguire la migrazione delle riunioni nel cloud per funzionare con l'account utente online, ma se non si specifica -MoveToTeams, le riunioni verranno migrate come riunioni Skype for Business anziché convertite in Teams.</span><span class="sxs-lookup"><span data-stu-id="ea72c-151">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="ea72c-152">Quando si assegna la modalità TeamsOnly a livello di tenant, la migrazione delle riunioni non viene attivata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ea72c-152">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="ea72c-153">Se si vuole assegnare la modalità TeamsOnly a livello di tenant ed eseguire la migrazione delle riunioni, è possibile usare PowerShell per ottenere un elenco di utenti nel tenant , ad esempio usando Get-CsOnlineUser con tutti i filtri necessari, e quindi scorrere ognuno di questi utenti per avviare la migrazione delle riunioni con Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="ea72c-153">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="ea72c-154">Per informazioni dettagliate, vedere [Uso del servizio di migrazione delle riunioni (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="ea72c-154">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="ea72c-155">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="ea72c-155">Related links</span></span>

[<span data-ttu-id="ea72c-156">Modalità di coesistenza - Riferimento</span><span class="sxs-lookup"><span data-stu-id="ea72c-156">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="ea72c-157">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="ea72c-157">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="ea72c-158">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="ea72c-158">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="ea72c-159">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ea72c-159">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="ea72c-160">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ea72c-160">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="ea72c-161">Uso del servizio di migrazione delle riunioni (MMS)</span><span class="sxs-lookup"><span data-stu-id="ea72c-161">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
