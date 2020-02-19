---
title: 'Lync Server 2013: assegnare un criterio di chat persistente per utente'
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
ms.openlocfilehash: e06d6c7403bd348b44c6ab36216ed7ee9a1c6d02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134412"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="b7876-102">Assegnazione di criteri di chat persistente per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7876-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b7876-103">È possibile assegnare criteri di chat persistente per utente con il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7876-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b7876-104">Per informazioni dettagliate sulla creazione di criteri utente per il server Chat persistente, vedere [creare un criterio utente per la chat persistente in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="b7876-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="b7876-105">Per assegnare criteri di chat persistente per utente con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b7876-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b7876-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b7876-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7876-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b7876-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b7876-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b7876-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b7876-109">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="b7876-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b7876-110">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="b7876-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b7876-111">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b7876-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b7876-112">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b7876-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b7876-113">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="b7876-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b7876-114">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="b7876-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b7876-115">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="b7876-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b7876-116">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="b7876-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b7876-117">A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b7876-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b7876-118">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b7876-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="b7876-119">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b7876-119">Click **Find**.</span></span>

6.  <span data-ttu-id="b7876-120">Fare clic su un utente nei risultati di ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="b7876-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="b7876-121">Se si desidera applicare gli stessi criteri di chat persistente a più utenti, selezionare più utenti all'interno dei risultati di ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b7876-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="b7876-122">In **Assegna criteri** eseguire una delle operazioni seguenti in **Criteri chat persistente**:</span><span class="sxs-lookup"><span data-stu-id="b7876-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b7876-123">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b7876-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="b7876-124">Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="b7876-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="b7876-125">Selezionare \*\* \<automatico\> \*\* per consentire a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="b7876-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="b7876-126">Fare clic sul nome dei criteri di chat persistente per utente precedentemente definiti nella pagina **Criteri chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="b7876-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b7876-127">Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definite nei criteri.</span><span class="sxs-lookup"><span data-stu-id="b7876-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="b7876-128">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7876-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b7876-129">Assegnazione di criteri di chat persistente per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7876-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b7876-130">È inoltre possibile assegnare criteri di chat persistente per utente utilizzando il cmdlet **Grant-CsPersistentChatPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b7876-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="b7876-131">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7876-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b7876-132">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="b7876-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="b7876-133">Per assegnare criteri di chat persistente per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="b7876-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="b7876-134">Il comando seguente consente di assegnare i criteri di chat persistente per utente denominati RedmondPersistentChatPolicy all'utente Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b7876-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="b7876-135">Per assegnare criteri di chat persistente per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="b7876-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="b7876-136">Questo comando consente di assegnare i criteri di chat persistente per utente RedmondUsersPersistentChatPolicy a tutti gli utenti che fanno parte del reparto IT.</span><span class="sxs-lookup"><span data-stu-id="b7876-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="b7876-137">Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="b7876-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="b7876-138">Per annullare l'assegnazione di un criterio di chat persistente per utente</span><span class="sxs-lookup"><span data-stu-id="b7876-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="b7876-p106">Il comando seguente consente di annullare l'assegnazione dei criteri di chat persistente per utente precedentemente assegnati all'utente Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente tramite i criteri globali oppure i criteri di sito locale, se esistenti. I criteri di sito sono prioritari rispetto ai criteri globali.</span><span class="sxs-lookup"><span data-stu-id="b7876-p106">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b7876-142">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="b7876-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7876-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7876-143">See Also</span></span>


[<span data-ttu-id="b7876-144">Creare un criterio utente per la chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7876-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

