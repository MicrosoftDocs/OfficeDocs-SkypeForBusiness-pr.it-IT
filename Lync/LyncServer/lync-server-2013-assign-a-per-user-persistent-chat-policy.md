---
title: 'Lync Server 2013: assegnare un criterio per la chat persistente per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 616a171d4aedcc6014ddea3c5993a097d410a5e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722826"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="01561-102">Assegnare criteri per la chat persistente per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01561-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="01561-103">È possibile assegnare un criterio per la chat persistente per ogni utente con il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="01561-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="01561-104">Per informazioni dettagliate sulla creazione di criteri utente per il server di chat persistente, vedere [creare criteri utente per la chat persistente in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="01561-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="01561-105">Per assegnare un criterio per la chat persistente per utente con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="01561-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="01561-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="01561-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="01561-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01561-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="01561-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="01561-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="01561-109">Sulla barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="01561-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="01561-110">Usare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="01561-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="01561-111">Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="01561-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="01561-112">Se si ha una query salvata, fare clic sull'icona **Apri query** , usare la finestra di dialogo **Apri** per recuperare la query (un file con estensione USF) e quindi fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="01561-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="01561-113">Opzionale Specificare altri criteri di ricerca per restringere i risultati:</span><span class="sxs-lookup"><span data-stu-id="01561-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="01561-114">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="01561-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="01561-115">Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="01561-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="01561-116">Nell'elenco **a discesa uguale a** fare clic sull'operatore, ad esempio **uguale** a o diverso **da**.</span><span class="sxs-lookup"><span data-stu-id="01561-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="01561-117">A seconda della proprietà utente selezionata, immettere i criteri da usare per filtrare i risultati della ricerca digitando o facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="01561-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="01561-118">Per aggiungere altre clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="01561-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="01561-119">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="01561-119">Click **Find**.</span></span>

6.  <span data-ttu-id="01561-120">Fare clic su un utente nei risultati della ricerca, fare clic su **azione**e quindi su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="01561-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="01561-121">Se si vuole che gli stessi criteri per la chat persistente per utente vengano applicati a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="01561-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="01561-122">In **Assegna criteri**, in **criteri Chat persistente**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="01561-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="01561-123">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come&gt; </STRONG> è selezionato per impostazione predefinita per ogni criterio nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="01561-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="01561-124">Continuare a usare il criterio precedentemente assegnato all'utente senza apportare alcuna modifica a questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="01561-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="01561-125">Selezionare \*\* \<automatico\> \*\* per consentire a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="01561-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="01561-126">Fare clic sul nome di un criterio di chat persistente per utente definito in precedenza nella pagina dei **criteri di chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="01561-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="01561-127">Per decidere i criteri da assegnare, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definiti nel criterio dopo aver fatto clic su un nome di criterio.</span><span class="sxs-lookup"><span data-stu-id="01561-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="01561-128">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="01561-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="01561-129">Assegnazione di un criterio di chat persistente per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01561-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="01561-130">Puoi anche assegnare criteri per la chat persistente per utente usando il cmdlet **Grant-CsPersistentChatPolicy** .</span><span class="sxs-lookup"><span data-stu-id="01561-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="01561-131">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01561-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="01561-132">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="01561-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="01561-133">Per assegnare un criterio di chat persistente per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="01561-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="01561-134">Con il comando seguente viene assegnato il criterio di chat persistente per utente RedmondPersistentChatPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="01561-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="01561-135">Per assegnare criteri di chat permanenti per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="01561-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="01561-136">Questo comando assegna il criterio per la chat persistente per utente RedmondUsersPersistentChatPolicy a tutti gli utenti che lavorano per il reparto IT.</span><span class="sxs-lookup"><span data-stu-id="01561-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="01561-137">Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="01561-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="01561-138">Per annullare l'assegnazione di un criterio per la chat persistente per utente</span><span class="sxs-lookup"><span data-stu-id="01561-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="01561-139">Il comando seguente annulla l'assegnazione di qualsiasi criterio di chat persistente per utente assegnato in precedenza a Ken.</span><span class="sxs-lookup"><span data-stu-id="01561-139">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="01561-140">Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale.</span><span class="sxs-lookup"><span data-stu-id="01561-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="01561-141">Un criterio di sito ha la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="01561-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="01561-142">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="01561-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="01561-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01561-143">See Also</span></span>


[<span data-ttu-id="01561-144">Creare criteri utente per Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01561-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

