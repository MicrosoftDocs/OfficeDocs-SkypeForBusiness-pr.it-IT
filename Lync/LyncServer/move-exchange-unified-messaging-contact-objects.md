---
title: Spostare gli oggetti contatto della messaggistica unificata di Exchange
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c02e391fa66084a27e3790ccaf42753bcaeaa16
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="de2e5-102">Spostare gli oggetti contatto della messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="de2e5-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de2e5-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="de2e5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="de2e5-104">Per eseguire la migrazione degli oggetti contatto dell'operatore automatico (AA) e dell'accesso sottoscrittore (SA) alla nuova distribuzione di Lync Server 2013, è necessario prima di tutto spostare gli oggetti dalla distribuzione di Office Communications Server 2007 R2 legacy alla nuova distribuzione di Lync Server 2013 utilizzando i cmdlet **Get-CsExUmContact** e **Move-CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="de2e5-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="de2e5-105">Sul server Exchange, eseguire lo script di Windows PowerShell di **ExchUCUtil** per effettuare le seguenti operazioni per il pool Lync appena distribuito:</span><span class="sxs-lookup"><span data-stu-id="de2e5-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="de2e5-106">Aggiungerlo ai gateway IP di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="de2e5-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="de2e5-107">Aggiungerlo ai gruppi di risposta di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="de2e5-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de2e5-p102">Per poter utilizzare i cmdlet <STRONG>Get-CsExUmContact</STRONG> e <STRONG>Move-CsExUmContact</STRONG>, è necessario essere membri del gruppo RTCUniversalUserAdmins e disporre dell'autorizzazione per l'unità organizzativa (OU) in cui sono archiviati gli oggetti contatto. Tale autorizzazione può essere concessa eseguendo il cmdlet <STRONG>Grant-OUPermission</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="de2e5-p102">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="de2e5-110">Per spostare gli oggetti contatto utilizzando Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="de2e5-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="de2e5-111">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="de2e5-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="de2e5-112">Per ogni pool registrato con messaggistica unificata di Exchange (dove pool1.contoso.net è un pool della distribuzione di Office Communications Server 2007 R2 e pool2.contoso.net è il pool della distribuzione di Lync Server 2013) dalla riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="de2e5-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="de2e5-113">Per accertarsi che gli oggetti contatto siano stati spostati, eseguire il cmdlet **Get-CsExumContact** e verificare che **RegistrarPool** ora punti al nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="de2e5-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="de2e5-114">Per eseguire lo script ExchUCUtil di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de2e5-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="de2e5-115">Accedere al server di messaggistica unificata di Exchange come utente con privilegi di amministratore dell'organizzazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="de2e5-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="de2e5-116">Passare allo script di Windows PowerShell di ExchUCUtil.</span><span class="sxs-lookup"><span data-stu-id="de2e5-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="de2e5-117">In Exchange 2007, ExchUCUtil. ps1 si trova in: **% Program Files%\\Microsoft\\Exchange Server\\Scripts\\exchucutil. ps1**</span><span class="sxs-lookup"><span data-stu-id="de2e5-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="de2e5-118">In Exchange 2010, ExchUCUtil. ps1 si trova in: **% Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\exchucutil. ps1**</span><span class="sxs-lookup"><span data-stu-id="de2e5-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="de2e5-119">Se Exchange è distribuito in una singola foresta, digitare quanto indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="de2e5-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="de2e5-120">In alternativa, se Exchange è distribuito in più foreste, digitare quanto indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="de2e5-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="de2e5-121">dove la foresta FQDN Specifica la foresta in cui è distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de2e5-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="de2e5-122">Riavviare il servizio <STRONG>Lync Server Front End</STRONG> (rtcsrv.exe) <EM>dopo</EM> aver eseguito exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="de2e5-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="de2e5-123">In caso contrario, Lync Server 2013 non rileva la messaggistica unificata nella topologia.</span><span class="sxs-lookup"><span data-stu-id="de2e5-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

