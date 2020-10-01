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
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c359b39707b57a653f35e75497672d306209ccd
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328215"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="718da-103">Considerazioni sull'aggiornamento per le organizzazioni con Skype for Business Server locale &mdash; per gli amministratori IT</span><span class="sxs-lookup"><span data-stu-id="718da-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="718da-104">In questo articolo vengono illustrate altre considerazioni per le organizzazioni con Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="718da-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="718da-105">Questo articolo è il quarto di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="718da-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="718da-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="718da-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="718da-107">Metodi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="718da-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="718da-108">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="718da-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="718da-109">**Considerazioni aggiuntive per le organizzazioni con Skype for business locale** (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="718da-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="718da-110">Implementazione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="718da-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="718da-111">Considerazioni su PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="718da-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="718da-112">Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="718da-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="718da-113">Coesistenza di teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="718da-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="718da-114">Modalità di coesistenza-riferimento</span><span class="sxs-lookup"><span data-stu-id="718da-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="718da-115">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="718da-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="718da-116">Considerazioni per le organizzazioni con Skype for Business Server locale</span><span class="sxs-lookup"><span data-stu-id="718da-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="718da-117">La configurazione di Skype for business Hybrid è un prerequisito per la migrazione alla modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="718da-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="718da-118">Anche se è possibile usare le squadre in modalità isole senza ibrida, la transizione alla modalità TeamsOnly non può essere eseguita finché l'utente non viene spostato da Skype for business locale a Skype for business online (usando [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span><span class="sxs-lookup"><span data-stu-id="718da-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="718da-119">Per altre informazioni, vedere [configurare la connettività ibrida](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="718da-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="718da-120">Se l'organizzazione ha Skype for Business Server e non è stata configurata la connettività ibrida, ma si vuole comunque usare teams, per amministrare la funzionalità teams, è necessario usare un account di amministrazione che disponga di un dominio con estensione onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="718da-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="718da-121">Gli utenti di team che hanno un account Skype for business locale (ovvero non sono ancora stati spostati nel cloud usando Move-CsUser) non possono interagire con gli utenti di Skype for business, né possono essere federati con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="718da-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="718da-122">Questa funzionalità è disponibile solo quando gli utenti vengono spostati nel cloud (in modalità isole o come utenti di TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="718da-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="718da-123">Se si hanno utenti con account Skype for business in locale, non è possibile assegnare la modalità TeamsOnly a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="718da-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="718da-124">Devi prima di tutto trasferire tutti gli utenti con gli account Skype for business locali nel cloud usando `Move-CsUser` e quindi [disabilitare Hybrid per completare la migrazione al cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span><span class="sxs-lookup"><span data-stu-id="718da-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="718da-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` non funziona a livello di tenant se viene rilevato un record DNS di Lyncdiscover che punta a una posizione diversa da Office 365.</span><span class="sxs-lookup"><span data-stu-id="718da-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="718da-126">Devi assicurarti che gli utenti siano sincronizzati correttamente in Azure AD con gli attributi Skype for business corretti.</span><span class="sxs-lookup"><span data-stu-id="718da-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="718da-127">Questi attributi sono tutti prefissi con "msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="718da-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="718da-128">Se gli utenti non vengono sincronizzati correttamente con Azure AD, gli strumenti di gestione in teams non saranno in grado di gestire questi utenti.</span><span class="sxs-lookup"><span data-stu-id="718da-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="718da-129">Ad esempio, non sarà possibile assegnare criteri di teams agli utenti locali, a meno che non si stiano sincronizzando correttamente questi attributi. Per altre informazioni, vedere [configurare Azure ad Connect per Teams e Skype for business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="718da-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="718da-130">Per creare un nuovo utente di TeamsOnly o Skype for business online in un'organizzazione ibrida, *è prima di tutto necessario abilitare l'utente in Skype for Business Server locale*e quindi trasferire l'utente dal locale al cloud usando Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="718da-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="718da-131">La creazione dell'utente in locale garantisce innanzitutto che tutti gli altri utenti di Skype for business rimanenti saranno in grado di instradare l'utente appena creato.</span><span class="sxs-lookup"><span data-stu-id="718da-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="718da-132">Una volta che tutti gli utenti sono stati spostati online, non è più necessario abilitare prima gli utenti in locale.</span><span class="sxs-lookup"><span data-stu-id="718da-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="718da-133">Quando un utente viene spostato dal locale al cloud, le riunioni organizzate dall'utente vengono migrate in Skype for business online o in teams, a seconda che venga specificato o meno l'opzione-MoveToTeams.</span><span class="sxs-lookup"><span data-stu-id="718da-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="718da-134">Se si vogliono visualizzare le notifiche nel client Skype for business per gli utenti locali, è necessario usare TeamsUpgradePolicy nel set di strumenti locale.</span><span class="sxs-lookup"><span data-stu-id="718da-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="718da-135">Solo il parametro NotifySfbUsers è pertinente per gli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="718da-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="718da-136">Gli utenti locali ricevono la modalità dalle istanze online di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="718da-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="718da-137">Vedere le note in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="718da-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="718da-138">Qualsiasi nuovo tenant creato dopo il 3 settembre 2019 viene creato come tenant di TeamsOnly, a meno che l'organizzazione non abbia già una distribuzione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="718da-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="718da-139">Microsoft usa i record DNS per identificare le organizzazioni di Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="718da-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="718da-140">Se l'organizzazione ha un server Skype for business locale senza voci DNS pubbliche, è necessario chiamare il supporto Microsoft per declassare il nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="718da-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="718da-141">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="718da-141">Related links</span></span>

[<span data-ttu-id="718da-142">Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business</span><span class="sxs-lookup"><span data-stu-id="718da-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="718da-143">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="718da-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="718da-144">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="718da-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="718da-145">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="718da-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="718da-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="718da-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="718da-147">Uso del servizio di migrazione delle riunioni (MMS)</span><span class="sxs-lookup"><span data-stu-id="718da-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

