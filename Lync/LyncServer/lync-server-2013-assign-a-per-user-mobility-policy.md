---
title: 'Lync Server 2013: assegnare un criterio per dispositivi mobili per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1014bce74e0e7dcd789c9b2948c029f4b40ecb9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030139"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="ded65-102">Assegnare un criterio per dispositivi mobili per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ded65-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="ded65-103">I criteri per dispositivi mobili sono una delle singole impostazioni di un account utente che è possibile configurare nel pannello di controllo di Lync Server o in Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ded65-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="ded65-104">Per assegnare criteri dispositivi mobili per utente con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ded65-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ded65-105">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ded65-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ded65-106">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ded65-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ded65-107">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ded65-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ded65-108">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="ded65-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="ded65-109">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="ded65-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="ded65-110">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="ded65-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="ded65-111">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="ded65-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="ded65-112">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="ded65-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="ded65-113">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="ded65-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="ded65-114">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="ded65-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="ded65-115">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Non uguale a**).</span><span class="sxs-lookup"><span data-stu-id="ded65-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="ded65-116">A seconda della proprietà utente selezionata, immettere i criteri da utilizzare per filtrare i risultati della ricerca digitandoli o facendo clic sulla freccia dell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="ded65-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="ded65-117">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ded65-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="ded65-118">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="ded65-118">Click **Find**.</span></span>

6.  <span data-ttu-id="ded65-119">Fare clic su un utente all'interno dei risultati della ricerca, fare clic su **Azione** e quindi fare clic su **Assegna criteri**.</span><span class="sxs-lookup"><span data-stu-id="ded65-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="ded65-120">Se si desidera applicare lo stesso criterio per dispositivi mobili per utente a più utenti, selezionare più utenti nei risultati della ricerca, quindi fare clic su <STRONG>azioni</STRONG>e quindi su <STRONG>Assegna criteri</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ded65-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="ded65-121">In **Assegna criteri**, in **criteri dispositivi mobili**, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ded65-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="ded65-122">Poiché esistono più criteri che è possibile configurare in <STRONG>Assegna criteri</STRONG>, <STRONG> &lt;Mantieni come è&gt; </STRONG> selezionato per impostazione predefinita per tutti i criteri nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ded65-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="ded65-123">Per continuare a utilizzare i criteri assegnati in precedenza all'utente, non modificare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="ded65-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="ded65-124">Selezionare \*\* \<automatico\> \*\* per consentire a Lync Server 2013 di scegliere automaticamente i criteri a livello globale o, se definiti, i criteri a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="ded65-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="ded65-125">Fare clic sul nome di un criterio dispositivi mobili per utente definito in precedenza nella pagina **criteri dispositivi mobili** .</span><span class="sxs-lookup"><span data-stu-id="ded65-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="ded65-126">Per decidere quali criteri assegnare, dopo aver selezionato un nome di criteri, fare clic su <STRONG>Visualizza</STRONG> per visualizzare i diritti utente e le autorizzazioni definite nei criteri.</span><span class="sxs-lookup"><span data-stu-id="ded65-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="ded65-127">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ded65-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ded65-128">Assegnazione di un criterio per dispositivi mobili per utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ded65-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ded65-129">È possibile assegnare criteri per dispositivi mobili per utente utilizzando Windows PowerShell e il cmdlet **Grant-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="ded65-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="ded65-130">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ded65-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ded65-131">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="ded65-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="ded65-132">Per assegnare criteri dispositivi mobili per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="ded65-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="ded65-133">Il comando seguente assegna il criterio per dispositivi mobili per utente RedmondMobilityPolicy all'utente Ken.</span><span class="sxs-lookup"><span data-stu-id="ded65-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="ded65-134">Per assegnare criteri dispositivi mobili per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="ded65-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="ded65-135">Il comando seguente assegna il criterio per dispositivi mobili per utente RedmondMobilityPolicy a tutti gli utenti a cui è attualmente assegnato il criterio NorthAmericaMobilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="ded65-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="ded65-136">Per informazioni dettagliate sul parametro Filter utilizzato in questo comando, vedere [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="ded65-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="ded65-137">Per annullare l'assegnazione di un criterio per dispositivi mobili per utente</span><span class="sxs-lookup"><span data-stu-id="ded65-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="ded65-138">Il comando seguente annulla l'assegnazione di qualsiasi criterio di mobilità per utente precedentemente assegnato a Ken.</span><span class="sxs-lookup"><span data-stu-id="ded65-138">The following command unassigns any per-user mobility policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="ded65-139">Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="ded65-139">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="ded65-140">I criteri del sito hanno la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="ded65-140">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="ded65-141">Per informazioni dettagliate, vedere [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="ded65-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="ded65-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ded65-142">See Also</span></span>


[<span data-ttu-id="ded65-143">Configurazione di criteri per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ded65-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

