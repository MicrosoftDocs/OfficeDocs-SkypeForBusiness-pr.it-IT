---
title: Assegnare un criterio PIN per utente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Riepilogo: certificati per la fase AV e OAuth per Skype for Business Server.'
ms.openlocfilehash: dafb70239552b9ee2c5e84e7624e881711e8ce6f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188204"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="6a98d-103">Assegnare un criterio PIN per utente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a98d-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="6a98d-104">**Riepilogo:** I certificati di fase AV e OAuth per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a98d-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="6a98d-105">Il criterio PIN (Personal Identification Number) dei servizi di conferenza telefonica con accesso esterno è una delle singole impostazioni di un account utente che può essere configurato nel pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a98d-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="6a98d-106">La distribuzione di uno o più criteri PIN per utente è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="6a98d-106">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="6a98d-107">È anche possibile distribuire solo un criterio PIN a livello globale o un criterio PIN a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="6a98d-107">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="6a98d-108">Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="6a98d-108">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="6a98d-109">I diritti e le autorizzazioni degli utenti per l'uso dei pin per i servizi di conferenza telefonica con accesso esterno vengono automaticamente predefiniti per quelli definiti nel criterio PIN a livello globale quando non viene assegnato alcun criterio specifico a livello di sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="6a98d-109">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="6a98d-110">Dopo aver creato almeno un criterio PIN per utente, usare le procedure descritte in questo argomento per assegnare i criteri che specificano i vincoli che il server deve applicare ai pin creati e usati da un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="6a98d-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="6a98d-111">Per assegnare un criterio PIN per utente</span><span class="sxs-lookup"><span data-stu-id="6a98d-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="6a98d-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="6a98d-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6a98d-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a98d-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6a98d-114">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="6a98d-115">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="6a98d-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="6a98d-116">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="6a98d-117">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="6a98d-118">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="6a98d-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="6a98d-119">un.</span><span class="sxs-lookup"><span data-stu-id="6a98d-119">a.</span></span> <span data-ttu-id="6a98d-120">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="6a98d-121">b.</span><span class="sxs-lookup"><span data-stu-id="6a98d-121">b.</span></span> <span data-ttu-id="6a98d-122">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="6a98d-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="6a98d-123">c.</span><span class="sxs-lookup"><span data-stu-id="6a98d-123">c.</span></span> <span data-ttu-id="6a98d-124">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="6a98d-125">3D.</span><span class="sxs-lookup"><span data-stu-id="6a98d-125">d.</span></span> <span data-ttu-id="6a98d-126">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6a98d-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6a98d-127">Per aggiungere altre clausole di ricerca alla query, fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="6a98d-128">e.</span><span class="sxs-lookup"><span data-stu-id="6a98d-128">e.</span></span> <span data-ttu-id="6a98d-129">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="6a98d-130">Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6a98d-131">Se si desidera che gli stessi criteri PIN per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su **azioni**e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="6a98d-132">In **Assegna criteri**, in **criteri PIN**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a98d-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6a98d-133">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo **Assegna criteri** , \*\* \<Mantieni come\> \*\* è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6a98d-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="6a98d-134">Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="6a98d-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="6a98d-135">Consenti a Skype for Business Server di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="6a98d-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="6a98d-136">Fare clic sul nome di un criterio PIN per utente definito in precedenza nella pagina dei **criteri PIN** .</span><span class="sxs-lookup"><span data-stu-id="6a98d-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="6a98d-137">Per decidere i criteri da assegnare, fare clic su **Visualizza** per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.</span><span class="sxs-lookup"><span data-stu-id="6a98d-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="6a98d-138">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a98d-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6a98d-139">Assegnazione di un criterio PIN per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a98d-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6a98d-140">È possibile assegnare criteri PIN per utente tramite Windows PowerShell e il cmdlet **Grant-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="6a98d-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="6a98d-141">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a98d-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6a98d-142">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="6a98d-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6a98d-143">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a98d-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="6a98d-144">Per assegnare un criterio PIN per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="6a98d-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="6a98d-145">Con il comando seguente viene assegnato il criterio PIN per ogni utente RedmondPinPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="6a98d-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="6a98d-146">Per assegnare un criterio PIN per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="6a98d-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="6a98d-147">Con il comando seguente viene assegnato il criterio PIN per utente RedmondUsersPinPolicy a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="6a98d-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="6a98d-148">Per informazioni dettagliate sul parametro LdapFilter usato in questo comando, vedere [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6a98d-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="6a98d-149">Per annullare l'assegnazione di un criterio PIN per utente</span><span class="sxs-lookup"><span data-stu-id="6a98d-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="6a98d-150">Il comando seguente annulla l'assegnazione di qualsiasi criterio PIN per utente assegnato in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="6a98d-150">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="6a98d-151">Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale.</span><span class="sxs-lookup"><span data-stu-id="6a98d-151">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="6a98d-152">Un criterio di sito ha la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="6a98d-152">A site policy takes precedence over the global policy.</span></span>
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="6a98d-153">Per informazioni dettagliate, vedere [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6a98d-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a98d-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a98d-154">See also</span></span>

[<span data-ttu-id="6a98d-155">Creare un nuovo criterio PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a98d-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
