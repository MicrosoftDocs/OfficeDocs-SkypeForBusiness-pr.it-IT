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
ms.openlocfilehash: 9523794808ca3b689cf1f3213c1f4ad657c83c25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030119"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="612a6-102">Assegnare un criterio PIN per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="612a6-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="612a6-103">Il criterio PIN (Personal Identification Number) per le conferenze telefoniche con accesso esterno è una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="612a6-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="612a6-104">La distribuzione di uno o più criteri PIN per utente è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="612a6-104">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="612a6-105">È inoltre possibile distribuire solo un criterio PIN a livello globale o criteri PIN a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="612a6-105">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="612a6-106">Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito agli utenti, ai gruppi o agli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="612a6-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="612a6-107">I diritti utente e le autorizzazioni per l'utilizzo dei pin per le conferenze telefoniche con accesso esterno vengono automaticamente predefiniti rispetto a quelli definiti nel criterio PIN a livello globale quando non vengono assegnati criteri specifici a livello di sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="612a6-107">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="612a6-108">Dopo aver creato almeno un criterio PIN per utente, utilizzare le procedure descritte in questo argomento per assegnare i criteri che specificano i vincoli che il server deve imporre sui pin creati e utilizzati da un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="612a6-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="612a6-109">Per informazioni dettagliate sulla creazione di criteri PIN per le conferenze telefoniche con accesso esterno per utente, vedere [creare o modificare le impostazioni del PIN per le conferenze telefoniche con accesso esterno in Lync Server 2013 per un sito o un gruppo di utenti](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="612a6-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="612a6-110">Per assegnare un criterio PIN per utente</span><span class="sxs-lookup"><span data-stu-id="612a6-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="612a6-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="612a6-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="612a6-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="612a6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="612a6-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="612a6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="612a6-114">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="612a6-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="612a6-115">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="612a6-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="612a6-116">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="612a6-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="612a6-117">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="612a6-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="612a6-118">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="612a6-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="612a6-119">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="612a6-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="612a6-120">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="612a6-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="612a6-121">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="612a6-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="612a6-122">A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="612a6-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="612a6-123">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="612a6-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="612a6-124">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="612a6-124">Click **Find**.</span></span>

6.  <span data-ttu-id="612a6-125">Fare clic su un utente all'interno dei risultati della ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="612a6-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="612a6-126">Se si desidera applicare lo stesso criterio PIN per utente a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="612a6-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="612a6-127">In **Assegna criteri**, in **criteri PIN**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="612a6-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="612a6-128">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="612a6-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="612a6-129">Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="612a6-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="612a6-130">Consenti a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="612a6-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="612a6-131">Fare clic sul nome di un criterio PIN per utente definito in precedenza nella pagina **criteri PIN** .</span><span class="sxs-lookup"><span data-stu-id="612a6-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="612a6-132">Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definite nei criteri.</span><span class="sxs-lookup"><span data-stu-id="612a6-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="612a6-133">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="612a6-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="612a6-134">Assegnazione di un criterio PIN per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="612a6-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="612a6-135">È possibile assegnare criteri PIN per utente tramite Windows PowerShell e il cmdlet **Grant-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="612a6-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="612a6-136">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="612a6-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="612a6-137">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="612a6-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="612a6-138">Per assegnare criteri PIN per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="612a6-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="612a6-139">Il comando seguente assegna il criterio PIN per utente RedmondPinPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="612a6-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="612a6-140">Per assegnare criteri PIN per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="612a6-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="612a6-141">Il comando seguente assegna il criterio PIN per utente RedmondUsersPinPolicy a tutti gli utenti che lavorano nella città di Redmond.</span><span class="sxs-lookup"><span data-stu-id="612a6-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="612a6-142">Per informazioni dettagliate sul parametro LdapFilter utilizzato in questo comando, vedere [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="612a6-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="612a6-143">Per annullare l'assegnazione di un criterio PIN per utente</span><span class="sxs-lookup"><span data-stu-id="612a6-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="612a6-144">Il comando seguente annulla l'assegnazione di un criterio PIN per utente precedentemente assegnato a Ken remario.</span><span class="sxs-lookup"><span data-stu-id="612a6-144">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="612a6-145">Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="612a6-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="612a6-146">I criteri del sito hanno la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="612a6-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="612a6-147">Per informazioni dettagliate, vedere [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="612a6-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="612a6-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="612a6-148">See Also</span></span>


[<span data-ttu-id="612a6-149">Creare un nuovo criterio PIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="612a6-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="612a6-150">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="612a6-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

