---
title: 'Lync Server 2013: assegnare un criterio percorso per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec78fd434706ec3e1c5f28c256b38a5f4463ac7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044028"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="bce9e-102">Assegnare un criterio percorso per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bce9e-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="bce9e-103">Il criterio percorso è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bce9e-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="bce9e-p101">La distribuzione di uno o più criteri percorso per utente è facoltativa. È inoltre possibile distribuire un solo criterio percorso a livello globale o a livello di subnet. Se si distribuiscono criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto. Se non sono assegnati criteri specifici a livello di subnet o per utente, per impostazione predefinita in Enhanced 9-1-1 (E9-1-1) vengono utilizzate automaticamente le impostazioni definite nel criterio a livello globale.</span><span class="sxs-lookup"><span data-stu-id="bce9e-p101">Deploying one or more per-user location policies is optional. You can also deploy only a global-level location policy or subnet-level location policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="bce9e-108">Dopo aver creato almeno un criterio percorso per utente, utilizzare le procedure descritte in questo argomento per assegnare il criterio che specifica le impostazioni che devono essere applicate dal server per le chiamate di emergenza effettuate da un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="bce9e-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="bce9e-109">Per un elenco di tutte le impostazioni dei criteri di percorso disponibili, vedere [define the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="bce9e-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="bce9e-110">Per informazioni dettagliate sulla creazione dei criteri percorso, vedere [create location Policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bce9e-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="bce9e-111">Per assegnare un criterio percorso per utente con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="bce9e-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bce9e-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="bce9e-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bce9e-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bce9e-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bce9e-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bce9e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bce9e-115">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="bce9e-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="bce9e-116">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="bce9e-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="bce9e-117">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="bce9e-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="bce9e-118">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="bce9e-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="bce9e-119">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="bce9e-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="bce9e-120">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="bce9e-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="bce9e-121">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="bce9e-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="bce9e-122">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="bce9e-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="bce9e-123">A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bce9e-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="bce9e-124">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bce9e-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="bce9e-125">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="bce9e-125">Click **Find**.</span></span>

6.  <span data-ttu-id="bce9e-126">Fare clic su un utente nei risultati della ricerca, su **Azione** e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="bce9e-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="bce9e-127">Se si desidera applicare lo stesso criterio percorso per utente a più utenti, selezionare più utenti nei risultati della ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bce9e-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="bce9e-128">In **Criteri percorso** in **Assegna criteri** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bce9e-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="bce9e-129">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="bce9e-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="bce9e-130">Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="bce9e-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="bce9e-131">Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di subnet.</span><span class="sxs-lookup"><span data-stu-id="bce9e-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="bce9e-132">Fare clic sul nome di un criterio percorso per utente precedentemente definito eseguendo il cmdlet **New-CsLocationPolicy**.</span><span class="sxs-lookup"><span data-stu-id="bce9e-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="bce9e-133">Per agevolare la scelta dei criteri da assegnare, fare clic su un nome di criteri e quindi fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nei criteri.</span><span class="sxs-lookup"><span data-stu-id="bce9e-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="bce9e-134">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bce9e-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="bce9e-135">Assegnazione di un criterio percorso per utente tramite i cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="bce9e-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="bce9e-136">È possibile assegnare criteri percorso per utente utilizzando il cmdlet Grant-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="bce9e-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="bce9e-137">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bce9e-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bce9e-138">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="bce9e-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="bce9e-139">Per assegnare un criterio percorso per utente a un utente singolo</span><span class="sxs-lookup"><span data-stu-id="bce9e-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="bce9e-140">Il comando seguente consente di assegnare i criteri percorso per utente denominati RedmondLocationPolicy all'utente Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="bce9e-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="bce9e-141">Per assegnare un criterio percorso per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="bce9e-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="bce9e-142">Questo comando assegna il criterio percorso per utente AccountingDepartmentLocationPolicy a tutti gli utenti che lavorano per il reparto Contabilità.</span><span class="sxs-lookup"><span data-stu-id="bce9e-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="bce9e-143">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="bce9e-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="bce9e-144">Per annullare l'assegnazione di un criterio percorso per utente</span><span class="sxs-lookup"><span data-stu-id="bce9e-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="bce9e-p106">Il comando seguente annulla l'assegnazione dei criteri percorso per utente precedentemente assegnati all'utente Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente tramite i criteri globali oppure i criteri di sito locale, se esistenti. I criteri di sito sono prioritari rispetto ai criteri globali.</span><span class="sxs-lookup"><span data-stu-id="bce9e-p106">The following command unassigns any per-user location policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="bce9e-148">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="bce9e-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

