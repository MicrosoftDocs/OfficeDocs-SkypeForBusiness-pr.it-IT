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
description: Questo articolo spiega come configurare e risolvere i problemi di delega di Skype for business online. In questo articolo vengono fornite indicazioni per suggerimenti per la configurazione, procedure consigliate e procedure per la risoluzione dei problemi.
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706481"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="3b014-104">Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3b014-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="3b014-105">Questo articolo spiega come configurare e risolvere i problemi di delega di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="3b014-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="3b014-106">In questo articolo vengono fornite indicazioni per suggerimenti per la configurazione, procedure consigliate e procedure per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="3b014-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="3b014-107">Linee guida e requisiti</span><span class="sxs-lookup"><span data-stu-id="3b014-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="3b014-108">Linee guida per la delega</span><span class="sxs-lookup"><span data-stu-id="3b014-108">Guidelines for delegation</span></span>

<span data-ttu-id="3b014-109">La configurazione e l'ottenimento della delega per il corretto funzionamento dipende dalle seguenti linee guida:</span><span class="sxs-lookup"><span data-stu-id="3b014-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="3b014-110">È necessario usare il client completo di Skype for business 2015 con gli aggiornamenti più recenti o con il client completo Skype for business 2016.</span><span class="sxs-lookup"><span data-stu-id="3b014-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="3b014-111">È necessario usare il client Outlook 2013 con gli aggiornamenti più recenti o con il client Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="3b014-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="3b014-112">Verificare che il delegante e i computer delegati dispongano di un profilo di posta di Outlook che sia il profilo principale o quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="3b014-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="3b014-113">Il profilo di posta elettronica deve contenere un solo account.</span><span class="sxs-lookup"><span data-stu-id="3b014-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="3b014-114">Skype for business per il delegante e il delegato devono essere utenti online.</span><span class="sxs-lookup"><span data-stu-id="3b014-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="3b014-115">Inoltre, le cassette postali di Exchange Server per ogni account devono essere entrambe online o entrambe in locale.</span><span class="sxs-lookup"><span data-stu-id="3b014-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="3b014-116">Sia il delegante che il delegato devono usare la stessa versione principale di Outlook.</span><span class="sxs-lookup"><span data-stu-id="3b014-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="3b014-117">Il valore dell'attributo **EnableExchangeDelegateSync** deve essere impostato su **true** nei criteri client.</span><span class="sxs-lookup"><span data-stu-id="3b014-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="3b014-118">Puoi verificare questa impostazione eseguendo il cmdlet **Get-CsClientPolicy** nel modulo di PowerShell per Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="3b014-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="3b014-119">Sia il delegante che il delegato devono avere effettuato l'accesso a Skype for business e Outlook contemporaneamente su workstation diverse.</span><span class="sxs-lookup"><span data-stu-id="3b014-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="3b014-120">Le cassette postali condivise non sono supportate per la delega di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="3b014-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="3b014-121">Il motivo è che la cassetta postale condivisa non ha l'elenco di controllo di accesso (ACL) di **SendOnBehalf** .</span><span class="sxs-lookup"><span data-stu-id="3b014-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="3b014-122">Supporto della versione client di Skype for business</span><span class="sxs-lookup"><span data-stu-id="3b014-122">Skype for Business client version support</span></span>

||<span data-ttu-id="3b014-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="3b014-123">**Outlook 2013**</span></span>|<span data-ttu-id="3b014-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="3b014-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b014-125">**Client Basic Lync/Skype for business**</span><span class="sxs-lookup"><span data-stu-id="3b014-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="3b014-126">Non supportato</span><span class="sxs-lookup"><span data-stu-id="3b014-126">Not supported</span></span> |<span data-ttu-id="3b014-127">Non supportato</span><span class="sxs-lookup"><span data-stu-id="3b014-127">Not supported</span></span>
|<span data-ttu-id="3b014-128">**Skype for business 2015**</span><span class="sxs-lookup"><span data-stu-id="3b014-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="3b014-129">Supportati</span><span class="sxs-lookup"><span data-stu-id="3b014-129">Supported</span></span>| <span data-ttu-id="3b014-130">Supportati</span><span class="sxs-lookup"><span data-stu-id="3b014-130">Supported</span></span>|
|<span data-ttu-id="3b014-131">**Skype for business 2016**</span><span class="sxs-lookup"><span data-stu-id="3b014-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="3b014-132">Supportati</span><span class="sxs-lookup"><span data-stu-id="3b014-132">Supported</span></span>| <span data-ttu-id="3b014-133">Supportati</span><span class="sxs-lookup"><span data-stu-id="3b014-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="3b014-134">Requisiti per le licenze</span><span class="sxs-lookup"><span data-stu-id="3b014-134">Licensing requirements</span></span>

