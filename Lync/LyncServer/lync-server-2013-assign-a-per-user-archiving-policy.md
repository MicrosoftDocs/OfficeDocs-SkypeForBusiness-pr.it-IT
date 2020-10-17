---
title: 'Lync Server 2013: assegnare un criterio di archiviazione per utente'
description: 'Lync Server 2013: assegnare un criterio di archiviazione per utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559992"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="3d4b5-103">Assegnare criteri di archiviazione per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d4b5-103">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="3d4b5-104">I criteri di archiviazione sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-104">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="3d4b5-p101">La distribuzione di uno o più criteri di archiviazione per utente è facoltativa. È inoltre possibile distribuire criteri di archiviazione solo a livello globale o a livello di sito. Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto. Se non sono assegnati criteri a livello di sito o per utente specifici, come requisiti di archiviazione predefiniti vengono impostati automaticamente quelli definiti nei criteri di conferenza a livello globale.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-p101">Deploying one or more per-user archiving policies is optional. You can also deploy only a global-level archiving policy or site-level archiving policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="3d4b5-109">Dopo la creazione di almeno un criterio di archiviazione per utente, utilizzare le procedure descritte in questo argomento per assegnare i criteri in modo da stabilire per ogni utente se il server deve archiviare le comunicazioni interne, le comunicazioni esterne o le comunicazioni di entrambi i tipi.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-109">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="3d4b5-110">Per informazioni dettagliate sulla creazione di criteri di archiviazione per utente, vedere [creazione di un criterio di archiviazione in Lync Server 2013 per abilitare o disabilitare l'archiviazione delle comunicazioni interne o esterne per siti o utenti specifici](lync-server-2013-create-archiving-policy-sites-users.md).</span><span class="sxs-lookup"><span data-stu-id="3d4b5-110">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="3d4b5-111">Per assegnare criteri di archiviazione per utente</span><span class="sxs-lookup"><span data-stu-id="3d4b5-111">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="3d4b5-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3d4b5-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3d4b5-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3d4b5-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3d4b5-115">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3d4b5-116">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="3d4b5-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="3d4b5-117">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="3d4b5-118">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="3d4b5-119">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="3d4b5-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3d4b5-120">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3d4b5-121">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="3d4b5-122">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="3d4b5-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="3d4b5-123">A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="3d4b5-124">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="3d4b5-125">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-125">Click **Find**.</span></span>

6.  <span data-ttu-id="3d4b5-126">Fare clic su un utente all'interno dei risultati della ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="3d4b5-127">Se si desidera applicare gli stessi criteri di archiviazione a più utenti, selezionare più utenti all'interno dei risultati di ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-127">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="3d4b5-128">In **Assegna criteri**, in **Criteri di archiviazione**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d4b5-128">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="3d4b5-129">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt; Mantieni come è &gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="3d4b5-130">Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="3d4b5-131">Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="3d4b5-132">Fare clic sul nome di criteri di archiviazione per utente precedentemente definiti nella pagina **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-132">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="3d4b5-133">Per agevolare la scelta dei criteri da assegnare, fare clic su un nome di criteri e quindi fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nei criteri.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="3d4b5-134">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3d4b5-135">Assegnazione di un criterio di archiviazione Per-User tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d4b5-135">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3d4b5-136">È possibile assegnare criteri di archiviazione per utente tramite Windows PowerShell e il cmdlet **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="3d4b5-136">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="3d4b5-137">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3d4b5-138">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="3d4b5-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="3d4b5-139">Per assegnare criteri di archiviazione per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="3d4b5-139">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="3d4b5-140">Il comando seguente assegna il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="3d4b5-140">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="3d4b5-141">Per assegnare criteri di archiviazione per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="3d4b5-141">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="3d4b5-142">Questo comando assegna il criterio di archiviazione per utente RedmondArchivingPolicy a tutti gli utenti i cui account si trovano nel pool di registrazione atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-142">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="3d4b5-143">Per ulteriori informazioni sul parametro Filter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="3d4b5-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="3d4b5-144">Per annullare l'assegnazione di un criterio di archiviazione per utente</span><span class="sxs-lookup"><span data-stu-id="3d4b5-144">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="3d4b5-p106">Il comando seguente annulla l'assegnazione di qualsiasi criterio di archiviazione per utente precedentemente assegnato a Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti. I criteri del sito hanno la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="3d4b5-p106">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="3d4b5-148">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="3d4b5-148">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d4b5-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d4b5-149">See Also</span></span>


[<span data-ttu-id="3d4b5-150">Creazione di un criterio di archiviazione in Lync Server 2013 per abilitare o disabilitare l'archiviazione delle comunicazioni interne o esterne per siti o utenti specifici</span><span class="sxs-lookup"><span data-stu-id="3d4b5-150">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="3d4b5-151">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d4b5-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

