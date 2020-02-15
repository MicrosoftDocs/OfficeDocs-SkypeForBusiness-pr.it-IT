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
ms.openlocfilehash: 3668e21836fd3ecee0740493c8b9bd631227583a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029267"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="854d3-102">Assegnare criteri di versione client per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854d3-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="854d3-103">I criteri di versione client sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="854d3-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="854d3-104">La distribuzione di uno o più criteri di versione client per utente è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="854d3-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="854d3-105">È anche possibile distribuire solo un criterio di versione client a livello globale oppure criteri di versione client a livello di sito o di pool.</span><span class="sxs-lookup"><span data-stu-id="854d3-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="854d3-106">Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito a utenti, gruppi o oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="854d3-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="854d3-107">Quando non vengono assegnati criteri specifici a livello di sito, a livello di pool o per utente, i client predefiniti che sono autorizzati a eseguire la registrazione con Lync Server 2013 sono quelli definiti nei criteri di versione client a livello globale.</span><span class="sxs-lookup"><span data-stu-id="854d3-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="854d3-108">Dopo aver creato almeno un criterio di versione client per utente, utilizzare le procedure descritte in questo argomento per assegnare i criteri che specificano le versioni client che si desidera consentire di eseguire la registrazione con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="854d3-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="854d3-109">Per informazioni dettagliate sulla creazione di criteri di versione client per utente, vedere [specificare le applicazioni client che possono essere utilizzate per accedere a Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="854d3-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="854d3-110">Per assegnare criteri di versione client per utente</span><span class="sxs-lookup"><span data-stu-id="854d3-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="854d3-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="854d3-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="854d3-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="854d3-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="854d3-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="854d3-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="854d3-114">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="854d3-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="854d3-115">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="854d3-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="854d3-116">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="854d3-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="854d3-117">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="854d3-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="854d3-118">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="854d3-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="854d3-119">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="854d3-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="854d3-120">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="854d3-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="854d3-121">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="854d3-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="854d3-122">A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="854d3-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="854d3-123">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="854d3-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="854d3-124">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="854d3-124">Click **Find**.</span></span>

6.  <span data-ttu-id="854d3-125">Fare clic su un utente nei risultati di ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="854d3-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="854d3-126">Se si desidera applicare a più utenti gli stessi criteri di versione client per utente, selezionare più utenti nei risultati di ricerca, fare clic su <STRONG>Azioni</STRONG> e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="854d3-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="854d3-127">In **Assegna criteri**, in **Criteri versione client** effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="854d3-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="854d3-128">Poiché esistono più criteri che è possibile configurare tramite la finestra di dialogo <STRONG>Assegna criteri</STRONG> , <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="854d3-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="854d3-129">Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="854d3-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="854d3-130">Consentire a Lync Server di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito o a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="854d3-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="854d3-131">Fare clic sul nome dei criteri di versione client per utente precedentemente definiti nella pagina **Criteri versione client**.</span><span class="sxs-lookup"><span data-stu-id="854d3-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="854d3-132">Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definite nei criteri.</span><span class="sxs-lookup"><span data-stu-id="854d3-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="854d3-133">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="854d3-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="854d3-134">Assegnazione di un criterio di versione client per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="854d3-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="854d3-135">È possibile assegnare un criterio di versione client per utente utilizzando il cmdlet Grant-CsClientVersionPolicy.</span><span class="sxs-lookup"><span data-stu-id="854d3-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="854d3-136">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="854d3-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="854d3-137">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="854d3-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="854d3-138">Per assegnare un criterio di versione client per utente a un unico utente</span><span class="sxs-lookup"><span data-stu-id="854d3-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="854d3-139">Il comando seguente assegna il criterio di versione client per utente RedmondClientVersionPolicy all'utente Davide Garghentini.</span><span class="sxs-lookup"><span data-stu-id="854d3-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="854d3-140">Per assegnare un criterio di versione client per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="854d3-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="854d3-141">Il comando assegna il criterio di versione client per utente RedmondClientVersionPolicy a tutti gli utenti a cui è attualmente assegnato il criterio vocale RedmondVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="854d3-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="854d3-142">Per ulteriori informazioni sul parametro Filter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="854d3-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="854d3-143">Per annullare l'assegnazione dei criteri di versione client per utente</span><span class="sxs-lookup"><span data-stu-id="854d3-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="854d3-p106">Il comando seguente annulla l'assegnazione del criterio di versione client per utente precedentemente assegnato a Davide Garghentini. Dopo che l'assegnazione del criterio per utente è stata annullata, Davide Garghentini verrà gestito automaticamente utilizzando il criterio globale, il relativo criterio sito globale (se esistente) o il criterio dell'ambito del servizio assegnato alla relativa Registrazione avanzata. Un criterio ambito del servizio ha la precedenza rispetto a un criterio sito e un criterio sito ha la precedenza rispetto al criterio globale.</span><span class="sxs-lookup"><span data-stu-id="854d3-p106">The following command unassigns any per-user client version policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar. A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="854d3-147">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="854d3-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="854d3-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="854d3-148">See Also</span></span>


[<span data-ttu-id="854d3-149">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854d3-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="854d3-150">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="854d3-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

