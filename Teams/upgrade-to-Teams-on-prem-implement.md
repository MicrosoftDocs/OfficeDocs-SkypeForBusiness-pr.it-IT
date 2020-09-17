---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 887ab004ae913ee2171f1894bd5fc4a44845881f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940726"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="c6121-103">Implementare l'aggiornamento da Skype for business a teams &mdash; per gli amministratori IT</span><span class="sxs-lookup"><span data-stu-id="c6121-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="c6121-104">Questo articolo descrive come implementare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c6121-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="c6121-105">Questo articolo è il quinto di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="c6121-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="c6121-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c6121-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="c6121-107">Metodi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c6121-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="c6121-108">Strumenti per la gestione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c6121-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="c6121-109">Considerazioni aggiuntive per le organizzazioni con Skype for business locale</span><span class="sxs-lookup"><span data-stu-id="c6121-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="c6121-110">**Implementare l'aggiornamento** (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="c6121-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="c6121-111">Considerazioni su PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="c6121-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="c6121-112">Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:</span><span class="sxs-lookup"><span data-stu-id="c6121-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="c6121-113">Coesistenza di teams e Skype for business</span><span class="sxs-lookup"><span data-stu-id="c6121-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="c6121-114">Modalità di coesistenza-riferimento</span><span class="sxs-lookup"><span data-stu-id="c6121-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="c6121-115">Esperienza del client di Teams e conformità alle modalità di coesistenza</span><span class="sxs-lookup"><span data-stu-id="c6121-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="c6121-116">Opzioni di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c6121-116">Upgrade options</span></span>

