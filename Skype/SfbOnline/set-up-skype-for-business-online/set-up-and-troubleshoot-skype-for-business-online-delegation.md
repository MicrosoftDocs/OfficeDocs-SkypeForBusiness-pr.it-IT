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
description: Questo articolo spiega come configurare e risolvere i problemi Skype for Business delega online. Questo articolo fornisce indicazioni per i suggerimenti per la configurazione, le procedure consigliate e i passaggi per la risoluzione dei problemi.
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239825"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="4f035-104">Configurare le deleghe e risolvere i problemi relativi alle deleghe in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="4f035-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="4f035-105">Questo articolo spiega come configurare e risolvere i problemi Skype for Business delega online.</span><span class="sxs-lookup"><span data-stu-id="4f035-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="4f035-106">Questo articolo fornisce indicazioni per i suggerimenti per la configurazione, le procedure consigliate e i passaggi per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="4f035-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="4f035-107">Linee guida e requisiti</span><span class="sxs-lookup"><span data-stu-id="4f035-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="4f035-108">Linee guida per la delega</span><span class="sxs-lookup"><span data-stu-id="4f035-108">Guidelines for delegation</span></span>

<span data-ttu-id="4f035-109">La configurazione e il corretto funzionamento della delega dipendono dall'utente che segue queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="4f035-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="4f035-110">È necessario usare il client Skype for Business 2015 completo con gli aggiornamenti più recenti o il client completo Skype for Business 2016.</span><span class="sxs-lookup"><span data-stu-id="4f035-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="4f035-111">È necessario usare il client Outlook 2013 con gli aggiornamenti più recenti o il client Outlook 2016 2013.</span><span class="sxs-lookup"><span data-stu-id="4f035-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="4f035-112">Assicurarsi che il delegante e il computer delegato Outlook un profilo di posta elettronica principale o predefinito.</span><span class="sxs-lookup"><span data-stu-id="4f035-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="4f035-113">Il profilo di posta elettronica deve contenere un solo account.</span><span class="sxs-lookup"><span data-stu-id="4f035-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="4f035-114">Skype for Business per il delegante e il delegato devono essere utenti online.</span><span class="sxs-lookup"><span data-stu-id="4f035-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="4f035-115">Inoltre, le Exchange Server per ogni account devono essere entrambe online o entrambe in locale.</span><span class="sxs-lookup"><span data-stu-id="4f035-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="4f035-116">Sia il delegato che il delegato devono usare la stessa versione principale di Outlook.</span><span class="sxs-lookup"><span data-stu-id="4f035-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="4f035-117">Il **valore dell'attributo EnableExchangeDelegateSync** deve essere impostato su **true** nei criteri client.</span><span class="sxs-lookup"><span data-stu-id="4f035-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="4f035-118">È possibile verificare questa impostazione eseguendo il cmdlet **Get-CSClientPolicy** nel modulo di PowerShell Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="4f035-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="4f035-119">Sia il delegato che il delegato devono essere connessi a Skype for Business e Outlook contemporaneamente su workstation diverse.</span><span class="sxs-lookup"><span data-stu-id="4f035-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="4f035-120">Le cassette postali condivise non sono supportate per Skype for Business delega online.</span><span class="sxs-lookup"><span data-stu-id="4f035-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="4f035-121">Questo perché la cassetta postale condivisa non ha l'elenco di controllo di accesso (ACL) **sendonbehalf.**</span><span class="sxs-lookup"><span data-stu-id="4f035-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="4f035-122">Skype for Business versione client</span><span class="sxs-lookup"><span data-stu-id="4f035-122">Skype for Business client version support</span></span>

||<span data-ttu-id="4f035-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="4f035-123">**Outlook 2013**</span></span>|<span data-ttu-id="4f035-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="4f035-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f035-125">**Client di base di Lync/Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="4f035-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="4f035-126">Non supportato</span><span class="sxs-lookup"><span data-stu-id="4f035-126">Not supported</span></span> |<span data-ttu-id="4f035-127">Non supportato</span><span class="sxs-lookup"><span data-stu-id="4f035-127">Not supported</span></span>
|<span data-ttu-id="4f035-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="4f035-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="4f035-129">Supportato</span><span class="sxs-lookup"><span data-stu-id="4f035-129">Supported</span></span>| <span data-ttu-id="4f035-130">Supportato</span><span class="sxs-lookup"><span data-stu-id="4f035-130">Supported</span></span>|
|<span data-ttu-id="4f035-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="4f035-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="4f035-132">Supportato</span><span class="sxs-lookup"><span data-stu-id="4f035-132">Supported</span></span>| <span data-ttu-id="4f035-133">Supportato</span><span class="sxs-lookup"><span data-stu-id="4f035-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="4f035-134">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="4f035-134">Licensing requirements</span></span>

