---
title: Assegnare un criterio PIN per utente in Skype for Business Server
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
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Sintesi: Stage AV e OAuth Certificates per Skype for Business Server.'
ms.openlocfilehash: 6a0d0a1824e809a70dfee419fb5da1f663d8d779
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828526"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="e428b-103">Assegnare un criterio PIN per utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e428b-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="e428b-104">**Riepilogo:** In stage AV e OAuth Certificates per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e428b-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="e428b-105">Il criterio PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e428b-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="e428b-106">La distribuzione di uno o più criteri PIN per utente è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e428b-106">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="e428b-107">È inoltre possibile distribuire solo un criterio PIN a livello globale o criteri PIN a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="e428b-107">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="e428b-108">Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="e428b-108">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="e428b-109">I diritti utente e le autorizzazioni per l'utilizzo dei pin per le conferenze telefoniche con accesso esterno vengono automaticamente predefiniti rispetto a quelli definiti nel criterio PIN a livello globale quando non vengono assegnati criteri specifici a livello di sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="e428b-109">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="e428b-110">Dopo aver creato almeno un criterio PIN per utente, utilizzare le procedure descritte in questo argomento per assegnare i criteri che specificano i vincoli che il server deve imporre sui pin creati e utilizzati da un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="e428b-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="e428b-111">Per assegnare un criterio PIN per utente</span><span class="sxs-lookup"><span data-stu-id="e428b-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="e428b-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e428b-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e428b-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e428b-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e428b-114">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="e428b-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="e428b-115">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="e428b-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="e428b-116">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="e428b-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="e428b-117">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="e428b-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="e428b-118">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="e428b-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="e428b-119">a.</span><span class="sxs-lookup"><span data-stu-id="e428b-119">a.</span></span> <span data-ttu-id="e428b-120">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="e428b-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="e428b-121">b.</span><span class="sxs-lookup"><span data-stu-id="e428b-121">b.</span></span> <span data-ttu-id="e428b-122">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="e428b-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="e428b-123">c.</span><span class="sxs-lookup"><span data-stu-id="e428b-123">c.</span></span> <span data-ttu-id="e428b-124">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="e428b-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="e428b-125">d.</span><span class="sxs-lookup"><span data-stu-id="e428b-125">d.</span></span> <span data-ttu-id="e428b-126">A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e428b-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e428b-127">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="e428b-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="e428b-128">e.</span><span class="sxs-lookup"><span data-stu-id="e428b-128">e.</span></span> <span data-ttu-id="e428b-129">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="e428b-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="e428b-130">Fare clic su un utente all'interno dei risultati della ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="e428b-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e428b-131">Se si desidera applicare lo stesso criterio PIN per utente a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su **azioni** e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="e428b-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="e428b-132">In **Assegna criteri**, in **criteri PIN**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e428b-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e428b-133">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo **Assegna criteri** , **\<Keep as is\>** è selezionata per impostazione predefinita per tutti i criteri nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="e428b-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="e428b-134">Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="e428b-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="e428b-135">Consenti a Skype for Business Server di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="e428b-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="e428b-136">Fare clic sul nome di un criterio PIN per utente definito in precedenza nella pagina **criteri PIN** .</span><span class="sxs-lookup"><span data-stu-id="e428b-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="e428b-137">Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su **Visualizza** per visualizzare i diritti utente e le autorizzazioni definite nei criteri.</span><span class="sxs-lookup"><span data-stu-id="e428b-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="e428b-138">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e428b-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e428b-139">Assegnazione di un criterio PIN Per-User tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e428b-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e428b-140">È possibile assegnare criteri PIN per utente tramite Windows PowerShell e il cmdlet **Grant-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="e428b-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="e428b-141">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e428b-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e428b-142">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="e428b-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e428b-143">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e428b-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="e428b-144">Per assegnare criteri PIN per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="e428b-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="e428b-145">Il comando seguente assegna il criterio PIN per utente RedmondPinPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="e428b-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="e428b-146">Per assegnare criteri PIN per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="e428b-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="e428b-147">Il comando seguente assegna il criterio PIN per utente RedmondUsersPinPolicy a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="e428b-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="e428b-148">Per informazioni dettagliate sul parametro LdapFilter utilizzato in questo comando, vedere [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e428b-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="e428b-149">Per annullare l'assegnazione di un criterio PIN per utente</span><span class="sxs-lookup"><span data-stu-id="e428b-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="e428b-150">Il comando seguente annulla l'assegnazione di un criterio PIN per utente precedentemente assegnato a Ken remario.</span><span class="sxs-lookup"><span data-stu-id="e428b-150">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="e428b-151">Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="e428b-151">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="e428b-152">I criteri del sito hanno la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="e428b-152">A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="e428b-153">Per informazioni dettagliate, vedere [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e428b-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e428b-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e428b-154">See also</span></span>

[<span data-ttu-id="e428b-155">Creare un nuovo criterio PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e428b-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
