---
title: Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: In questo articolo viene illustrato come impostare e risolvere i problemi Skype per la delega Business Online. In questo articolo vengono fornite indicazioni per suggerimenti per il programma di installazione, procedure consigliate e istruzioni sulla risoluzione dei problemi.
ms.openlocfilehash: e3131b28be1ad01e0965b2739dc152a627826d5e
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546676"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="fcd68-104">Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="fcd68-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="fcd68-105">In questo articolo viene illustrato come impostare e risolvere i problemi Skype per la delega Business Online.</span><span class="sxs-lookup"><span data-stu-id="fcd68-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="fcd68-106">In questo articolo vengono fornite indicazioni per suggerimenti per il programma di installazione, procedure consigliate e istruzioni sulla risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="fcd68-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="fcd68-107">Requisiti e le linee guida</span><span class="sxs-lookup"><span data-stu-id="fcd68-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="fcd68-108">Linee guida per la delega</span><span class="sxs-lookup"><span data-stu-id="fcd68-108">Guidelines for delegation</span></span>

<span data-ttu-id="fcd68-109">Configurazione e il recupero di delega per il corretto funzionamento dipende è seguendo le indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fcd68-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="fcd68-110">È necessario utilizzare Skype per 2015 Business completo client con gli aggiornamenti più recenti o le Skype per client completo 2016 Business.</span><span class="sxs-lookup"><span data-stu-id="fcd68-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="fcd68-111">È necessario utilizzare il client di Outlook 2013 con gli aggiornamenti più recenti o del client Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="fcd68-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="fcd68-112">Verificare che il delegante e computer di delegato di un profilo di posta elettronica di Outlook che è il server principale o il profilo predefinito.</span><span class="sxs-lookup"><span data-stu-id="fcd68-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="fcd68-113">Un profilo di posta elettronica sia presente un solo account.</span><span class="sxs-lookup"><span data-stu-id="fcd68-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="fcd68-114">Skype per le aziende per il delegante e il delegato deve essere utenti in linea.</span><span class="sxs-lookup"><span data-stu-id="fcd68-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="fcd68-115">Inoltre, le cassette postali Exchange Server per ogni account deve essere entrambi Online o locale possono essere entrambi.</span><span class="sxs-lookup"><span data-stu-id="fcd68-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="fcd68-116">Delegator sia il delegato devono utilizzare la stessa versione principale di Outlook.</span><span class="sxs-lookup"><span data-stu-id="fcd68-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="fcd68-117">Il valore dell'attributo **EnableExchangeDelegateSync** deve impostare su **true** nel criterio del client.</span><span class="sxs-lookup"><span data-stu-id="fcd68-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="fcd68-118">È possibile verificare questa impostazione eseguendo il cmdlet **Get-CSClientPolicy** in Skype di funzionalità di Business Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcd68-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="fcd68-119">Delegator sia il delegato devono eseguire l'accesso a Skype per le aziende e Outlook contemporaneamente nella workstation diverse.</span><span class="sxs-lookup"><span data-stu-id="fcd68-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="fcd68-120">Cassette postali condivise non sono supportate per Skype per la delega Business Online.</span><span class="sxs-lookup"><span data-stu-id="fcd68-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="fcd68-121">Ciò avviene perché l'elenco di controllo di accesso (ACL) **sendonbehalf** non dispone di cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="fcd68-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="fcd68-122">Skype per il supporto di versione client Business</span><span class="sxs-lookup"><span data-stu-id="fcd68-122">Skype for Business client version support</span></span>

||<span data-ttu-id="fcd68-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="fcd68-123">**Outlook 2013**</span></span>|<span data-ttu-id="fcd68-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="fcd68-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcd68-125">**Lync/Skype per Client di base di Business**</span><span class="sxs-lookup"><span data-stu-id="fcd68-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="fcd68-126">Non supportato</span><span class="sxs-lookup"><span data-stu-id="fcd68-126">Not supported</span></span> |<span data-ttu-id="fcd68-127">Non supportato</span><span class="sxs-lookup"><span data-stu-id="fcd68-127">Not supported</span></span>
|<span data-ttu-id="fcd68-128">**Skype per Business 2015**</span><span class="sxs-lookup"><span data-stu-id="fcd68-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="fcd68-129">È supportata</span><span class="sxs-lookup"><span data-stu-id="fcd68-129">Supported</span></span>| <span data-ttu-id="fcd68-130">È supportata</span><span class="sxs-lookup"><span data-stu-id="fcd68-130">Supported</span></span>|
|<span data-ttu-id="fcd68-131">**Skype per Business 2016**</span><span class="sxs-lookup"><span data-stu-id="fcd68-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="fcd68-132">È supportata</span><span class="sxs-lookup"><span data-stu-id="fcd68-132">Supported</span></span>| <span data-ttu-id="fcd68-133">È supportata</span><span class="sxs-lookup"><span data-stu-id="fcd68-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="fcd68-134">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="fcd68-134">Licensing requirements</span></span>