<span data-ttu-id="4f035-135">**Enterprise Scenario di gestione delle licenze di E3**</span><span class="sxs-lookup"><span data-stu-id="4f035-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="4f035-136">**Licenza**</span><span class="sxs-lookup"><span data-stu-id="4f035-136">**License**</span></span>|<span data-ttu-id="4f035-137">**Client**</span><span class="sxs-lookup"><span data-stu-id="4f035-137">**Clients**</span></span>|<span data-ttu-id="4f035-138">**Note**</span><span class="sxs-lookup"><span data-stu-id="4f035-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f035-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="4f035-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="4f035-140">Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f035-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4f035-141">Skype for Business 2016 usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f035-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="4f035-142">Skype for Business Il client di base non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="4f035-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4f035-143">Per i client Mac, è possibile delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="4f035-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="4f035-144">Enterprise E3 con Sistema telefonico di Office 365 + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="4f035-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="4f035-145">Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f035-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4f035-146">Skype for Business 2016 usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f035-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4f035-147">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="4f035-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="4f035-148">Skype for Business Il client di base non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="4f035-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4f035-149">Per i client Mac, è possibile delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="4f035-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="4f035-150">**Enterprise Scenario di licenza E5**</span><span class="sxs-lookup"><span data-stu-id="4f035-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="4f035-151">**Licenza**</span><span class="sxs-lookup"><span data-stu-id="4f035-151">**License**</span></span>|<span data-ttu-id="4f035-152">**Client**</span><span class="sxs-lookup"><span data-stu-id="4f035-152">**Clients**</span></span>|<span data-ttu-id="4f035-153">**Note**</span><span class="sxs-lookup"><span data-stu-id="4f035-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f035-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="4f035-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="4f035-155">Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="4f035-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="4f035-156">Skype for Business 2016 usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f035-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="4f035-157">Skype for Business Il client di base non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="4f035-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4f035-158">Per i client Mac, è possibile delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="4f035-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="4f035-159">Enterprise E5 plus Office 365 Calling Plan</span><span class="sxs-lookup"><span data-stu-id="4f035-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="4f035-160">Skype for Business per Mac 2016</span><span class="sxs-lookup"><span data-stu-id="4f035-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="4f035-161">Lync 2013 (Skype for Business 2015) usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f035-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4f035-162">Skype for Business 2016 usato con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f035-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4f035-163">Lync per Mac 2011</span><span class="sxs-lookup"><span data-stu-id="4f035-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="4f035-164">Skype for Business Il client di base non supporta la delega.</span><span class="sxs-lookup"><span data-stu-id="4f035-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4f035-165">Per i client Mac, è possibile delegare le chiamate ma non le riunioni.</span><span class="sxs-lookup"><span data-stu-id="4f035-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="4f035-166">Configurare e verificare la delega</span><span class="sxs-lookup"><span data-stu-id="4f035-166">Set up and verify delegation</span></span>

<span data-ttu-id="4f035-167">Per configurare la delega Skype for Business Online, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="4f035-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="4f035-168">Per Windows client</span><span class="sxs-lookup"><span data-stu-id="4f035-168">For Windows clients</span></span>

 <span data-ttu-id="4f035-169">**Scheda Inoltro di chiamata**</span><span class="sxs-lookup"><span data-stu-id="4f035-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="4f035-170">Selezionare **Strumenti**  >  **Opzioni Inoltro** di chiamata  >  **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="4f035-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="4f035-171">Selezionare **Modifica membri delegati.**</span><span class="sxs-lookup"><span data-stu-id="4f035-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="4f035-172">Selezionare **Aggiungi**, selezionare il delegato da aggiungere e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f035-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="4f035-173">**Scheda Inoltro di chiamata non disponibile**</span><span class="sxs-lookup"><span data-stu-id="4f035-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="4f035-174">In Outlook selezionare **Account file** Impostazioni  >    >  **Delega accesso**  >  **aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="4f035-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="4f035-175">Individuare e aggiungere il nome della persona che sarà il delegato.</span><span class="sxs-lookup"><span data-stu-id="4f035-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="4f035-176">Selezionare **il** menu Calendario e quindi scegliere Editor (è possibile **leggere, creare e modificare elementi)**.</span><span class="sxs-lookup"><span data-stu-id="4f035-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="4f035-177">Per i client Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="4f035-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="4f035-178">**Scheda Inoltro di chiamata**</span><span class="sxs-lookup"><span data-stu-id="4f035-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="4f035-179">Se il client non  ha una scheda Inoltro  di chiamata con il collegamento Modifica membri delegati e il delegante si trova in un computer Mac, il delegante deve accedere a un computer basato su Windows per configurare la delega.</span><span class="sxs-lookup"><span data-stu-id="4f035-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="4f035-180">Questo è dovuto al fatto che i client Mac non possono effettuare connessioni MAPI e questo è un requisito per stabilire Skype for Business delega da Outlook.</span><span class="sxs-lookup"><span data-stu-id="4f035-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="4f035-181">Verifica dell'esito positivo</span><span class="sxs-lookup"><span data-stu-id="4f035-181">Verify success</span></span>

