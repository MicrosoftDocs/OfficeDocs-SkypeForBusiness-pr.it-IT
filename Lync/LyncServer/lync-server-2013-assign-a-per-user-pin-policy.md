---
title: 'Lync Server 2013: assegnare un criterio PIN per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0864fdf4d2356ee04e1084c2f6b0149b2a6ebd5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722816"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="b6ab9-102">Assegnare un criterio PIN per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6ab9-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b6ab9-103">Il criterio PIN (Personal Identification Number) dei servizi di conferenza telefonica con accesso esterno è una delle singole impostazioni di un account utente che può essere configurato nel pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="b6ab9-104">La distribuzione di uno o più criteri PIN per utente è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-104">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="b6ab9-105">È anche possibile distribuire solo un criterio PIN a livello globale o un criterio PIN a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-105">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="b6ab9-106">Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="b6ab9-107">I diritti e le autorizzazioni degli utenti per l'uso dei pin per i servizi di conferenza telefonica con accesso esterno vengono automaticamente predefiniti per quelli definiti nel criterio PIN a livello globale quando non viene assegnato alcun criterio specifico a livello di sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-107">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="b6ab9-108">Dopo aver creato almeno un criterio PIN per utente, usare le procedure descritte in questo argomento per assegnare i criteri che specificano i vincoli che il server deve applicare ai pin creati e usati da un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="b6ab9-109">Per informazioni dettagliate sulla creazione di criteri PIN per i servizi di conferenza telefonica con accesso esterno per ogni utente, vedere [creare o modificare le impostazioni dei pin di conferenza telefonica con accesso esterno in Lync Server 2013 per un sito o un gruppo di utenti](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="b6ab9-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="b6ab9-110">Per assegnare un criterio PIN per utente</span><span class="sxs-lookup"><span data-stu-id="b6ab9-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="b6ab9-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b6ab9-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b6ab9-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b6ab9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b6ab9-114">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b6ab9-115">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="b6ab9-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b6ab9-116">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b6ab9-117">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b6ab9-118">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="b6ab9-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b6ab9-119">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b6ab9-120">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b6ab9-121">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b6ab9-122">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b6ab9-123">Per aggiungere altre clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="b6ab9-124">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-124">Click **Find**.</span></span>

6.  <span data-ttu-id="b6ab9-125">Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="b6ab9-126">Se si desidera che gli stessi criteri PIN per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="b6ab9-127">In **Assegna criteri**, in **criteri PIN**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6ab9-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b6ab9-128">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come&gt; </STRONG> è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="b6ab9-129">Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="b6ab9-130">Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="b6ab9-131">Fare clic sul nome di un criterio PIN per utente definito in precedenza nella pagina dei **criteri PIN** .</span><span class="sxs-lookup"><span data-stu-id="b6ab9-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b6ab9-132">Per decidere i criteri da assegnare, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="b6ab9-133">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b6ab9-134">Assegnazione di un criterio PIN per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6ab9-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b6ab9-135">È possibile assegnare criteri PIN per utente tramite Windows PowerShell e il cmdlet **Grant-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b6ab9-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="b6ab9-136">Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b6ab9-137">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="b6ab9-138">Per assegnare un criterio PIN per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="b6ab9-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="b6ab9-139">Con il comando seguente viene assegnato il criterio PIN per ogni utente RedmondPinPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="b6ab9-140">Per assegnare un criterio PIN per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="b6ab9-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="b6ab9-141">Con il comando seguente viene assegnato il criterio PIN per utente RedmondUsersPinPolicy a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="b6ab9-142">Per informazioni dettagliate sul parametro LdapFilter usato in questo comando, vedere [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="b6ab9-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="b6ab9-143">Per annullare l'assegnazione di un criterio PIN per utente</span><span class="sxs-lookup"><span data-stu-id="b6ab9-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="b6ab9-144">Il comando seguente annulla l'assegnazione di qualsiasi criterio PIN per utente assegnato in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-144">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b6ab9-145">Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="b6ab9-146">Un criterio di sito ha la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="b6ab9-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b6ab9-147">Per informazioni dettagliate, vedere [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="b6ab9-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6ab9-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6ab9-148">See Also</span></span>


[<span data-ttu-id="b6ab9-149">Creare un nuovo criterio PIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6ab9-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="b6ab9-150">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6ab9-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