<span data-ttu-id="c6121-117">Questa sezione descrive come implementare l'aggiornamento usando una delle opzioni di aggiornamento seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6121-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="c6121-118">Aggiornamento delle funzionalità sovrapposte (utilizzo della modalità isole)</span><span class="sxs-lookup"><span data-stu-id="c6121-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="c6121-119">Aggiornamento delle funzionalità di selezione per un'organizzazione che non ha ancora iniziato a usare Teams</span><span class="sxs-lookup"><span data-stu-id="c6121-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="c6121-120">Aggiornamento delle funzionalità di selezione per un'organizzazione che usa già teams in modalità Islands</span><span class="sxs-lookup"><span data-stu-id="c6121-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="c6121-121">Per altre informazioni sulle opzioni, verificare di avere già letto i [metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="c6121-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="c6121-122">Aggiornamento delle funzionalità sovrapposte (utilizzo della modalità isole)</span><span class="sxs-lookup"><span data-stu-id="c6121-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="c6121-123">Per l'opzione di aggiornamento delle funzionalità sovrapposte:</span><span class="sxs-lookup"><span data-stu-id="c6121-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="c6121-124">Considerare questa opzione se è possibile eseguire un aggiornamento rapido per l'organizzazione complessiva.</span><span class="sxs-lookup"><span data-stu-id="c6121-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="c6121-125">Poiché esiste un potenziale rischio di confusione per gli utenti finali che eseguono entrambi i client, è preferibile ridurre al minimo il periodo di tempo durante il quale gli utenti devono eseguire entrambi i client.</span><span class="sxs-lookup"><span data-stu-id="c6121-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="c6121-126">Dovresti assicurarti che gli utenti sappiano di eseguire entrambi i client.</span><span class="sxs-lookup"><span data-stu-id="c6121-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="c6121-127">Questa opzione è il modello box fuori sede e non richiede l'intervento dell'amministratore per iniziare a usare teams tranne che per assegnare la licenza Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6121-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="c6121-128">Se gli utenti hanno già Skype for business online, è possibile che si trovi già in questo modello.</span><span class="sxs-lookup"><span data-stu-id="c6121-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="c6121-129">Può essere difficile uscire dalla modalità di sovrapposizione delle funzionalità e passare a TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="c6121-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="c6121-130">Poiché gli utenti aggiornati comunicano solo tramite Team, qualsiasi altro utente dell'organizzazione che comunica con l'utente deve usare teams.</span><span class="sxs-lookup"><span data-stu-id="c6121-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="c6121-131">Se si hanno utenti che non hanno iniziato a usare teams, verranno esposti a messaggi mancanti.</span><span class="sxs-lookup"><span data-stu-id="c6121-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="c6121-132">Inoltre, non vedranno gli utenti di TeamsOnly online in Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c6121-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="c6121-133">Alcune organizzazioni scelgono di eseguire un aggiornamento a livello di tenant usando i criteri globali del tenant per evitare questo problema, ma richiede la pianificazione anticipata e l'attesa finché tutti gli utenti non saranno pronti per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c6121-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="c6121-134">Aggiornamento delle funzionalità di selezione per un'organizzazione che non ha ancora iniziato a usare Teams</span><span class="sxs-lookup"><span data-stu-id="c6121-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="c6121-135">Se l'organizzazione non ha ancora utenti attivi in teams, il primo passaggio consiste nell'impostare i criteri a livello di tenant predefiniti per TeamsUpgradePolicy in una delle modalità Skype for business, ad esempio SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="c6121-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="c6121-136">Gli utenti che non hanno ancora iniziato a usare teams non notano alcuna differenza di comportamento.</span><span class="sxs-lookup"><span data-stu-id="c6121-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="c6121-137">Tuttavia, impostando questo criterio a livello di tenant, è possibile avviare l'aggiornamento degli utenti alla modalità TeamsOnly e assicurarsi che gli utenti aggiornati possano ancora comunicare con utenti non aggiornati.</span><span class="sxs-lookup"><span data-stu-id="c6121-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="c6121-138">Dopo aver identificato gli utenti pilota, è possibile aggiornarli in TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="c6121-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="c6121-139">In caso di locale, usare Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="c6121-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="c6121-140">Se sono online, assegna semplicemente la modalità TeamsOnly usando Grant-CsTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="c6121-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="c6121-141">Per impostazione predefinita, tutte le riunioni Skype for business programmate da questi utenti verranno migrate in teams.</span><span class="sxs-lookup"><span data-stu-id="c6121-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="c6121-142">Di seguito sono riportati i comandi principali:</span><span class="sxs-lookup"><span data-stu-id="c6121-142">Following are the key commands:</span></span>

1. <span data-ttu-id="c6121-143">Impostare l'impostazione predefinita a livello di tenant su modalità SfbWithTeamsCollab come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c6121-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="c6121-144">Aggiornare gli utenti pilota in TeamsOnly come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c6121-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="c6121-145">Per un utente online:</span><span class="sxs-lookup"><span data-stu-id="c6121-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="c6121-146">Per un utente locale:</span><span class="sxs-lookup"><span data-stu-id="c6121-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="c6121-147">Note</span><span class="sxs-lookup"><span data-stu-id="c6121-147">Notes</span></span>
 
- <span data-ttu-id="c6121-148">Invece di impostare il criterio a livello di tenant su SfbWithTeamsCollab, è possibile impostarlo su SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="c6121-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="c6121-149">In questo modo tutti gli utenti possono pianificare tutte le nuove riunioni in teams.</span><span class="sxs-lookup"><span data-stu-id="c6121-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="c6121-150">`Move-CsUser` è un cmdlet negli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="c6121-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="c6121-151">Lo `MoveToTeams` Switch richiede Skype for Business server 2019 o Skype for Business server 2015 con CU8 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c6121-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="c6121-152">Se si usa una versione precedente, è possibile prima di tutto trasferire l'utente in Skype for business online e quindi concedere la modalità TeamsOnly a tale utente.</span><span class="sxs-lookup"><span data-stu-id="c6121-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="c6121-153">Per impostazione predefinita, le riunioni di Skype for business vengono migrate in teams quando si esegue l'aggiornamento alla modalità TeamsOnly o quando si assegna la modalità SfbWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="c6121-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="c6121-154">Il diagramma seguente mostra le fasi concettuali dell'aggiornamento delle funzionalità di selezione per un'organizzazione senza l'utilizzo preventivo di teams.</span><span class="sxs-lookup"><span data-stu-id="c6121-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="c6121-155">L'altezza delle barre rappresenta il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="c6121-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="c6121-156">Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.</span><span class="sxs-lookup"><span data-stu-id="c6121-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="c6121-157">Gli utenti di Skype for business comunicano con gli utenti di TeamsOnly con l'interoperabilità e viceversa.</span><span class="sxs-lookup"><span data-stu-id="c6121-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="c6121-158">Gli utenti in modalità isole devono assicurarsi di eseguire entrambi i client.</span><span class="sxs-lookup"><span data-stu-id="c6121-158">Users in Islands mode must be sure to run both clients.</span></span>

![Diagramma che mostra l'aggiornamento delle funzionalità di selezione senza un uso preventivo dei team](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="c6121-160">Aggiornamento delle funzionalità di selezione per un'organizzazione che usa già teams in modalità Islands</span><span class="sxs-lookup"><span data-stu-id="c6121-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="c6121-161">Se alcuni utenti dell'organizzazione usano attivamente team in modalità isole, probabilmente non si vuole rimuovere la funzionalità dagli utenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="c6121-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="c6121-162">È pertanto necessario un passaggio aggiuntivo prima di modificare il criterio a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="c6121-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="c6121-163">La soluzione consiste nel "nonno" di questi utenti di team attivi esistenti in modalità isole, prima di impostare i criteri a livello di tenant su SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="c6121-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="c6121-164">Dopo aver eseguito questa operazione, è possibile procedere con la distribuzione come sopra, ma si avranno due gruppi di utenti che si spostano in TeamsOnly: gli utenti che erano attivi in teams saranno in modalità Islands e gli utenti rimanenti saranno in modalità SfbWithTeamsCollab.</span><span class="sxs-lookup"><span data-stu-id="c6121-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="c6121-165">Puoi trasferire progressivamente questi utenti in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="c6121-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="c6121-166">Trovare gli utenti attivi in teams come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c6121-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="c6121-167">Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento sinistra, vai a report e quindi utilizzo.</span><span class="sxs-lookup"><span data-stu-id="c6121-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="c6121-168">Nell'elenco a discesa "Seleziona un report" scegliere Microsoft teams e quindi attività utente.</span><span class="sxs-lookup"><span data-stu-id="c6121-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="c6121-169">Verrà fornito un tavolo esportabile di utenti attivi in teams.</span><span class="sxs-lookup"><span data-stu-id="c6121-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="c6121-170">Fare clic su Esporta, Apri Excel e filtra per visualizzare solo gli utenti attivi in teams.</span><span class="sxs-lookup"><span data-stu-id="c6121-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="c6121-171">Per ogni utente di team attivi che si trova nel passaggio 1, assegnare la modalità isole in PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="c6121-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="c6121-172">In questo modo è possibile passare al passaggio successivo e verificare che l'esperienza utente non venga modificata.</span><span class="sxs-lookup"><span data-stu-id="c6121-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="c6121-173">Impostare i criteri a livello di tenant su SfbWithTeamsCollab:</span><span class="sxs-lookup"><span data-stu-id="c6121-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="c6121-174">Aggiornare gli utenti selezionati alla modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="c6121-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="c6121-175">È possibile scegliere di aggiornare gli utenti in modalità isole o in modalità SfbWithTeamsCollab, anche se è consigliabile assegnare priorità all'aggiornamento degli utenti in modalità isole per ridurre al minimo le potenzialità di confusione che possono verificarsi quando gli utenti si trovano in modalità isole.</span><span class="sxs-lookup"><span data-stu-id="c6121-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="c6121-176">Per gli utenti residenti in Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="c6121-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="c6121-177">Per gli utenti residenti in Skype for Business Server locale:</span><span class="sxs-lookup"><span data-stu-id="c6121-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="c6121-178">Il diagramma seguente mostra le fasi concettuali di una transizione di funzionalità di selezione in cui ci sono utenti di isole attive all'inizio.</span><span class="sxs-lookup"><span data-stu-id="c6121-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="c6121-179">L'altezza delle barre rappresenta il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="c6121-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="c6121-180">Durante qualsiasi fase dell'aggiornamento, tutti gli utenti possono comunicare tra loro.</span><span class="sxs-lookup"><span data-stu-id="c6121-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="c6121-181">Gli utenti di Skype for business comunicano con gli utenti di TeamsOnly con l'interoperabilità e viceversa.</span><span class="sxs-lookup"><span data-stu-id="c6121-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![Diagramma che mostra l'aggiornamento delle funzionalità di selezione con gli utenti attivi in modalità Isole](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="c6121-183">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="c6121-183">Related links</span></span>

[<span data-ttu-id="c6121-184">Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business</span><span class="sxs-lookup"><span data-stu-id="c6121-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="c6121-185">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="c6121-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="c6121-186">Spostare utenti tra locale e cloud</span><span class="sxs-lookup"><span data-stu-id="c6121-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="c6121-187">Impostazione delle impostazioni di coesistenza e aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c6121-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="c6121-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="c6121-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="c6121-189">Uso del servizio di migrazione delle riunioni (MMS)</span><span class="sxs-lookup"><span data-stu-id="c6121-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

