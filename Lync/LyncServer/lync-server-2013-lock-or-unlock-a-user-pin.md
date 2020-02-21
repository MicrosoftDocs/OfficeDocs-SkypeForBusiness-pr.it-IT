---
title: 'Lync Server 2013: bloccare o sbloccare il PIN di un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698bbb2138978cea9ca5b2aa75b5370ea7e11c14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="b3cf7-102">Bloccare o sbloccare il PIN di un utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3cf7-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3cf7-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b3cf7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b3cf7-104">È possibile bloccare o sbloccare il PIN di un utente dalla sezione **utenti** del pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="b3cf7-105">Per bloccare il PIN di un utente nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b3cf7-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b3cf7-106">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3cf7-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b3cf7-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b3cf7-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b3cf7-109">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b3cf7-110">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="b3cf7-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b3cf7-111">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b3cf7-112">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b3cf7-113">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="b3cf7-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b3cf7-114">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b3cf7-115">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b3cf7-116">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Diverso da**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b3cf7-117">A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="b3cf7-118">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="b3cf7-119">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="b3cf7-120">Fare clic sull'utente, su **Azione** e quindi su **Blocca PIN**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="b3cf7-121">Per sbloccare il PIN di un utente nel pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b3cf7-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b3cf7-122">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3cf7-123">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b3cf7-124">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b3cf7-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b3cf7-125">Sulla barra di spostamento sinistra fare clic su **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b3cf7-126">Utilizzare uno dei metodi seguenti per individuare un utente:</span><span class="sxs-lookup"><span data-stu-id="b3cf7-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b3cf7-127">Nella casella **Cerca utenti** digitare per intero nome visualizzato, nome, cognome, nome account SAM (Security Accounts Manager), indirizzo SIP o URI linea dell'account utente desiderato, oppure digitare la prima parte di questi e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b3cf7-128">Se è disponibile una query salvata, fare clic sull'icona **Apri query**, recuperare la query (file con estensione usf) mediante la finestra di dialogo **Apri** e quindi fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b3cf7-129">(Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:</span><span class="sxs-lookup"><span data-stu-id="b3cf7-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b3cf7-130">Fare clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b3cf7-131">Immettere una proprietà utente digitandola o selezionandola dall'elenco a discesa dopo aver fatto clic sulla freccia.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b3cf7-132">Nell'elenco a discesa **Uguale a** fare clic sull'operatore, ad esempio **Uguale a** o **Diverso da**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b3cf7-133">A seconda della proprietà utente selezionata, immettere i criteri che si desidera utilizzare per filtrare i risultati della ricerca digitandoli oppure facendo clic sulla freccia nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="b3cf7-134">Per aggiungere ulteriori clausole di ricerca alla query, fare clic su <STRONG>Aggiungi filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="b3cf7-135">Fare clic su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="b3cf7-136">Fare clic sull'utente, su **Azione** e quindi su **Sblocca PIN**.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b3cf7-137">Blocco e sblocco dei PIN utente tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3cf7-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b3cf7-138">È possibile bloccare e sbloccare i pin degli utenti utilizzando Windows PowerShell e i cmdlet Lock-CsClientPin e Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="b3cf7-139">È possibile eseguire questi cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b3cf7-140">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="b3cf7-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="b3cf7-141">Per bloccare il PIN di un utente</span><span class="sxs-lookup"><span data-stu-id="b3cf7-141">To lock a user PIN</span></span>

  - <span data-ttu-id="b3cf7-p104">Per bloccare il PIN di un utente, utilizzare il cmdlet Lock-CsClientPin. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b3cf7-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="b3cf7-144">Per sbloccare il PIN di un utente</span><span class="sxs-lookup"><span data-stu-id="b3cf7-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="b3cf7-p105">Per sbloccare il PIN di un utente, utilizzare il cmdlet Unlock-CsClientPin. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b3cf7-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="b3cf7-147">Per ulteriori informazioni, vedere l'argomento della Guida relativo ai cmdlet [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="b3cf7-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

