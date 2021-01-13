---
title: Bloccare o sbloccare il PIN di un utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Riepilogo: bloccare o sbloccare il PIN per le conferenze telefoniche con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828366"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="0e4b7-103">Bloccare o sbloccare il PIN di un utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0e4b7-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="0e4b7-104">**Riepilogo:** Bloccare o sbloccare il PIN per le conferenze telefoniche con accesso esterno di un utente per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="0e4b7-105">È possibile bloccare o sbloccare il PIN di un utente dalla sezione **utenti** del pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="0e4b7-106">Per bloccare il PIN di un utente nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0e4b7-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0e4b7-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0e4b7-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0e4b7-109">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0e4b7-110">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="0e4b7-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="0e4b7-111">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="0e4b7-112">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="0e4b7-113">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="0e4b7-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="0e4b7-114">a.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-114">a.</span></span> <span data-ttu-id="0e4b7-115">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="0e4b7-116">b.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-116">b.</span></span> <span data-ttu-id="0e4b7-117">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="0e4b7-118">c.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-118">c.</span></span> <span data-ttu-id="0e4b7-119">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="0e4b7-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="0e4b7-120">d.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-120">d.</span></span> <span data-ttu-id="0e4b7-121">A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0e4b7-122">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="0e4b7-123">e.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-123">e.</span></span> <span data-ttu-id="0e4b7-124">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-124">Click **Find**.</span></span>
    
   <span data-ttu-id="0e4b7-125">f.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-125">f.</span></span> <span data-ttu-id="0e4b7-126">Fare clic sull'utente, su **Azione** e quindi su **Blocca PIN**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="0e4b7-127">Per sbloccare il PIN di un utente nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0e4b7-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0e4b7-128">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0e4b7-129">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0e4b7-130">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="0e4b7-131">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="0e4b7-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="0e4b7-132">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="0e4b7-133">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="0e4b7-134">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="0e4b7-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="0e4b7-135">a.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-135">a.</span></span> <span data-ttu-id="0e4b7-136">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="0e4b7-137">b.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-137">b.</span></span> <span data-ttu-id="0e4b7-138">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="0e4b7-139">c.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-139">c.</span></span> <span data-ttu-id="0e4b7-140">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="0e4b7-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="0e4b7-141">d.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-141">d.</span></span> <span data-ttu-id="0e4b7-142">A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0e4b7-143">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="0e4b7-144">e.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-144">e.</span></span> <span data-ttu-id="0e4b7-145">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-145">Click **Find**.</span></span>
    
   <span data-ttu-id="0e4b7-146">f.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-146">f.</span></span> <span data-ttu-id="0e4b7-147">Fare clic sull'utente, su **Azione** e quindi su **Sblocca PIN**.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0e4b7-148">Blocco e sblocco dei PIN utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e4b7-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0e4b7-149">È possibile bloccare e sbloccare i pin degli utenti utilizzando Windows PowerShell e i cmdlet Lock-CsClientPin e Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="0e4b7-150">È possibile eseguire questi cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0e4b7-151">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="0e4b7-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="0e4b7-152">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="0e4b7-153">Per bloccare il PIN di un utente</span><span class="sxs-lookup"><span data-stu-id="0e4b7-153">To lock a user PIN</span></span>

- <span data-ttu-id="0e4b7-154">Per bloccare il PIN di un utente, utilizzare il cmdlet Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="0e4b7-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0e4b7-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="0e4b7-156">Per sbloccare il PIN di un utente</span><span class="sxs-lookup"><span data-stu-id="0e4b7-156">To unlock a user PIN</span></span>

- <span data-ttu-id="0e4b7-157">Per sbloccare il PIN di un utente, utilizzare il cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="0e4b7-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="0e4b7-158">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0e4b7-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="0e4b7-159">Per ulteriori informazioni, vedere l'argomento della Guida relativo ai cmdlet [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0e4b7-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
