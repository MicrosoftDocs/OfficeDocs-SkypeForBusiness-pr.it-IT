---
title: Rimuovere le autorizzazioni di Skype for Business Server
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
description: Istruzioni per la rimozione di Skype for Business Server.
ms.openlocfilehash: 9c6051a07fc05297985b3692351c36791d8842bb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656692"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="bf9d8-103">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bf9d8-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="bf9d8-104">Questo articolo descrive come rimuovere la distribuzione locale di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="bf9d8-105">Questo è il passaggio 4 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="bf9d8-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-106">Step 1.</span></span> <span data-ttu-id="bf9d8-107">[Spostare tutti gli utenti necessari da locale a online.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="bf9d8-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="bf9d8-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-108">Step 2.</span></span> <span data-ttu-id="bf9d8-109">[Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="bf9d8-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="bf9d8-110">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-110">Step 3.</span></span> [<span data-ttu-id="bf9d8-111">Spostare gli endpoint dell'applicazione ibrida da locale a online</span><span class="sxs-lookup"><span data-stu-id="bf9d8-111">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="bf9d8-112">**Passaggio 4. Rimuovere la distribuzione locale di Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="bf9d8-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="bf9d8-113">(Questo articolo)</span><span class="sxs-lookup"><span data-stu-id="bf9d8-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="bf9d8-114">La procedura descritta in questo articolo si applica solo se si utilizza il metodo 2 per la gestione degli attributi utente, come descritto [qui.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="bf9d8-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="bf9d8-115">Se si utilizza il metodo 1, non eseguire la procedura descritta in questo articolo per rimuovere i server Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="bf9d8-116">Al contrario, è possibile ri-immagine dei server.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="bf9d8-117">Per completare i passaggi descritti in questo articolo, sono necessari privilegi sia per il gruppo Schema Admins che per il gruppo Enterprise Admin.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="bf9d8-118">Questi privilegi sono necessari per annullare lo schema di Skype for Business Server e le modifiche a livello di foresta in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="bf9d8-119">Sarà inoltre necessario essere membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="bf9d8-120">Preparare la rimozione della distribuzione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bf9d8-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="bf9d8-121">Dopo aver spostato tutti gli account utente necessari nel cloud, potrebbero essere ancora presenti alcuni oggetti locali rimanenti, ad esempio contatti e applicazioni, che sarà necessario pulire.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="bf9d8-122">Eseguire la procedura seguente per pulire questi oggetti e assicurarsi di essere membri sia del gruppo Amministratore locale che del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="bf9d8-123">Si noti che ExUmContacts e PersistantChatEndPoints non sono disponibili in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="bf9d8-124">Se si dispone di Skype for Business Server 2019, i cmdlet corrispondenti nei passaggi seguenti devono essere omessi.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="bf9d8-125">Per verificare se sono presenti contatti o applicazioni associati alla distribuzione locale di Skype for Business Server, eseguire i cmdlet di PowerShell di Skype for Business Server seguenti.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="bf9d8-126">Esaminare gli elenchi di output dei cmdlet nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="bf9d8-127">Quindi, se gli oggetti possono essere rimossi, eseguire i cmdlet di PowerShell di Skype for Business Server seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="bf9d8-128">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bf9d8-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="bf9d8-129">Dopo aver completato tutti i passaggi preliminari, è possibile rimuovere la distribuzione di Skype for Business seguendo questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="bf9d8-130">Rimuovere logicamente la distribuzione di Skype for Business Server, ad eccezione di un singolo front-end, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="bf9d8-131">a.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-131">a.</span></span> <span data-ttu-id="bf9d8-132">Aggiornare la topologia di Skype for Business Server in modo che abbia un singolo pool front-end:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-132">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="bf9d8-133">In Generatore di topologie scaricare una nuova copia e passare al pool Frontend.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-133">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="bf9d8-134">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-134">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="bf9d8-135">In **Associazioni** deselezionare Associa pool di server perimetrali (per i componenti multimediali) e fare clic su **OK.** </span><span class="sxs-lookup"><span data-stu-id="bf9d8-135">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="bf9d8-136">Se sono presenti più pool front-end, rimuovere associazioni per tutti i pool rimanenti.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-136">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="bf9d8-137">Selezionare **Azione > Rimuovi distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-137">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="bf9d8-138">Selezionare **Azione > Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-138">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="bf9d8-139">b.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-139">b.</span></span> <span data-ttu-id="bf9d8-140">Dopo aver pubblicato la topologia, completare i passaggi aggiuntivi descritti nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-140">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="bf9d8-141">Rimuovere le directory conferenze di Skype for Business Server eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-141">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="bf9d8-142">Completare la disinstallazione della distribuzione di Skype for Business Server eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-142">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="bf9d8-143">Se questo passaggio restituisce un errore, aprire un ticket di supporto Microsoft per ottenere assistenza per la rimozione degli oggetti non obsoleti rimanenti.</span><span class="sxs-lookup"><span data-stu-id="bf9d8-143">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="bf9d8-144">Rimuovere il punto di controllo del servizio Archivio di gestione centrale eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-144">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="bf9d8-145">Annullare le modifiche a livello di foresta del dominio Active Directory di Skype for Business Server eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-145">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="bf9d8-146">Annullare le modifiche allo schema del dominio di Active Directory di Skype for Business Server eseguendo il cmdlet di PowerShell di Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="bf9d8-146">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="bf9d8-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf9d8-147">See also</span></span>

- [<span data-ttu-id="bf9d8-148">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bf9d8-148">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="bf9d8-149">Spostare tutti gli utenti necessari da locale a online</span><span class="sxs-lookup"><span data-stu-id="bf9d8-149">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="bf9d8-150">Disabilitare la configurazione ibrida</span><span class="sxs-lookup"><span data-stu-id="bf9d8-150">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="bf9d8-151">Spostare gli endpoint dell'applicazione ibrida da locale a online</span><span class="sxs-lookup"><span data-stu-id="bf9d8-151">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)











