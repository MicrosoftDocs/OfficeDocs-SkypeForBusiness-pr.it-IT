---
title: 'Lync Server 2013: assegnazione di un criterio di conferenza per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4fbef02553d4ba390dcf94f96f55936e2661b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043318"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="d6407-102">Assegnazione di un criterio di conferenza per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6407-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="d6407-103">I criteri di conferenza sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6407-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="d6407-p101">La distribuzione di uno o più criteri di conferenza per utente è facoltativa. È inoltre possibile distribuire solo criteri di conferenza a livello globale o a livello di sito. Se si distribuiscono criteri per utente, è necessario assegnarli in modo esplicito a utenti, gruppi o oggetti contatto. Le autorizzazioni e i diritti utente per le conferenze vengono impostati automaticamente su quelli definiti nei criteri di conferenza a livello globale quando non sono assegnati criteri a livello di sito o per utente specifici.</span><span class="sxs-lookup"><span data-stu-id="d6407-p101">Deploying one or more per-user conferencing policies is optional. You can also deploy only a global-level conferencing policy or site-level conferencing policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects. Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="d6407-108">Dopo aver creato criteri di conferenza per utente, utilizzare le procedure incluse in questo argomento per assegnare i criteri che specificano le autorizzazioni e i diritti utente che si desidera vengano concessi dal server alle riunioni organizzate da un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="d6407-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="d6407-109">Per un elenco di tutte le impostazioni disponibili per i criteri di conferenza, vedere informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d6407-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="d6407-110">Per informazioni dettagliate sulla creazione di criteri di conferenza, vedere [Create or modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d6407-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="d6407-111">Per assegnare criteri di conferenza per utente</span><span class="sxs-lookup"><span data-stu-id="d6407-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="d6407-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d6407-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d6407-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6407-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d6407-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d6407-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d6407-115">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="d6407-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d6407-116">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="d6407-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="d6407-117">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="d6407-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="d6407-118">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="d6407-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="d6407-119">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="d6407-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="d6407-120">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="d6407-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="d6407-121">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="d6407-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="d6407-122">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="d6407-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="d6407-123">A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d6407-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="d6407-124">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d6407-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="d6407-125">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="d6407-125">Click **Find**.</span></span>

6.  <span data-ttu-id="d6407-126">Fare clic su un utente nei risultati della ricerca, fare clic su **Azione** e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="d6407-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="d6407-127">Se si desidera applicare gli stessi criteri di conferenza per utente a più utenti, selezionare i diversi utenti nei risultati della ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d6407-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="d6407-128">In **Criteri conferenza** in **Assegna criteri** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6407-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="d6407-129">Poiché esistono più criteri che è possibile configurare in <STRONG>Assegna criteri</STRONG>, <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d6407-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="d6407-130">Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="d6407-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="d6407-131">Selezionare \*\* \<automatico\> \*\* per consentire a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="d6407-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="d6407-132">Fare clic sui nomi dei criteri di conferenza per utente definiti in precedenza nella pagina **Criteri conferenza**.</span><span class="sxs-lookup"><span data-stu-id="d6407-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="d6407-133">Per stabilire i criteri che si desidera assegnare, dopo avere fatto clic sui nomi dei criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare le autorizzazioni e i diritti utente definiti nei criteri.</span><span class="sxs-lookup"><span data-stu-id="d6407-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="d6407-134">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6407-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d6407-135">Assegnazione di un criterio di conferenza per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6407-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d6407-136">I criteri di conferenza per utente possono essere assegnati utilizzando Windows PowerShell e il cmdlet Grant-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="d6407-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="d6407-137">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6407-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d6407-138">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="d6407-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="d6407-139">Per assegnare criteri di conferenza per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="d6407-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="d6407-140">Il comando seguente assegna il criterio di conferenza per utente RedmondConferencingPolicy all'utente Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d6407-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="d6407-141">Per assegnare criteri di conferenza per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="d6407-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="d6407-142">Questo comando assegna il criterio di conferenza per utente HRConferencingPolicy a tutti gli utenti che lavorano nel dipartimento delle Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="d6407-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="d6407-143">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="d6407-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="d6407-144">Per annullare l'assegnazione di un criterio di conferenza per utente</span><span class="sxs-lookup"><span data-stu-id="d6407-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="d6407-p106">Il comando seguente annulla l'assegnazione di tutti i criteri di conferenza per utente precedentemente assegnati a Ken Myer. Dopo l'annullamento del criterio per utente, Ken Myer sarà gestito automaticamente dal criterio globale oppure dall'eventuale criterio del sito locale, che ha la precedenza sul criterio globale.</span><span class="sxs-lookup"><span data-stu-id="d6407-p106">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="d6407-148">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="d6407-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6407-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6407-149">See Also</span></span>


[<span data-ttu-id="d6407-150">Creare o modificare criteri di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6407-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="d6407-151">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6407-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

