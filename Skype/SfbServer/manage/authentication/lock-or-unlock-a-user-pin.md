---
title: Bloccare o sbloccare un PIN utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Riepilogo: bloccare o sbloccare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: bbf082fd85780972387cf014573e22996a9edcf0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992313"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="11324-103">Bloccare o sbloccare un PIN utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="11324-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="11324-104">**Riepilogo:** Bloccare o sbloccare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="11324-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="11324-105">È possibile bloccare o sbloccare il PIN di un utente dalla sezione **utenti** del pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="11324-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="11324-106">Per bloccare il PIN di un utente nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="11324-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="11324-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="11324-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="11324-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="11324-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="11324-109">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="11324-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="11324-110">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="11324-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="11324-111">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11324-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="11324-112">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11324-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="11324-113">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="11324-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="11324-114">un.</span><span class="sxs-lookup"><span data-stu-id="11324-114">a.</span></span> <span data-ttu-id="11324-115">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="11324-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="11324-116">b.</span><span class="sxs-lookup"><span data-stu-id="11324-116">b.</span></span> <span data-ttu-id="11324-117">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="11324-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="11324-118">c.</span><span class="sxs-lookup"><span data-stu-id="11324-118">c.</span></span> <span data-ttu-id="11324-119">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="11324-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="11324-120">3D.</span><span class="sxs-lookup"><span data-stu-id="11324-120">d.</span></span> <span data-ttu-id="11324-121">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="11324-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="11324-122">Per aggiungere altre clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="11324-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="11324-123">e.</span><span class="sxs-lookup"><span data-stu-id="11324-123">e.</span></span> <span data-ttu-id="11324-124">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11324-124">Click **Find**.</span></span>
    
   <span data-ttu-id="11324-125">f.</span><span class="sxs-lookup"><span data-stu-id="11324-125">f.</span></span> <span data-ttu-id="11324-126">Fare clic sull'utente, fare clic su **azione**e quindi su **blocca pin**.</span><span class="sxs-lookup"><span data-stu-id="11324-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="11324-127">Per sbloccare il PIN di un utente nel pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="11324-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="11324-128">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="11324-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="11324-129">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="11324-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="11324-130">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="11324-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="11324-131">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="11324-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="11324-132">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11324-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="11324-133">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11324-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="11324-134">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="11324-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="11324-135">un.</span><span class="sxs-lookup"><span data-stu-id="11324-135">a.</span></span> <span data-ttu-id="11324-136">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="11324-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="11324-137">b.</span><span class="sxs-lookup"><span data-stu-id="11324-137">b.</span></span> <span data-ttu-id="11324-138">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="11324-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="11324-139">c.</span><span class="sxs-lookup"><span data-stu-id="11324-139">c.</span></span> <span data-ttu-id="11324-140">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="11324-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="11324-141">3D.</span><span class="sxs-lookup"><span data-stu-id="11324-141">d.</span></span> <span data-ttu-id="11324-142">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="11324-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="11324-143">Per aggiungere altre clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="11324-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="11324-144">e.</span><span class="sxs-lookup"><span data-stu-id="11324-144">e.</span></span> <span data-ttu-id="11324-145">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11324-145">Click **Find**.</span></span>
    
   <span data-ttu-id="11324-146">f.</span><span class="sxs-lookup"><span data-stu-id="11324-146">f.</span></span> <span data-ttu-id="11324-147">Fare clic sull'utente, scegliere **azione**e quindi fare clic su **Sblocca PIN**.</span><span class="sxs-lookup"><span data-stu-id="11324-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="11324-148">Blocco e sblocco di PIN utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11324-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="11324-149">È possibile bloccare e sbloccare i pin degli utenti usando Windows PowerShell e i cmdlet Lock-CsClientPin e Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="11324-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="11324-150">Puoi eseguire questi cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11324-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="11324-151">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="11324-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="11324-152">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="11324-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="11324-153">Per bloccare un PIN utente</span><span class="sxs-lookup"><span data-stu-id="11324-153">To lock a user PIN</span></span>

- <span data-ttu-id="11324-154">Per bloccare il PIN di un utente, usare il cmdlet Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="11324-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="11324-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="11324-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="11324-156">Per sbloccare un PIN utente</span><span class="sxs-lookup"><span data-stu-id="11324-156">To unlock a user PIN</span></span>

- <span data-ttu-id="11324-157">Per sbloccare il PIN di un utente, usare il cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="11324-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="11324-158">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="11324-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="11324-159">Per altre informazioni, vedere l'argomento della Guida per i cmdlet [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="11324-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