<span data-ttu-id="fcd68-135">**Scenario di gestione delle licenze aziendale E3**</span><span class="sxs-lookup"><span data-stu-id="fcd68-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="fcd68-136">**Licenza**</span><span class="sxs-lookup"><span data-stu-id="fcd68-136">**License**</span></span>|<span data-ttu-id="fcd68-137">**Client**</span><span class="sxs-lookup"><span data-stu-id="fcd68-137">**Clients**</span></span>|<span data-ttu-id="fcd68-138">**Note**</span><span class="sxs-lookup"><span data-stu-id="fcd68-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcd68-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="fcd68-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="fcd68-140">Lync 2013 (Skype per 2015 Business) utilizzato con 2016 Outlook o Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="fcd68-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fcd68-141">Skype per 2016 Business utilizzate con 2016 Outlook o Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="fcd68-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="fcd68-142">Skype per client Business Basic non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="fcd68-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fcd68-143">Per i client Mac, è possibile delegare le chiamate ma non in riunioni.</span><span class="sxs-lookup"><span data-stu-id="fcd68-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="fcd68-144">Aziendale E3 con sistema telefonico in Office 365 + Office 365 xCalling piano</span><span class="sxs-lookup"><span data-stu-id="fcd68-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="fcd68-145">Lync 2013 (Skype per 2015 Business) utilizzato con 2016 Outlook o Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="fcd68-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fcd68-146">Skype per 2016 Business utilizzate con 2016 Outlook o Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="fcd68-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fcd68-147">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="fcd68-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="fcd68-148">Skype per client Business Basic non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="fcd68-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fcd68-149">Per i client Mac, è possibile delegare le chiamate ma non in riunioni.</span><span class="sxs-lookup"><span data-stu-id="fcd68-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="fcd68-150">**Scenario di licenza Enterprise E5**</span><span class="sxs-lookup"><span data-stu-id="fcd68-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="fcd68-151">**Licenza**</span><span class="sxs-lookup"><span data-stu-id="fcd68-151">**License**</span></span>|<span data-ttu-id="fcd68-152">**Client**</span><span class="sxs-lookup"><span data-stu-id="fcd68-152">**Clients**</span></span>|<span data-ttu-id="fcd68-153">**Note**</span><span class="sxs-lookup"><span data-stu-id="fcd68-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcd68-154">E5 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fcd68-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="fcd68-155">Lync 2013 (Skype per 2015 Business) utilizzato con 2016 Outlook o Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="fcd68-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="fcd68-156">Skype per 2016 Business utilizzate con 2016 Outlook o Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="fcd68-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="fcd68-157">Skype per client Business Basic non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="fcd68-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fcd68-158">Per i client Mac, è possibile delegare le chiamate ma non in riunioni.</span><span class="sxs-lookup"><span data-stu-id="fcd68-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="fcd68-159">Enterprise E5 e piano di chiamata di Office 365</span><span class="sxs-lookup"><span data-stu-id="fcd68-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="fcd68-160">Skype per le aziende per Mac 2016</span><span class="sxs-lookup"><span data-stu-id="fcd68-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="fcd68-161">Lync 2013 (Skype per 2015 Business) utilizzato con 2016 Outlook o Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="fcd68-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fcd68-162">Skype per 2016 Business utilizzate con 2016 Outlook o Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="fcd68-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fcd68-163">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="fcd68-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="fcd68-164">Skype per client Business Basic non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="fcd68-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fcd68-165">Per i client Mac, è possibile delegare le chiamate ma non in riunioni.</span><span class="sxs-lookup"><span data-stu-id="fcd68-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="fcd68-166">Impostare e verificare la delega</span><span class="sxs-lookup"><span data-stu-id="fcd68-166">Set up and verify delegation</span></span>

<span data-ttu-id="fcd68-167">Per configurare Skype per la delega Business Online, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="fcd68-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="fcd68-168">Per i client Windows</span><span class="sxs-lookup"><span data-stu-id="fcd68-168">For Windows clients</span></span>

 <span data-ttu-id="fcd68-169">**Scheda inoltro di chiamata.**</span><span class="sxs-lookup"><span data-stu-id="fcd68-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="fcd68-170">Selezionare **Strumenti** > **Opzioni** > **le impostazioni di inoltro di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="fcd68-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="fcd68-171">Selezionare **Modifica i membri delegati personali**.</span><span class="sxs-lookup"><span data-stu-id="fcd68-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="fcd68-172">Selezionare **Aggiungi**, selezionare il delegato che si desidera aggiungere e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcd68-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="fcd68-173">**Nessuna scheda inoltro di chiamata**</span><span class="sxs-lookup"><span data-stu-id="fcd68-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="fcd68-174">In Outlook, selezionare **File** > **Le impostazioni degli Account** > **Accesso delegato** > **Add**.</span><span class="sxs-lookup"><span data-stu-id="fcd68-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="fcd68-175">Individuare e quindi aggiungere il nome della persona che verrà il delegato.</span><span class="sxs-lookup"><span data-stu-id="fcd68-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="fcd68-176">Selezionare il menu **calendario** e quindi selezionare **Editor (lettura, creare e modificare elementi)**.</span><span class="sxs-lookup"><span data-stu-id="fcd68-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="fcd68-177">Per i client Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="fcd68-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="fcd68-178">**Scheda inoltro di chiamata.**</span><span class="sxs-lookup"><span data-stu-id="fcd68-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="fcd68-179">Se il client non dispone di una scheda **Inoltro di chiamata** con collegamento **Modifica i membri delegati personali** e delegante si trova in un computer Mac, delegante deve effettuare l'accesso a un computer basato su Windows per impostare la delega.</span><span class="sxs-lookup"><span data-stu-id="fcd68-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="fcd68-180">Ciò avviene perché i client Mac non possono effettuare connessioni MAPI e questo è un requisito per stabilire Skype per la delega Business da Outlook.</span><span class="sxs-lookup"><span data-stu-id="fcd68-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="fcd68-181">Verificare l'esito positivo</span><span class="sxs-lookup"><span data-stu-id="fcd68-181">Verify success</span></span>