<span data-ttu-id="3b014-135">**Scenario di licenze Enterprise E3**</span><span class="sxs-lookup"><span data-stu-id="3b014-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="3b014-136">**Licenza**</span><span class="sxs-lookup"><span data-stu-id="3b014-136">**License**</span></span>|<span data-ttu-id="3b014-137">**Client**</span><span class="sxs-lookup"><span data-stu-id="3b014-137">**Clients**</span></span>|<span data-ttu-id="3b014-138">**Note**</span><span class="sxs-lookup"><span data-stu-id="3b014-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b014-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="3b014-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="3b014-140">Lync 2013 (Skype for business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b014-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3b014-141">Skype for business 2016 usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b014-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="3b014-142">Skype for Business Basic client non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="3b014-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="3b014-143">Per i client Mac puoi delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="3b014-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="3b014-144">Enterprise E3 con Office 365 Phone System + Office 365 xCalling piano</span><span class="sxs-lookup"><span data-stu-id="3b014-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="3b014-145">Lync 2013 (Skype for business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b014-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3b014-146">Skype for business 2016 usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b014-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3b014-147">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="3b014-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="3b014-148">Skype for Business Basic client non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="3b014-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="3b014-149">Per i client Mac puoi delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="3b014-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="3b014-150">**Scenario di licenze Enterprise E5**</span><span class="sxs-lookup"><span data-stu-id="3b014-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="3b014-151">**Licenza**</span><span class="sxs-lookup"><span data-stu-id="3b014-151">**License**</span></span>|<span data-ttu-id="3b014-152">**Client**</span><span class="sxs-lookup"><span data-stu-id="3b014-152">**Clients**</span></span>|<span data-ttu-id="3b014-153">**Note**</span><span class="sxs-lookup"><span data-stu-id="3b014-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b014-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="3b014-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="3b014-155">Lync 2013 (Skype for business 2015) usato con Outlook 2013 o Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="3b014-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="3b014-156">Skype for business 2016 usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b014-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="3b014-157">Skype for Business Basic client non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="3b014-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="3b014-158">Per i client Mac puoi delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="3b014-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="3b014-159">Piano per le chiamate Enterprise E5 Plus Office 365</span><span class="sxs-lookup"><span data-stu-id="3b014-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="3b014-160">Skype for business per Mac 2016</span><span class="sxs-lookup"><span data-stu-id="3b014-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="3b014-161">Lync 2013 (Skype for business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b014-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3b014-162">Skype for business 2016 usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b014-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3b014-163">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="3b014-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="3b014-164">Skype for Business Basic client non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="3b014-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="3b014-165">Per i client Mac puoi delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="3b014-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="3b014-166">Configurare e verificare la delega</span><span class="sxs-lookup"><span data-stu-id="3b014-166">Set up and verify delegation</span></span>

<span data-ttu-id="3b014-167">Per configurare la delega di Skype for business online, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b014-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="3b014-168">Per i client Windows</span><span class="sxs-lookup"><span data-stu-id="3b014-168">For Windows clients</span></span>

 <span data-ttu-id="3b014-169">**Scheda inoltro di chiamata**</span><span class="sxs-lookup"><span data-stu-id="3b014-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="3b014-170">Selezionare \*\*\*\* > \*\*\*\* opzioni > strumenti**inoltro di chiamata impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="3b014-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="3b014-171">Selezionare **Modifica membri delegati**.</span><span class="sxs-lookup"><span data-stu-id="3b014-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="3b014-172">Selezionare **Aggiungi**, selezionare il delegato che si vuole aggiungere e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b014-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="3b014-173">**Scheda inoltro di chiamata**</span><span class="sxs-lookup"><span data-stu-id="3b014-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="3b014-174">In > Outlook selezionare**Aggiungi\*\*\*\*accesso delegati\*\*\*\*Impostazioni** > account **file** > .</span><span class="sxs-lookup"><span data-stu-id="3b014-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="3b014-175">Individuare e quindi aggiungere il nome della persona che sta per essere il delegato.</span><span class="sxs-lookup"><span data-stu-id="3b014-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="3b014-176">Selezionare il menu **Calendario** , quindi selezionare **Editor (in grado di leggere, creare e modificare gli elementi)**.</span><span class="sxs-lookup"><span data-stu-id="3b014-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="3b014-177">Per client Mac-Lync</span><span class="sxs-lookup"><span data-stu-id="3b014-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="3b014-178">**Scheda inoltro di chiamata**</span><span class="sxs-lookup"><span data-stu-id="3b014-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="3b014-179">Se il client non ha una scheda **inoltro di chiamata** con il collegamento **modifica i membri delegati** e il delegante si trova in un computer Mac, il delegante deve accedere a un computer basato su Windows per configurare la delega.</span><span class="sxs-lookup"><span data-stu-id="3b014-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="3b014-180">Questo perché i client Mac non possono eseguire connessioni MAPI e questo è un requisito per stabilire la delega di Skype for business da Outlook.</span><span class="sxs-lookup"><span data-stu-id="3b014-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="3b014-181">Verificare il successo</span><span class="sxs-lookup"><span data-stu-id="3b014-181">Verify success</span></span>

<span data-ttu-id="3b014-182">Se il programma di installazione ha esito positivo, il delegato deve vedere l' **utente che è stato aggiunto come delegato per < nome>** messaggio e che vengono create anche le **persone che gestiscono le chiamate per** il gruppo.</span><span class="sxs-lookup"><span data-stu-id="3b014-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="3b014-183">Il delegante deve verificare che il gruppo **delegati** sia stato creato.</span><span class="sxs-lookup"><span data-stu-id="3b014-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b014-184">Le autorizzazioni di delega vengono in genere visualizzate entro 30 minuti dal processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3b014-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="3b014-185">Tuttavia, questo processo può richiedere fino a 24 ore per il completamento.</span><span class="sxs-lookup"><span data-stu-id="3b014-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="3b014-186">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="3b014-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="3b014-187">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="3b014-187">Common issues</span></span>

- > <span data-ttu-id="3b014-188">**Problema 1** La voce del delegato continua a essere visualizzata nelle **persone che gestiscono le chiamate per** il gruppo dopo che il delegante ha rimosso il delegato dal client di Outlook.</span><span class="sxs-lookup"><span data-stu-id="3b014-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="3b014-189">**Risoluzione 1** Nel client Skype for business fare clic con il pulsante destro del mouse sul delegato nel gruppo **delegati** e quindi scegliere **Rimuovi dal gruppo**.</span><span class="sxs-lookup"><span data-stu-id="3b014-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="3b014-190">**Problema 2** Dopo aver concesso l'accesso al delegato tramite il client Outlook, non viene visualizzato il messaggio di conferma né le **persone che gestiscono le chiamate per** il gruppo per il delegato.</span><span class="sxs-lookup"><span data-stu-id="3b014-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="3b014-191">**Risoluzione 2** Rimuovere la delega dal client Outlook, attendere circa 15 minuti per la replica e quindi aggiungere di nuovo il delegato.</span><span class="sxs-lookup"><span data-stu-id="3b014-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="3b014-192">Altri problemi comuni</span><span class="sxs-lookup"><span data-stu-id="3b014-192">Other common issues</span></span>

- <span data-ttu-id="3b014-193">La delega non funziona se viene superata la soglia di 25 delegati e di 25 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="3b014-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="3b014-194">Il client di base di Skype for business non è supportato.</span><span class="sxs-lookup"><span data-stu-id="3b014-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b014-195">Se si installa il client di Skype for Business Basic, verrà rimosso e interrotta la delega.</span><span class="sxs-lookup"><span data-stu-id="3b014-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="3b014-196">Se il valore di **stato MAPI** non è **OK**, verificare che i valori **SIP** e **SMTP** corrispondano.</span><span class="sxs-lookup"><span data-stu-id="3b014-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b014-197">Dopo aver avviato Skype for business e Outlook, è possibile che lo stato MAPI venga visualizzato in diversi minuti come **OK** .</span><span class="sxs-lookup"><span data-stu-id="3b014-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="3b014-198">La creazione di un gruppo di sicurezza e l'aggiunta delle autorizzazioni di delega per il gruppo di sicurezza non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="3b014-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="3b014-199">MAPI non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="3b014-199">MAPI is unavailable.</span></span> <span data-ttu-id="3b014-200">Vedere [errore "MAPI non disponibile" nel client di Skype for Business 2016](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="3b014-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="3b014-201">La cassetta postale di Exchange Online non è accessibile tramite il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3b014-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="3b014-202">In questo caso, Esegui il [test di connettività di Outlook](https://testconnectivity.microsoft.com/) per verificare che venga superato.</span><span class="sxs-lookup"><span data-stu-id="3b014-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="3b014-203">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3b014-203">Related topics</span></span>
[<span data-ttu-id="3b014-204">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3b014-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="3b014-205">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="3b014-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
