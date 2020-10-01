---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Eseguire l'aggiornamento da Skype for business a teams-strumenti per l'aggiornamento
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 076e96ac8cf44e05e2852ca5bdf33b42e14eb731
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328195"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="e7914-103">Strumenti per l'aggiornamento ai team &mdash; per gli amministratori IT</span><span class="sxs-lookup"><span data-stu-id="e7914-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="e7914-104">In questo articolo vengono illustrati gli strumenti per l'aggiornamento ai team.</span><span class="sxs-lookup"><span data-stu-id="e7914-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="e7914-105">Questo articolo è il terzo di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="e7914-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="e7914-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e7914-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="e7914-107">Metodi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e7914-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="e7914-108">**Strumenti per la gestione dell'aggiornamento**   (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="e7914-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="e7914-109">Considerazioni aggiuntive per le organizzazioni con Skype for business locale</span><span class="sxs-lookup"><span data-stu-id="e7914-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="e7914-110">Implementare l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e7914-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="e7914-111">Considerazioni su PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="e7914-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="e7914-112">Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="e7914-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="e7914-113">Coesistenza di teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="e7914-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="e7914-114">Modalità di coesistenza-riferimento</span><span class="sxs-lookup"><span data-stu-id="e7914-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="e7914-115">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="e7914-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="e7914-116">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e7914-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="e7914-117">Qualunque sia il metodo di aggiornamento scelto, per gli utenti che hanno già Skype for business online, è possibile gestire la transizione a TeamsOnly usando [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), che controlla la modalità di coesistenza di un utente.</span><span class="sxs-lookup"><span data-stu-id="e7914-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="e7914-118">Per gli utenti con un account locale in Skype for Business Server, puoi anche `Move-CsUser` [spostarli nel cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span><span class="sxs-lookup"><span data-stu-id="e7914-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="e7914-119">Per altre informazioni su ognuna delle modalità, vedere [modalità di coesistenza](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="e7914-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>  

<span data-ttu-id="e7914-120">Sia che si esegua una transizione Seleziona funzionalità usando le modalità Skype for business o semplicemente l'aggiornamento alla modalità TeamsOnly dalla configurazione di default Islands, TeamsUpgradePolicy è lo strumento principale per gli utenti che hanno già Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="e7914-120">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="e7914-121">Come qualsiasi altro criterio in teams, puoi assegnare TeamsUpgradePolicy direttamente a un utente.</span><span class="sxs-lookup"><span data-stu-id="e7914-121">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="e7914-122">È anche possibile impostare i criteri come predefiniti a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="e7914-122">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="e7914-123">Qualsiasi assegnazione a un utente ha la precedenza sull'impostazione predefinita del tenant.</span><span class="sxs-lookup"><span data-stu-id="e7914-123">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="e7914-124">È possibile gestire i criteri nella console di amministrazione di teams e in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7914-124">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="e7914-125">È anche possibile assegnare qualsiasi modalità di TeamsUpgradePolicy, ad eccezione della modalità TeamsOnly, agli utenti ospitati in Skype for business locale.</span><span class="sxs-lookup"><span data-stu-id="e7914-125">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="e7914-126">**La modalità TeamsOnly può essere assegnata solo a un utente già ospitato in Skype for business online**.</span><span class="sxs-lookup"><span data-stu-id="e7914-126">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="e7914-127">Il motivo è che l'interoperabilità con gli utenti di Skype for business e la Federazione, oltre alle funzionalità del sistema telefonico Microsoft 365, è possibile solo se l'utente è ospitato in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="e7914-127">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="e7914-128">Inoltre, **non è possibile assegnare la modalità TeamsOnly come predefinita a livello di tenant se si ha una distribuzione locale di Skype for business** (che viene rilevata dalla presenza di un record DNS di Lyncdiscover che punta alla posizione diversa da Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7914-128">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="e7914-129">Gli utenti con account Skype for business ospitati in locale [devono essere spostati online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (Skype for business online o Direct to Teams) usando Move-CsUser nel set di strumenti locali di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="e7914-129">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="e7914-130">Questi utenti possono essere spostati in TeamsOnly in uno o due passaggi:</span><span class="sxs-lookup"><span data-stu-id="e7914-130">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="e7914-131">1 passaggio: specificare l'opzione-MoveToTeams in Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e7914-131">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="e7914-132">In questo articolo è necessario Skype for Business Server 2019 o Skype for Business Server 2015 con CU8 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e7914-132">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="e7914-133">2 passaggi: dopo aver eseguito Move-CsUser, concedere la modalità TeamsOnly all'utente usando TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="e7914-133">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="e7914-134">A differenza di altri criteri, non è possibile creare nuove istanze di TeamsUpgradePolicy in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7914-134">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e7914-135">Tutte le istanze esistenti sono compilate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e7914-135">All the existing instances are built into the service.</span></span>  <span data-ttu-id="e7914-136">Tieni presente che la modalità è una proprietà all'interno di TeamsUpgradePolicy, piuttosto che il nome di un'istanza di criteri. In alcuni casi, ma non tutti, il nome dell'istanza di criterio corrisponde alla modalità.</span><span class="sxs-lookup"><span data-stu-id="e7914-136">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="e7914-137">In particolare, per assegnare la modalità TeamsOnly a un utente, l'istanza "UpgradeToTeams" di TeamsUpgradePolicy viene assegnata all'utente.</span><span class="sxs-lookup"><span data-stu-id="e7914-137">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="e7914-138">Per visualizzare un elenco di tutte le istanze, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7914-138">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="e7914-139">Per aggiornare un utente online alla modalità TeamsOnly, assegna l'istanza "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="e7914-139">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="e7914-140">Per aggiornare un utente locale di Skype for business alla modalità TeamsOnly, USA Move-CsUser nel set di strumenti locale:</span><span class="sxs-lookup"><span data-stu-id="e7914-140">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="e7914-141">Per modificare la modalità per tutti gli utenti del tenant, ad eccezione di quelli che hanno una concessione esplicita per utente (che ha la precedenza), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e7914-141">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="e7914-142">Se si hanno utenti con account Skype for business in locale, non è possibile assegnare la modalità TeamsOnly a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="e7914-142">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="e7914-143">È necessario trasferire questi utenti singolarmente nel cloud usando Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e7914-143">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="e7914-144">Uso delle notifiche nei client Skype for business</span><span class="sxs-lookup"><span data-stu-id="e7914-144">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="e7914-145">Gli amministratori hanno la possibilità di fornire notifiche degli utenti finali nel client Skype for business per informare gli utenti che presto verranno aggiornati ai team, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="e7914-145">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="e7914-146">Ad esempio, una settimana prima che l'amministratore abbia intenzione di aggiornare un gruppo di utenti alla modalità TeamsOnly, l'amministratore potrebbe voler attivare queste notifiche per il gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="e7914-146">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="e7914-147">Queste notifiche sono abilitate usando un'istanza di TeamsUpgradePolicy con NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="e7914-147">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="e7914-148">Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, che corrispondono ai due valori di NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="e7914-148">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="e7914-149">Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, che corrispondono ai due valori di NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="e7914-149">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagramma che mostra le notifiche](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="e7914-151">Se gli utenti sono ospitati in Skype for business online, è sufficiente assegnare l'istanza di criteri con la stessa modalità dell'utente, ma con NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="e7914-151">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="e7914-152">Se gli utenti sono ospitati in Skype for Business Server locale, sarà necessario usare il set di strumenti locale e sarà necessario Skype for Business Server 2019 o CU8 per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e7914-152">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="e7914-153">Per gli utenti ospitati in Skype for Business Server locale, la proprietà Mode dell'istanza online di TeamsUpgradePolicy è onorata, ma la proprietà NotifySfbUsers non è.</span><span class="sxs-lookup"><span data-stu-id="e7914-153">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="e7914-154">Se si desidera ricevere le notifiche, è necessario creare un'istanza locale di TeamsUpgradePolicy per controllare il comportamento del client.</span><span class="sxs-lookup"><span data-stu-id="e7914-154">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="e7914-155">Nella finestra di PowerShell locale creare una nuova istanza di TeamsUpgradePolicy con NotifySfbUsers = true:</span><span class="sxs-lookup"><span data-stu-id="e7914-155">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="e7914-156">Quindi, usando la stessa finestra di PowerShell locale, assegna il nuovo criterio agli utenti desiderati:</span><span class="sxs-lookup"><span data-stu-id="e7914-156">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="e7914-157">Migrazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="e7914-157">Meeting migration</span></span>

<span data-ttu-id="e7914-158">Quando un utente viene migrato in modalità TeamsOnly, per impostazione predefinita le riunioni Skype for business esistenti che hanno organizzato verranno convertite in teams.</span><span class="sxs-lookup"><span data-stu-id="e7914-158">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="e7914-159">Puoi facoltativamente disabilitare il comportamento predefinito quando assegni la modalità TeamsOnly a un utente.</span><span class="sxs-lookup"><span data-stu-id="e7914-159">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="e7914-160">Quando si spostano utenti da locale, le riunioni devono essere migrate nel cloud per funzionare con l'account utente online, ma se non si specifica-MoveToTeams, le riunioni verranno migrate come riunioni Skype for business, anziché convertite in teams.</span><span class="sxs-lookup"><span data-stu-id="e7914-160">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="e7914-161">Quando si assegna la modalità TeamsOnly a livello di tenant, la migrazione delle riunioni non viene attivata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e7914-161">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="e7914-162">Se si vuole assegnare la modalità TeamsOnly a livello di tenant e eseguire la migrazione delle riunioni, è possibile usare PowerShell per ottenere un elenco di utenti nel tenant (ad esempio, usando Get-CsOnlineUser con tutti i filtri necessari) e quindi scorrere ogni utente per attivare la migrazione delle riunioni usando Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="e7914-162">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="e7914-163">Per informazioni dettagliate, vedere [uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="e7914-163">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="e7914-164">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="e7914-164">Related links</span></span>

[<span data-ttu-id="e7914-165">Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business</span><span class="sxs-lookup"><span data-stu-id="e7914-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="e7914-166">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="e7914-166">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="e7914-167">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="e7914-167">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="e7914-168">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e7914-168">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="e7914-169">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e7914-169">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="e7914-170">Uso del servizio di migrazione delle riunioni (MMS)</span><span class="sxs-lookup"><span data-stu-id="e7914-170">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

