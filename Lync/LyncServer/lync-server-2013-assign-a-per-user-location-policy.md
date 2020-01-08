---
title: 'Lync Server 2013: assegnare un criterio di posizione per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a387d0f603addea31bd1e3ee6b591e06a26b2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976583"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="88009-102">Assegnare criteri di posizione per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88009-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="88009-103">Il criterio di posizione è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88009-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="88009-104">La distribuzione di uno o più criteri di posizione per utente è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="88009-104">Deploying one or more per-user location policies is optional.</span></span> <span data-ttu-id="88009-105">È anche possibile distribuire solo un criterio di posizione a livello globale o un criterio di posizione a livello di subnet.</span><span class="sxs-lookup"><span data-stu-id="88009-105">You can also deploy only a global-level location policy or subnet-level location policy.</span></span> <span data-ttu-id="88009-106">Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="88009-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="88009-107">Le impostazioni avanzate di 9-1-1 (E9-1-1) vengono predefinite automaticamente a quelle definite nel criterio di posizione a livello globale quando non viene assegnato alcun criterio specifico a livello di subnet o per utente.</span><span class="sxs-lookup"><span data-stu-id="88009-107">Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="88009-108">Dopo aver creato almeno un criterio di posizione per utente, usare le procedure descritte in questo argomento per assegnare i criteri che specificano le impostazioni che il server deve applicare per le chiamate di emergenza poste da un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="88009-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="88009-109">Per un elenco di tutte le impostazioni dei criteri di posizione disponibili, vedere [definizione dei criteri di posizione per Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="88009-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="88009-110">Per informazioni dettagliate sulla creazione di criteri di posizione, vedere [creare criteri di posizione in Lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="88009-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="88009-111">Per assegnare un criterio di posizione per utente con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="88009-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="88009-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="88009-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="88009-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88009-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88009-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="88009-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="88009-115">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="88009-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="88009-116">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="88009-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="88009-117">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="88009-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="88009-118">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="88009-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="88009-119">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="88009-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="88009-120">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="88009-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="88009-121">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="88009-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="88009-122">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="88009-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="88009-123">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="88009-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="88009-124">Per aggiungere altre clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="88009-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="88009-125">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="88009-125">Click **Find**.</span></span>

6.  <span data-ttu-id="88009-126">Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="88009-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="88009-127">Se si desidera che gli stessi criteri di posizione per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="88009-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="88009-128">In **Assegna criteri**, in **criteri di posizione**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="88009-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="88009-129">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come&gt; </STRONG> è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="88009-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="88009-130">Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="88009-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="88009-131">Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di subnet.</span><span class="sxs-lookup"><span data-stu-id="88009-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="88009-132">Fare clic sul nome dei criteri di posizione per utente definiti in precedenza eseguendo il cmdlet **New-CsLocationPolicy** .</span><span class="sxs-lookup"><span data-stu-id="88009-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="88009-133">Per decidere i criteri da assegnare, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.</span><span class="sxs-lookup"><span data-stu-id="88009-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="88009-134">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88009-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="88009-135">Assegnazione di un criterio di posizione per utente tramite i cmdlet di Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="88009-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="88009-136">È possibile assegnare criteri di posizione per utente usando il cmdlet Grant-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="88009-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="88009-137">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88009-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="88009-138">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="88009-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="88009-139">Per assegnare un criterio di posizione per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="88009-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="88009-140">Con il comando seguente viene assegnato il criterio di posizione per utente RedmondLocationPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="88009-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="88009-141">Per assegnare un criterio di posizione per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="88009-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="88009-142">Questo comando assegna il criterio di posizione per utente AccountingDepartmentLocationPolicy a tutti gli utenti che lavorano per il reparto contabilità.</span><span class="sxs-lookup"><span data-stu-id="88009-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="88009-143">Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="88009-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="88009-144">Per annullare l'assegnazione di un criterio di posizione per utente</span><span class="sxs-lookup"><span data-stu-id="88009-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="88009-145">Il comando seguente annulla l'assegnazione di criteri di posizione per utente assegnati in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="88009-145">The following command unassigns any per-user location policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="88009-146">Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale.</span><span class="sxs-lookup"><span data-stu-id="88009-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="88009-147">Un criterio di sito ha la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="88009-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="88009-148">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="88009-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

