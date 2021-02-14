---
title: Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Questo articolo spiega come configurare e risolvere i problemi relativi alla delega di Skype for Business online. Questo articolo fornisce indicazioni per la configurazione consigliata, procedure consigliate e procedure di risoluzione dei problemi.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010799"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="f1360-104">Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f1360-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="f1360-105">Questo articolo spiega come configurare e risolvere i problemi relativi alla delega di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="f1360-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="f1360-106">Questo articolo fornisce indicazioni per la configurazione consigliata, procedure consigliate e procedure di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="f1360-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="f1360-107">Linee guida e requisiti</span><span class="sxs-lookup"><span data-stu-id="f1360-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="f1360-108">Linee guida per la delega</span><span class="sxs-lookup"><span data-stu-id="f1360-108">Guidelines for delegation</span></span>

<span data-ttu-id="f1360-109">La configurazione e il corretto funzionamento della delega dipendono dalle linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1360-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="f1360-110">È necessario utilizzare il client completo Skype for Business 2015 con gli aggiornamenti più recenti o il client completo di Skype for Business 2016.</span><span class="sxs-lookup"><span data-stu-id="f1360-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="f1360-111">È necessario usare il client Outlook 2013 con gli aggiornamenti più recenti o con il client Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="f1360-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="f1360-112">Assicurarsi che il delegante e i computer delegati dispongono di un profilo di posta di Outlook che sia quello primario o quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="f1360-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="f1360-113">Il profilo di posta elettronica deve contenere un solo account.</span><span class="sxs-lookup"><span data-stu-id="f1360-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="f1360-114">Skype for Business per il delegante e il delegato devono essere utenti online.</span><span class="sxs-lookup"><span data-stu-id="f1360-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="f1360-115">Inoltre, le Exchange Server per ogni account devono essere entrambe online o entrambe in locale.</span><span class="sxs-lookup"><span data-stu-id="f1360-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="f1360-116">Sia il delegante che il delegato devono usare la stessa versione principale di Outlook.</span><span class="sxs-lookup"><span data-stu-id="f1360-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="f1360-117">Il **valore dell'attributo EnableExchangeDelegateSync** deve essere impostato su **true** nei criteri client.</span><span class="sxs-lookup"><span data-stu-id="f1360-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="f1360-118">Per verificare questa impostazione, eseguire il cmdlet **Get-CSClientPolicy** nel modulo PowerShell di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="f1360-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="f1360-119">Sia il delegante che il delegato devono aver effettuato l'accesso a Skype for Business e Outlook contemporaneamente su workstation diverse.</span><span class="sxs-lookup"><span data-stu-id="f1360-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="f1360-120">Le cassette postali condivise non sono supportate per la delega di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="f1360-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="f1360-121">Ciò è dovuto al fatto che la cassetta postale condivisa non ha l'elenco di controllo di accesso (ACL) **sendonbehalf.**</span><span class="sxs-lookup"><span data-stu-id="f1360-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="f1360-122">Supporto della versione del client Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f1360-122">Skype for Business client version support</span></span>

||<span data-ttu-id="f1360-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="f1360-123">**Outlook 2013**</span></span>|<span data-ttu-id="f1360-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="f1360-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1360-125">**Lync/Skype for Business Basic Client**</span><span class="sxs-lookup"><span data-stu-id="f1360-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="f1360-126">Non supportato</span><span class="sxs-lookup"><span data-stu-id="f1360-126">Not supported</span></span> |<span data-ttu-id="f1360-127">Non supportato</span><span class="sxs-lookup"><span data-stu-id="f1360-127">Not supported</span></span>
|<span data-ttu-id="f1360-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="f1360-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="f1360-129">Supportata</span><span class="sxs-lookup"><span data-stu-id="f1360-129">Supported</span></span>| <span data-ttu-id="f1360-130">Supportata</span><span class="sxs-lookup"><span data-stu-id="f1360-130">Supported</span></span>|
|<span data-ttu-id="f1360-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="f1360-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="f1360-132">Supportata</span><span class="sxs-lookup"><span data-stu-id="f1360-132">Supported</span></span>| <span data-ttu-id="f1360-133">Supportata</span><span class="sxs-lookup"><span data-stu-id="f1360-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="f1360-134">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="f1360-134">Licensing requirements</span></span>

