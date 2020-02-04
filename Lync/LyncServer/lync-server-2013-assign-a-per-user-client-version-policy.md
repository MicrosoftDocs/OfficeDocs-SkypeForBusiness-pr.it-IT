---
title: 'Lync Server 2013: assegnare un criterio di versione client per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e509427b6d2651f84b96a96c87fbe7cfd6177a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738376"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="11a55-102">Assegnare criteri di versione client per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11a55-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="11a55-103">Il criterio di versione client è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11a55-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="11a55-104">La distribuzione di uno o più criteri di versione client per utente è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="11a55-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="11a55-105">È anche possibile distribuire solo criteri di versione client a livello globale o criteri di versione del client a livello di sito o a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="11a55-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="11a55-106">Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="11a55-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="11a55-107">Quando non sono assegnati criteri specifici a livello di sito, a livello di pool o per utente, i client predefiniti consentiti per la registrazione con Lync Server 2013 sono quelli definiti nel criterio di versione client a livello globale.</span><span class="sxs-lookup"><span data-stu-id="11a55-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="11a55-108">Dopo aver creato almeno un criterio di versione client per utente, usare le procedure descritte in questo argomento per assegnare i criteri che specificano le versioni client che si desidera consentire la registrazione con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11a55-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="11a55-109">Per informazioni dettagliate sulla creazione di criteri di versione client per utente, vedere [specificare le applicazioni client che è possibile usare per accedere a Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="11a55-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="11a55-110">Per assegnare un criterio di versione client per utente</span><span class="sxs-lookup"><span data-stu-id="11a55-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="11a55-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="11a55-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11a55-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11a55-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11a55-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="11a55-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11a55-114">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="11a55-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="11a55-115">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="11a55-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="11a55-116">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11a55-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="11a55-117">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11a55-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="11a55-118">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="11a55-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="11a55-119">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="11a55-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="11a55-120">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="11a55-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="11a55-121">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="11a55-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="11a55-122">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="11a55-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="11a55-123">Per aggiungere altre clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="11a55-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="11a55-124">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="11a55-124">Click **Find**.</span></span>

6.  <span data-ttu-id="11a55-125">Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="11a55-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="11a55-126">Se si desidera che gli stessi criteri di versione client per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="11a55-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="11a55-127">In **Assegna criteri**, in **criteri di versione client**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="11a55-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="11a55-128">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come&gt; </STRONG> è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="11a55-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="11a55-129">Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="11a55-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="11a55-130">Consenti a Lync Server di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito o a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="11a55-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="11a55-131">Fare clic sul nome di un criterio di versione client per utente definito in precedenza nella pagina dei **criteri di versione client** .</span><span class="sxs-lookup"><span data-stu-id="11a55-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="11a55-132">Per decidere i criteri da assegnare, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.</span><span class="sxs-lookup"><span data-stu-id="11a55-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="11a55-133">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="11a55-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="11a55-134">Assegnazione di un criterio di versione client per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="11a55-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="11a55-135">Puoi assegnare criteri di versione client per utente usando il cmdlet Grant-CsClientVersionPolicy.</span><span class="sxs-lookup"><span data-stu-id="11a55-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="11a55-136">Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11a55-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="11a55-137">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="11a55-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="11a55-138">Per assegnare un criterio di versione client per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="11a55-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="11a55-139">Con il comando seguente viene assegnato il criterio di versione client per utente RedmondClientVersionPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="11a55-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="11a55-140">Per assegnare criteri di versione client per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="11a55-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="11a55-141">Questo comando assegna il criterio di versione client per utente RedmondClientVersionPolicy a tutti gli utenti a cui è attualmente assegnato il criterio vocale RedmondVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="11a55-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="11a55-142">Per altre informazioni sul parametro Filter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="11a55-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="11a55-143">Per annullare l'assegnazione di un criterio di versione client per utente</span><span class="sxs-lookup"><span data-stu-id="11a55-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="11a55-144">Il comando seguente annulla l'assegnazione di criteri di versione client per utente assegnati in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="11a55-144">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="11a55-145">Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale, i criteri del sito locale (se disponibile) o i criteri di ambito del servizio assegnati al suo registrar.</span><span class="sxs-lookup"><span data-stu-id="11a55-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="11a55-146">I criteri di ambito del servizio hanno la precedenza su qualsiasi criterio di sito e i criteri del sito hanno la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="11a55-146">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="11a55-147">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="11a55-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="11a55-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11a55-148">See Also</span></span>


[<span data-ttu-id="11a55-149">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11a55-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="11a55-150">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11a55-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