<span data-ttu-id="4f035-182">Se la configurazione ha esito positivo, il delegato dovrebbe visualizzare il messaggio Si è stati aggiunti  come delegato per il messaggio>Nome < e anche che viene creato il gruppo Persone per cui si gestiscono le chiamate. </span><span class="sxs-lookup"><span data-stu-id="4f035-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="4f035-183">Il delegante dovrebbe vedere che il **gruppo Delegati** è stato creato.</span><span class="sxs-lookup"><span data-stu-id="4f035-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f035-184">Le autorizzazioni di delega vengono in genere visualizzate entro 30 minuti dal processo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4f035-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="4f035-185">Tuttavia, il completamento di questo processo può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="4f035-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="4f035-186">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4f035-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="4f035-187">Problemi comuni</span><span class="sxs-lookup"><span data-stu-id="4f035-187">Common issues</span></span>

- > <span data-ttu-id="4f035-188">**Problema 1** La voce delegata continua  a essere visualizzata nel gruppo Persone per cui si gestiscono le chiamate dopo che il delegante ha rimosso il delegato dal client Outlook delegato.</span><span class="sxs-lookup"><span data-stu-id="4f035-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="4f035-189">**Risoluzione 1** Nel client Skype for Business fare clic con il pulsante destro del mouse sul delegato nel gruppo **Delegati** e quindi **scegliere Rimuovi dal gruppo**.</span><span class="sxs-lookup"><span data-stu-id="4f035-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="4f035-190">**Problema 2** Dopo che l'accesso delegato viene concesso tramite il client  Outlook, per il delegato non vengono visualizzati né il messaggio di conferma né il gruppo Persone per cui si gestiscono le chiamate.</span><span class="sxs-lookup"><span data-stu-id="4f035-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="4f035-191">**Risoluzione 2** Rimuovere la delega dal client Outlook, attendere circa 15 minuti per la replica e quindi aggiungere di nuovo il delegato.</span><span class="sxs-lookup"><span data-stu-id="4f035-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="4f035-192">Altri problemi comuni</span><span class="sxs-lookup"><span data-stu-id="4f035-192">Other common issues</span></span>

- <span data-ttu-id="4f035-193">La delega non funziona se viene superata la soglia di 25 deleganti e 25 delegati.</span><span class="sxs-lookup"><span data-stu-id="4f035-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="4f035-194">Il Skype for Business client Basic non è supportato.</span><span class="sxs-lookup"><span data-stu-id="4f035-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f035-195">Se si installa il client Skype for Business Basic, rimuoverà e interromperà la delega.</span><span class="sxs-lookup"><span data-stu-id="4f035-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="4f035-196">Se il **valore stato MAPI** non è **OK,** verificare che i valori **SIP** e **SMTP** corrispondano.</span><span class="sxs-lookup"><span data-stu-id="4f035-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f035-197">La visualizzazione dello stato MAPI come **OK** può richiedere alcuni minuti dopo l'avvio Skype for Business e Outlook.</span><span class="sxs-lookup"><span data-stu-id="4f035-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="4f035-198">La creazione di un gruppo di sicurezza e l'aggiunta di autorizzazioni di delega per il gruppo di sicurezza non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="4f035-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="4f035-199">MAPI non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="4f035-199">MAPI is unavailable.</span></span> <span data-ttu-id="4f035-200">Vedere [l'errore "MAPI non disponibile" nel client Skype for Business 2016.](https://support.microsoft.com/help/3147130)</span><span class="sxs-lookup"><span data-stu-id="4f035-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="4f035-201">La Exchange Online non è accessibile tramite il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4f035-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="4f035-202">In questo caso, eseguire il [test Outlook connettività](https://testconnectivity.microsoft.com/) per assicurarsi che passi.</span><span class="sxs-lookup"><span data-stu-id="4f035-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4f035-203">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4f035-203">Related topics</span></span>
[<span data-ttu-id="4f035-204">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="4f035-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="4f035-205">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="4f035-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