<span data-ttu-id="f1360-135">**Scenario di gestione delle licenze Enterprise E3**</span><span class="sxs-lookup"><span data-stu-id="f1360-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="f1360-136">**Licenza**</span><span class="sxs-lookup"><span data-stu-id="f1360-136">**License**</span></span>|<span data-ttu-id="f1360-137">**Client**</span><span class="sxs-lookup"><span data-stu-id="f1360-137">**Clients**</span></span>|<span data-ttu-id="f1360-138">**Note**</span><span class="sxs-lookup"><span data-stu-id="f1360-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1360-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="f1360-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="f1360-140">Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1360-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f1360-141">Skype for Business 2016 utilizzato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1360-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="f1360-142">Il client Skype for Business Basic non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="f1360-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="f1360-143">Per i client Mac, è possibile delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="f1360-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="f1360-144">Enterprise E3 con Sistema telefonico Office 365 + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="f1360-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="f1360-145">Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1360-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f1360-146">Skype for Business 2016 utilizzato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1360-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f1360-147">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="f1360-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="f1360-148">Il client Skype for Business Basic non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="f1360-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="f1360-149">Per i client Mac, è possibile delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="f1360-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="f1360-150">**Scenario di gestione delle licenze Enterprise E5**</span><span class="sxs-lookup"><span data-stu-id="f1360-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="f1360-151">**Licenza**</span><span class="sxs-lookup"><span data-stu-id="f1360-151">**License**</span></span>|<span data-ttu-id="f1360-152">**Client**</span><span class="sxs-lookup"><span data-stu-id="f1360-152">**Clients**</span></span>|<span data-ttu-id="f1360-153">**Note**</span><span class="sxs-lookup"><span data-stu-id="f1360-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1360-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="f1360-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="f1360-155">Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="f1360-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="f1360-156">Skype for Business 2016 utilizzato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1360-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="f1360-157">Il client Skype for Business Basic non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="f1360-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="f1360-158">Per i client Mac, è possibile delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="f1360-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="f1360-159">Enterprise E5 plus Office 365 Calling Plan</span><span class="sxs-lookup"><span data-stu-id="f1360-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="f1360-160">Skype for Business per Mac 2016</span><span class="sxs-lookup"><span data-stu-id="f1360-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="f1360-161">Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1360-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f1360-162">Skype for Business 2016 utilizzato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1360-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="f1360-163">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="f1360-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="f1360-164">Il client Skype for Business Basic non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="f1360-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="f1360-165">Per i client Mac, è possibile delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="f1360-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="f1360-166">Configurare e verificare la delega</span><span class="sxs-lookup"><span data-stu-id="f1360-166">Set up and verify delegation</span></span>

<span data-ttu-id="f1360-167">Per configurare la delega di Skype for Business online, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="f1360-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="f1360-168">Per client Windows</span><span class="sxs-lookup"><span data-stu-id="f1360-168">For Windows clients</span></span>

 <span data-ttu-id="f1360-169">**Scheda Inoltro di chiamata**</span><span class="sxs-lookup"><span data-stu-id="f1360-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="f1360-170">Selezionare **Strumenti -**  >  **Impostazioni** inoltro di  >  **chiamata.**</span><span class="sxs-lookup"><span data-stu-id="f1360-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="f1360-171">Selezionare **Modifica i membri delegati.**</span><span class="sxs-lookup"><span data-stu-id="f1360-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="f1360-172">Selezionare **Aggiungi,** selezionare il delegato da aggiungere e quindi scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="f1360-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="f1360-173">**Scheda Inoltro di chiamata non disponibile**</span><span class="sxs-lookup"><span data-stu-id="f1360-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="f1360-174">In Outlook selezionare **Impostazioni account file**,  >  **Accesso** delegato  >  **-**  >  **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="f1360-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="f1360-175">Individuare e aggiungere il nome della persona che sarà il delegato.</span><span class="sxs-lookup"><span data-stu-id="f1360-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="f1360-176">Selezionare il menu **Calendario** e quindi **Selezionare Editor (lettura, creazione e modifica di elementi).**</span><span class="sxs-lookup"><span data-stu-id="f1360-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="f1360-177">Per client Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="f1360-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="f1360-178">**Scheda Inoltro di chiamata**</span><span class="sxs-lookup"><span data-stu-id="f1360-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="f1360-179">Se il client non ha una scheda **Inoltro** di chiamata con il collegamento Modifica i membri delegati personale e il delegante si trova in un computer Mac, il delegante deve accedere a un computer basato su Windows per poter configurare la delega. </span><span class="sxs-lookup"><span data-stu-id="f1360-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="f1360-180">Questo perché i client Mac non possono effettuare connessioni MAPI e questo è un requisito per stabilire la delega di Skype for Business da Outlook.</span><span class="sxs-lookup"><span data-stu-id="f1360-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="f1360-181">Verifica dell'esito positivo</span><span class="sxs-lookup"><span data-stu-id="f1360-181">Verify success</span></span>

