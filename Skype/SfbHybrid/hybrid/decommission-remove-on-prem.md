---
title: Rimozione delle autorizzazioni Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni per la rimozione delle autorizzazioni Skype for Business Server.
ms.openlocfilehash: e96c4cd37d09fc62fbfbe34a8b8d61c79ea08289
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454339"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="94e73-103">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="94e73-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="94e73-104">In questo articolo viene descritto come rimuovere la distribuzione locale Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="94e73-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="94e73-105">Questo è il passaggio 4 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="94e73-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="94e73-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="94e73-106">Step 1.</span></span> <span data-ttu-id="94e73-107">[Spostare tutti gli utenti necessari da locale a online.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="94e73-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="94e73-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="94e73-108">Step 2.</span></span> <span data-ttu-id="94e73-109">[Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="94e73-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="94e73-110">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="94e73-110">Step 3.</span></span> [<span data-ttu-id="94e73-111">Eseguire la migrazione di endpoint di applicazioni ibride da locale a online</span><span class="sxs-lookup"><span data-stu-id="94e73-111">Migrate hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="94e73-112">**Passaggio 4. Rimuovere la distribuzione locale Skype for Business locale.**</span><span class="sxs-lookup"><span data-stu-id="94e73-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="94e73-113">(Questo articolo)</span><span class="sxs-lookup"><span data-stu-id="94e73-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="94e73-114">La procedura descritta in questo articolo si applica solo se si utilizza il metodo 2 per la gestione degli attributi utente, come descritto [qui.](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="94e73-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="94e73-115">Se si utilizza il metodo 1, non eseguire la procedura descritta in questo articolo per rimuovere i Skype for Business server.</span><span class="sxs-lookup"><span data-stu-id="94e73-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="94e73-116">Al contrario, è possibile ri-immagine dei server.</span><span class="sxs-lookup"><span data-stu-id="94e73-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="94e73-117">Per completare i passaggi descritti in questo articolo, sono necessari privilegi sia per il gruppo Schema Admins che per il Enterprise Admin.</span><span class="sxs-lookup"><span data-stu-id="94e73-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="94e73-118">Questi privilegi sono necessari per annullare le modifiche Skype for Business Server schema e a livello di foresta in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="94e73-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="94e73-119">Sarà inoltre necessario essere membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="94e73-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="94e73-120">Preparare la rimozione della Skype for Business distribuzione</span><span class="sxs-lookup"><span data-stu-id="94e73-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="94e73-121">Dopo aver spostato tutti gli account utente necessari nel cloud, potrebbero essere ancora presenti alcuni oggetti locali rimanenti, ad esempio contatti e applicazioni, che sarà necessario pulire.</span><span class="sxs-lookup"><span data-stu-id="94e73-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="94e73-122">Eseguire la procedura seguente per pulire questi oggetti e assicurarsi di essere membri sia del gruppo Amministratore locale che del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="94e73-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="94e73-123">Si noti che ExUmContacts e PersistantChatEndPoints non sono disponibili Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="94e73-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="94e73-124">Se è stato Skype for Business Server 2019, i cmdlet corrispondenti nei passaggi seguenti devono essere omessi.</span><span class="sxs-lookup"><span data-stu-id="94e73-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="94e73-125">Per verificare se sono presenti contatti o applicazioni associati alla Skype for Business Server locale, eseguire i cmdlet di PowerShell Skype for Business Server seguenti.</span><span class="sxs-lookup"><span data-stu-id="94e73-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="94e73-126">Esaminare gli elenchi di output dei cmdlet nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="94e73-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="94e73-127">Se quindi è possibile rimuovere oggetti, eseguire i cmdlet di PowerShell Skype for Business Server seguenti:</span><span class="sxs-lookup"><span data-stu-id="94e73-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="94e73-128">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="94e73-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="94e73-129">Dopo aver completato tutti i passaggi preliminari, è possibile rimuovere la Skype for Business distribuzione seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="94e73-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="94e73-130">Rimuovere logicamente la Skype for Business Server distribuzione, ad eccezione di un singolo front-end, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="94e73-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   1. <span data-ttu-id="94e73-131">Aggiornare la Skype for Business Server della topologia in modo che abbia un singolo pool front-end:</span><span class="sxs-lookup"><span data-stu-id="94e73-131">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

      1. <span data-ttu-id="94e73-132">In Generatore di topologie scaricare una nuova copia e passare al pool Frontend.</span><span class="sxs-lookup"><span data-stu-id="94e73-132">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
      1. <span data-ttu-id="94e73-133">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="94e73-133">Right-click the pool, and then click **Edit Properties**.</span></span>
      1. <span data-ttu-id="94e73-134">In **Associazioni** deselezionare Associa pool di server perimetrali (per i componenti multimediali) e fare clic su **OK.** </span><span class="sxs-lookup"><span data-stu-id="94e73-134">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
      1. <span data-ttu-id="94e73-135">Se sono presenti più pool front-end, rimuovere associazioni per tutti i pool rimanenti.</span><span class="sxs-lookup"><span data-stu-id="94e73-135">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
      1. <span data-ttu-id="94e73-136">Selezionare **Azione > Rimuovi distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="94e73-136">Select **Action > Remove Deployment**.</span></span>
      1. <span data-ttu-id="94e73-137">Selezionare **Azione > Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="94e73-137">Select **Action > Publish Topology**.</span></span>

    1. <span data-ttu-id="94e73-138">Dopo aver pubblicato la topologia, completare i passaggi aggiuntivi descritti nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="94e73-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="94e73-139">Rimuovere Skype for Business Server directory conferenze eseguendo il cmdlet di PowerShell Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="94e73-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="94e73-140">Completare la disinstallazione della Skype for Business Server di distribuzione eseguendo il cmdlet di PowerShell Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="94e73-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="94e73-141">Se questo passaggio restituisce un errore, aprire un ticket di supporto Microsoft per ottenere assistenza per la rimozione degli oggetti non obsoleti rimanenti.</span><span class="sxs-lookup"><span data-stu-id="94e73-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="94e73-142">Rimuovere il punto di controllo del servizio archivio di gestione centrale eseguendo il cmdlet powershell Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="94e73-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="94e73-143">Annullare Skype for Business Server modifiche a livello di dominio di Active Directory eseguendo il cmdlet Skype for Business Server PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="94e73-143">Undo Skype for Business Server Active Directory domain-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="94e73-144">Annullare Skype for Business Server modifiche a livello di foresta di Active Directory eseguendo il cmdlet Skype for Business Server PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="94e73-144">Undo Skype for Business Server Active Directory forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="94e73-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e73-145">See also</span></span>

- [<span data-ttu-id="94e73-146">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="94e73-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="94e73-147">Spostare tutti gli utenti necessari da locale a online</span><span class="sxs-lookup"><span data-stu-id="94e73-147">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="94e73-148">Disabilitare la configurazione ibrida</span><span class="sxs-lookup"><span data-stu-id="94e73-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="94e73-149">Spostare gli endpoint dell'applicazione ibrida da locale a online</span><span class="sxs-lookup"><span data-stu-id="94e73-149">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