<span data-ttu-id="fcd68-182">Se l'installazione viene eseguita correttamente, il delegato verrà visualizzato l'oggetto **è stato aggiunto come delegato per < nome >** messaggio e che viene creato il gruppo **persone per utente gestisce le chiamate** .</span><span class="sxs-lookup"><span data-stu-id="fcd68-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="fcd68-183">Delegante dovrebbero essere visualizzati che viene creato il gruppo **delegati** .</span><span class="sxs-lookup"><span data-stu-id="fcd68-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fcd68-184">Autorizzazioni di delega in genere vengono visualizzati all'interno di 30 minuti di processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="fcd68-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="fcd68-185">Tuttavia, il processo può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="fcd68-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="fcd68-186">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="fcd68-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="fcd68-187">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="fcd68-187">Common issues</span></span>

- > <span data-ttu-id="fcd68-188">**Problema 1** La voce del delegato viene ancora visualizzato nel gruppo di **persone per utente gestisce le chiamate** dopo che il delegante è rimosso il delegato dal client di Outlook.</span><span class="sxs-lookup"><span data-stu-id="fcd68-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="fcd68-189">**Soluzione 1** In Skype per client di Business, destro il delegato nel gruppo **delegati** e quindi scegliere **Rimuovi dal gruppo**.</span><span class="sxs-lookup"><span data-stu-id="fcd68-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="fcd68-190">**Problema 2** Dopo che un client Outlook viene concesso l'accesso delegato, il messaggio di conferma e il gruppo **persone per utente gestisce le chiamate** non vengono visualizzati per il delegato.</span><span class="sxs-lookup"><span data-stu-id="fcd68-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="fcd68-191">**Soluzione 2** Rimuovere la delega dal client Outlook, attendere 15 minuti per la replica e quindi aggiungere di nuovo il delegato.</span><span class="sxs-lookup"><span data-stu-id="fcd68-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="fcd68-192">Altri problemi comuni</span><span class="sxs-lookup"><span data-stu-id="fcd68-192">Other common issues</span></span>

- <span data-ttu-id="fcd68-193">Delega non funziona se supera la soglia di 25 delegante e 25 delegati.</span><span class="sxs-lookup"><span data-stu-id="fcd68-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="fcd68-194">Skype per client Business Basic non è supportato.</span><span class="sxs-lookup"><span data-stu-id="fcd68-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fcd68-195">Se si installa Skype per client di base di Business, rimuoverà e interrompere la delega.</span><span class="sxs-lookup"><span data-stu-id="fcd68-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="fcd68-196">Se il valore di **Stato MAPI** non **OK**, verificare che i valori **SIP** e **SMTP** corrispondano.</span><span class="sxs-lookup"><span data-stu-id="fcd68-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fcd68-197">È possibile richiedere alcuni minuti per lo stato MAPI visualizzare come **OK** dopo aver avviato prima Skype per le aziende e Outlook.</span><span class="sxs-lookup"><span data-stu-id="fcd68-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="fcd68-198">Creare un gruppo di sicurezza e aggiungere le autorizzazioni di delega per tale gruppo di sicurezza non è supportato.</span><span class="sxs-lookup"><span data-stu-id="fcd68-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="fcd68-199">MAPI non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="fcd68-199">MAPI is unavailable.</span></span> <span data-ttu-id="fcd68-200">Vedere [l'errore "MAPI non disponibile" in Skype per client 2016 Business](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="fcd68-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="fcd68-201">La cassetta postale di Exchange Online non è accessibile tramite Skype per client di Business.</span><span class="sxs-lookup"><span data-stu-id="fcd68-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="fcd68-202">In tal caso, eseguire il [test di connettività Outlook](https://testconnectivity.microsoft.com/) per assicurarsi che viene passato.</span><span class="sxs-lookup"><span data-stu-id="fcd68-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fcd68-203">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fcd68-203">Related topics</span></span>
[<span data-ttu-id="fcd68-204">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="fcd68-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fcd68-205">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="fcd68-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