<span data-ttu-id="f1360-182">Se la configurazione riesce, il delegato dovrebbe visualizzare il messaggio Che l'utente è stato aggiunto  come delegato per il>Nome del **<** e che è stato creato anche il gruppo Persone per cui si gestiscono le chiamate.</span><span class="sxs-lookup"><span data-stu-id="f1360-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="f1360-183">Il delegante dovrebbe vedere che è **stato** creato il gruppo Delegati.</span><span class="sxs-lookup"><span data-stu-id="f1360-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1360-184">Le autorizzazioni di delega vengono in genere visualizzate entro 30 minuti dal processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1360-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="f1360-185">Tuttavia, il completamento di questo processo può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="f1360-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="f1360-186">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="f1360-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="f1360-187">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="f1360-187">Common issues</span></span>

- > <span data-ttu-id="f1360-188">**Problema 1** L'immissione del delegato  continua a essere visualizzata nel gruppo Persone per cui si gestiscono le chiamate dopo che il delegante ha rimosso il delegato dal client Outlook.</span><span class="sxs-lookup"><span data-stu-id="f1360-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="f1360-189">**Risoluzione 1** Nel client Skype for Business fare clic  con il pulsante destro del mouse sul delegato nel gruppo Delegati e quindi scegliere **Rimuovi dal gruppo.**</span><span class="sxs-lookup"><span data-stu-id="f1360-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="f1360-190">**Problema 2** Dopo aver concesso l'accesso come delegato tramite  il client Outlook, per il delegato non vengono visualizzati né il messaggio di conferma né il gruppo Persone per cui si gestiscono le chiamate.</span><span class="sxs-lookup"><span data-stu-id="f1360-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="f1360-191">**Risoluzione 2** Rimuovere la delega dal client Outlook, attendere circa 15 minuti per la replica e quindi aggiungere di nuovo il delegato.</span><span class="sxs-lookup"><span data-stu-id="f1360-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="f1360-192">Altri problemi comuni</span><span class="sxs-lookup"><span data-stu-id="f1360-192">Other common issues</span></span>

- <span data-ttu-id="f1360-193">La delega non funziona se viene superata la soglia di 25 deleganti e 25 delegati.</span><span class="sxs-lookup"><span data-stu-id="f1360-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="f1360-194">Il client Skype for Business Basic non è supportato.</span><span class="sxs-lookup"><span data-stu-id="f1360-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f1360-195">Se installi il client Skype for Business Basic, questo rimuoverà e interromperà la delega.</span><span class="sxs-lookup"><span data-stu-id="f1360-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="f1360-196">Se il **valore di Stato MAPI** non è **OK,** verificare che i valori **SIP** e **SMTP** corrispondano.</span><span class="sxs-lookup"><span data-stu-id="f1360-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f1360-197">Dopo l'avvio di Skype for Business  e Outlook, lo stato MAPI può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="f1360-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="f1360-198">La creazione di un gruppo di sicurezza e l'aggiunta di autorizzazioni di delega per tale gruppo di sicurezza non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f1360-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="f1360-199">MAPI non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="f1360-199">MAPI is unavailable.</span></span> <span data-ttu-id="f1360-200">Vedere [l'errore "MAPI non disponibile" nel client Skype for Business 2016.](https://support.microsoft.com/help/3147130)</span><span class="sxs-lookup"><span data-stu-id="f1360-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="f1360-201">La cassetta postale di Exchange Online non è accessibile tramite il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f1360-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="f1360-202">In questo caso, eseguire il [test di connettività di Outlook](https://testconnectivity.microsoft.com/) per assicurarsi che passi.</span><span class="sxs-lookup"><span data-stu-id="f1360-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="f1360-203">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f1360-203">Related topics</span></span>
[<span data-ttu-id="f1360-204">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f1360-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f1360-205">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="f1360-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
