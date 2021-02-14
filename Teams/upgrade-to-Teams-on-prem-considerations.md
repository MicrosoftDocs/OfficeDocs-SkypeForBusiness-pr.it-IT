---
title: Eseguire l'aggiornamento a Teams da una distribuzione locale di Skype for Business - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533593"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="472ff-103">Considerazioni sull'aggiornamento per le organizzazioni con Skype for Business Server locale &mdash; per amministratori IT</span><span class="sxs-lookup"><span data-stu-id="472ff-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="472ff-104">Questo articolo descrive altre considerazioni da tenere in considerazione per le organizzazioni con Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="472ff-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="472ff-105">Questo articolo è il quarto di diversi articoli che descrivono i concetti e l'implementazione dell'aggiornamento per gli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="472ff-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="472ff-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="472ff-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="472ff-107">Metodi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="472ff-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="472ff-108">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="472ff-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="472ff-109">**Considerazioni aggiuntive per le organizzazioni con Skype for Business locale** (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="472ff-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="472ff-110">Implementazione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="472ff-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="472ff-111">Considerazioni sulla rete PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="472ff-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="472ff-112">Gli articoli seguenti descrivono inoltre concetti importanti sull'aggiornamento e comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="472ff-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="472ff-113">Coesistenza di Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="472ff-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="472ff-114">Modalità di coesistenza - Riferimento</span><span class="sxs-lookup"><span data-stu-id="472ff-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="472ff-115">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="472ff-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="472ff-116">Considerazioni per le organizzazioni con Skype for Business Server locale</span><span class="sxs-lookup"><span data-stu-id="472ff-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="472ff-117">La configurazione ibrida di Skype for Business è un prerequisito per la migrazione alla modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="472ff-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="472ff-118">Anche se è possibile usare Teams in modalità isole senza distribuzione ibrida, la transizione alla modalità TeamsOnly non può essere effettuata finché l'utente non viene spostato da Skype for Business locale a Skype for Business online (con [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="472ff-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="472ff-119">Per altre informazioni, vedere [Configurare la connettività ibrida.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="472ff-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="472ff-120">Se l'organizzazione dispone di Skype for Business Server e la connettività ibrida non è stata configurata, ma si vuole comunque usare Teams per amministrare le funzionalità di Teams, è necessario usare un account amministrativo con un dominio onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="472ff-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="472ff-121">Gli utenti di Teams che dispongono di un account Skype for Business locale (ovvero non sono ancora stati spostati nel cloud con Move-CsUser) non possono interagire con gli utenti di Skype for Business né possono federatire con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="472ff-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="472ff-122">Questa funzionalità è disponibile solo dopo lo spostamento degli utenti nel cloud (in modalità Isole o in modalità TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="472ff-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="472ff-123">Se hai utenti con account Skype for Business in locale, non puoi assegnare la modalità TeamsOnly a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="472ff-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="472ff-124">Devi prima spostare nel cloud tutti gli utenti con account Skype for Business locali e quindi disabilitare la migrazione ibrida per completare `Move-CsUser` [la migrazione al cloud.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="472ff-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="472ff-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` non funzionerà a livello di tenant se è stato rilevato un record DNS lyncdiscover che punta a una posizione diversa da Office 365.</span><span class="sxs-lookup"><span data-stu-id="472ff-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="472ff-126">È necessario assicurarsi che gli utenti siano sincronizzati correttamente in Azure AD con gli attributi corretti di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="472ff-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="472ff-127">Questi attributi sono tutti prefissi con "msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="472ff-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="472ff-128">Se gli utenti non vengono sincronizzati correttamente con Azure AD, gli strumenti di gestione in Teams non saranno in grado di gestire questi utenti.</span><span class="sxs-lookup"><span data-stu-id="472ff-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="472ff-129">Ad esempio, non sarà possibile assegnare criteri di Teams agli utenti locali a meno che questi attributi non vengano sincronizzati correttamente. Per altre informazioni, vedere [Configurare Azure AD Connect per Teams e Skype for Business.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)</span><span class="sxs-lookup"><span data-stu-id="472ff-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="472ff-130">Per creare un nuovo utente TeamsOnly o Skype for Business online in un'organizzazione ibrida, devi prima abilitare l'utente *in Skype for Business Server* locale, quindi spostarlo dalla distribuzione locale al cloud con Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="472ff-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="472ff-131">La creazione dell'utente in locale assicura prima che tutti gli altri utenti skype for Business locali rimanenti saranno instraderanno all'utente appena creato.</span><span class="sxs-lookup"><span data-stu-id="472ff-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="472ff-132">Dopo aver spostato tutti gli utenti online, non è più necessario abilitare prima gli utenti in locale.</span><span class="sxs-lookup"><span data-stu-id="472ff-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="472ff-133">Quando un utente viene spostato dalla distribuzione locale al cloud, le riunioni organizzate da quell'utente vengono migrate a Skype for Business Online o Teams, a seconda che sia o meno specificato il parametro -MoveToTeams.</span><span class="sxs-lookup"><span data-stu-id="472ff-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="472ff-134">Se desideri visualizzare le notifiche nel client Skype for Business per gli utenti locali, devi utilizzare TeamsUpgradePolicy nel set di strumenti locale.</span><span class="sxs-lookup"><span data-stu-id="472ff-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="472ff-135">Solo il parametro NotifySfbUsers è pertinente per gli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="472ff-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="472ff-136">Gli utenti locali ricevono la modalità dalle istanze online di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="472ff-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="472ff-137">Vedere le note in [Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="472ff-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="472ff-138">I nuovi tenant creati dopo il 3 settembre 2019 vengono creati come tenant TeamsOnly, a meno che l'organizzazione non abbia già una distribuzione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="472ff-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="472ff-139">Microsoft usa i record DNS per identificare le organizzazioni Skype for Business Server locali.</span><span class="sxs-lookup"><span data-stu-id="472ff-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="472ff-140">Se l'organizzazione dispone di Skype for Business Server locale senza voci DNS pubbliche, sarà necessario chiamare il supporto Tecnico Microsoft per eseguire il downgrade del nuovo tenant.</span><span class="sxs-lookup"><span data-stu-id="472ff-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="472ff-141">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="472ff-141">Related links</span></span>

[<span data-ttu-id="472ff-142">Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business</span><span class="sxs-lookup"><span data-stu-id="472ff-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="472ff-143">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="472ff-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="472ff-144">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="472ff-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="472ff-145">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="472ff-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="472ff-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="472ff-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="472ff-147">Uso del servizio MMS (Meeting Migration Service)</span><span class="sxs-lookup"><span data-stu-id="472ff-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

