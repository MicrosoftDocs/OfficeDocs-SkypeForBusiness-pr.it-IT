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
ms.openlocfilehash: 3b910a93435cedfc1dcc83c34b766d9121f93eea
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955953"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="0dc35-103">Strumenti per l'aggiornamento ai team &mdash; per gli amministratori IT</span><span class="sxs-lookup"><span data-stu-id="0dc35-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="0dc35-104">In questo articolo vengono illustrati gli strumenti per l'aggiornamento ai team.</span><span class="sxs-lookup"><span data-stu-id="0dc35-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="0dc35-105">Questo articolo è il terzo di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="0dc35-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="0dc35-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0dc35-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="0dc35-107">Metodi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0dc35-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="0dc35-108">**Strumenti per la gestione dell'aggiornamento**   (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="0dc35-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="0dc35-109">Considerazioni aggiuntive per le organizzazioni con Skype for business locale</span><span class="sxs-lookup"><span data-stu-id="0dc35-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="0dc35-110">Implementare l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0dc35-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="0dc35-111">Considerazioni su PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="0dc35-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="0dc35-112">Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="0dc35-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="0dc35-113">Coesistenza di teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="0dc35-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="0dc35-114">Modalità di coesistenza-riferimento</span><span class="sxs-lookup"><span data-stu-id="0dc35-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="0dc35-115">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="0dc35-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="0dc35-116">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0dc35-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="0dc35-117">Qualunque sia il metodo di aggiornamento scelto, è possibile gestire la transizione a TeamsOnly usando [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), che controlla la modalità di coesistenza di un utente.</span><span class="sxs-lookup"><span data-stu-id="0dc35-117">Whichever upgrade method you choose, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="0dc35-118">Per altre informazioni su ognuna delle modalità, vedere [modalità di coesistenza](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="0dc35-118">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="0dc35-119">Sia che si esegua una transizione di selezione delle funzionalità usando le modalità Skype for business o semplicemente l'aggiornamento alla modalità TeamsOnly dalla configurazione predefinita Islands, TeamsUpgradePolicy è lo strumento principale.</span><span class="sxs-lookup"><span data-stu-id="0dc35-119">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.</span></span> <span data-ttu-id="0dc35-120">Come qualsiasi altro criterio in teams, puoi assegnare TeamsUpgradePolicy direttamente a un utente.</span><span class="sxs-lookup"><span data-stu-id="0dc35-120">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="0dc35-121">È anche possibile impostare i criteri come predefiniti a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="0dc35-121">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="0dc35-122">Qualsiasi assegnazione a un utente ha la precedenza sull'impostazione predefinita del tenant.</span><span class="sxs-lookup"><span data-stu-id="0dc35-122">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="0dc35-123">È possibile gestire i criteri nella console di amministrazione di teams e in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0dc35-123">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="0dc35-124">È possibile assegnare qualsiasi modalità di TeamsUpgradePolicy agli utenti se l'utente è ospitato in Skype for business online o in locale, **ad eccezione del fatto che la modalità TeamsOnly può essere assegnata solo a un utente già disponibile in Skype for business online**.</span><span class="sxs-lookup"><span data-stu-id="0dc35-124">You can assign any mode of TeamsUpgradePolicy to users whether the user is homed in Skype for Business Online or on-premises, **except that TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="0dc35-125">Il motivo è che l'interoperabilità con gli utenti di Skype for business e la Federazione, oltre alle funzionalità del sistema telefonico Microsoft 365, è possibile solo se l'utente è ospitato in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="0dc35-125">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>

<span data-ttu-id="0dc35-126">Gli utenti con account Skype for business ospitati in locale [devono essere spostati online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (Skype for business online o Direct to Teams) usando Move-CsUser nel set di strumenti locali di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="0dc35-126">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="0dc35-127">Questi utenti possono essere spostati in TeamsOnly in uno o due passaggi:</span><span class="sxs-lookup"><span data-stu-id="0dc35-127">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="0dc35-128">1 passaggio: specificare l'opzione-MoveToTeams in Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="0dc35-128">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="0dc35-129">In questo articolo è necessario Skype for Business Server 2019 o Skype for Business Server 2015 con CU8 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0dc35-129">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="0dc35-130">2 passaggi: dopo aver eseguito Move-CsUser, concedere la modalità TeamsOnly all'utente usando TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="0dc35-130">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="0dc35-131">A differenza di altri criteri, non è possibile creare nuove istanze di TeamsUpgradePolicy in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="0dc35-131">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0dc35-132">Tutte le istanze esistenti sono compilate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="0dc35-132">All the existing instances are built into the service.</span></span>  <span data-ttu-id="0dc35-133">Tieni presente che la modalità è una proprietà all'interno di TeamsUpgradePolicy, piuttosto che il nome di un'istanza di criteri. In alcuni casi, ma non tutti, il nome dell'istanza di criterio corrisponde alla modalità.</span><span class="sxs-lookup"><span data-stu-id="0dc35-133">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="0dc35-134">In particolare, per assegnare la modalità TeamsOnly a un utente, l'istanza "UpgradeToTeams" di TeamsUpgradePolicy viene assegnata all'utente.</span><span class="sxs-lookup"><span data-stu-id="0dc35-134">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="0dc35-135">Per visualizzare un elenco di tutte le istanze, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0dc35-135">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="0dc35-136">Per aggiornare un utente online alla modalità TeamsOnly, assegna l'istanza "UpgradeToTeams":</span><span class="sxs-lookup"><span data-stu-id="0dc35-136">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="0dc35-137">Per aggiornare un utente locale di Skype for business alla modalità TeamsOnly, USA Move-CsUser nel set di strumenti locale:</span><span class="sxs-lookup"><span data-stu-id="0dc35-137">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="0dc35-138">Per modificare la modalità per tutti gli utenti del tenant, ad eccezione di quelli che hanno una concessione esplicita per utente (che ha la precedenza), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0dc35-138">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="0dc35-139">Se si hanno utenti con account Skype for business in locale, non è necessario assegnare la modalità TeamsOnly a livello di tenant, a meno che non si assegni esplicitamente un'altra modalità a tutti gli utenti con account Skype for business locale.</span><span class="sxs-lookup"><span data-stu-id="0dc35-139">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="0dc35-140">Uso delle notifiche nei client Skype for business</span><span class="sxs-lookup"><span data-stu-id="0dc35-140">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="0dc35-141">Gli amministratori hanno la possibilità di fornire notifiche degli utenti finali nel client Skype for business per informare gli utenti che presto verranno aggiornati ai team, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="0dc35-141">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="0dc35-142">Ad esempio, una settimana prima che l'amministratore abbia intenzione di aggiornare un gruppo di utenti alla modalità TeamsOnly, l'amministratore potrebbe voler attivare queste notifiche per il gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="0dc35-142">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="0dc35-143">Queste notifiche sono abilitate usando un'istanza di TeamsUpgradePolicy con NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="0dc35-143">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="0dc35-144">Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, che corrispondono ai due valori di NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="0dc35-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="0dc35-145">Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, che corrispondono ai due valori di NotifySfbUsers.</span><span class="sxs-lookup"><span data-stu-id="0dc35-145">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![Diagramma che mostra le notifiche](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="0dc35-147">Se gli utenti sono ospitati in Skype for business online, è sufficiente assegnare l'istanza di criteri con la stessa modalità dell'utente, ma con NotifySfbUsers = true.</span><span class="sxs-lookup"><span data-stu-id="0dc35-147">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="0dc35-148">Se gli utenti sono ospitati in Skype for Business Server locale, sarà necessario usare il set di strumenti locale e sarà necessario Skype for Business Server 2019 o CU8 per Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0dc35-148">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="0dc35-149">Per gli utenti ospitati in Skype for Business Server locale, la proprietà Mode dell'istanza online di TeamsUpgradePolicy è onorata, ma la proprietà NotifySfbUsers non è.</span><span class="sxs-lookup"><span data-stu-id="0dc35-149">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="0dc35-150">Se si desidera ricevere le notifiche, è necessario creare un'istanza locale di TeamsUpgradePolicy per controllare il comportamento del client.</span><span class="sxs-lookup"><span data-stu-id="0dc35-150">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="0dc35-151">Nella finestra di PowerShell locale creare una nuova istanza di TeamsUpgradePolicy con NotifySfbUsers = true:</span><span class="sxs-lookup"><span data-stu-id="0dc35-151">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="0dc35-152">Quindi, usando la stessa finestra di PowerShell locale, assegna il nuovo criterio agli utenti desiderati:</span><span class="sxs-lookup"><span data-stu-id="0dc35-152">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="0dc35-153">Migrazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="0dc35-153">Meeting migration</span></span>

<span data-ttu-id="0dc35-154">Quando un utente viene migrato in modalità TeamsOnly, per impostazione predefinita le riunioni Skype for business esistenti che hanno organizzato verranno convertite in teams.</span><span class="sxs-lookup"><span data-stu-id="0dc35-154">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="0dc35-155">Puoi facoltativamente disabilitare il comportamento predefinito quando assegni la modalità TeamsOnly a un utente.</span><span class="sxs-lookup"><span data-stu-id="0dc35-155">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="0dc35-156">Quando si spostano utenti da locale, le riunioni devono essere migrate nel cloud per funzionare con l'account utente online, ma se non si specifica-MoveToTeams, le riunioni verranno migrate come riunioni Skype for business, anziché convertite in teams.</span><span class="sxs-lookup"><span data-stu-id="0dc35-156">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="0dc35-157">Quando si assegna la modalità TeamsOnly a livello di tenant, la migrazione delle riunioni non viene attivata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0dc35-157">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="0dc35-158">Se si vuole assegnare la modalità TeamsOnly a livello di tenant e eseguire la migrazione delle riunioni, è possibile usare PowerShell per ottenere un elenco di utenti nel tenant (ad esempio, usando Get-CsOnlineUser con tutti i filtri necessari) e quindi scorrere ogni utente per attivare la migrazione delle riunioni usando Start-CsExMeetingMigration.</span><span class="sxs-lookup"><span data-stu-id="0dc35-158">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="0dc35-159">Per informazioni dettagliate, vedere [uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span><span class="sxs-lookup"><span data-stu-id="0dc35-159">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="0dc35-160">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="0dc35-160">Related links</span></span>

[<span data-ttu-id="0dc35-161">Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business</span><span class="sxs-lookup"><span data-stu-id="0dc35-161">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="0dc35-162">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="0dc35-162">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="0dc35-163">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="0dc35-163">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="0dc35-164">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="0dc35-164">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="0dc35-165">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0dc35-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="0dc35-166">Uso del servizio di migrazione delle riunioni (MMS)</span><span class="sxs-lookup"><span data-stu-id="0dc35-166">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

