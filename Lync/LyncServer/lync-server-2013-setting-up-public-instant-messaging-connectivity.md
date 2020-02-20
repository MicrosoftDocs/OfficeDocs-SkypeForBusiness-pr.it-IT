---
title: 'Lync Server 2013: configurazione della connettività per la messaggistica istantanea pubblica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4887e419e45f6b6fb165dc7efff407332f3e150a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="cc5e6-102">Configurazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc5e6-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc5e6-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="cc5e6-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="cc5e6-p101">Se l'organizzazione desidera supportare la connettività di messaggistica istantanea pubblica con AOL, non è possibile utilizzare la Distribuzione guidata di Lync Server per richiedere il certificato. Eseguire le operazioni della procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="cc5e6-106">Configurazione della connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="cc5e6-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="cc5e6-p102">In un Front End server, aprire Generatore di topologie. Espandere Edge pool, quindi fare clic con il tasto destro del mouse su Server perimetrale o Pool di server perimetrali. or Edge server pool. Scegliere Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="cc5e6-p103">In Modifica Proprietà, sotto Generale, selezionare Abilita federazione per pool di server perimetrali (porta 5061). Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="cc5e6-p104">Fare clic su Azione, selezionare Topologia, selezionare Pubblica. Quando viene richiesto di pubblicare la topologia, fare clic su Avanti. Quando la pubblicazione è terminata, fare clic su Fine.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="cc5e6-p105">Nel server perimetrale, aprire la Distribuzione guidata di Lync Server. Fare clic su Installa o aggiorna il sistema Lync Server, quindi fare clic su Installazione o rimozione componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="cc5e6-p106">In Installazione componenti di Lync Server fare clic su Avanti. Nella schermata di riepilogo sono mostrate le azioni che vengono eseguite. Al termine della distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili. Fare clic su Fine per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="cc5e6-122">Per creare una richiesta di certificato per l'interfaccia esterna del server perimetrale per il supporto della connettività di messaggistica istantanea pubblica con AOL</span><span class="sxs-lookup"><span data-stu-id="cc5e6-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="cc5e6-123">Quando il modello richiesto è disponibile per la CA, utilizzare il cmdlet di Windows PowerShell seguente dal server perimetrale per richiedere il certificato:</span><span class="sxs-lookup"><span data-stu-id="cc5e6-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="cc5e6-124">Il nome del certificato predefinito del modello utilizzato per Lync Server è il server Web.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="cc5e6-125">Specificare il nome \<\> del modello solo se è necessario utilizzare un modello diverso dal modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cc5e6-126">Se l'organizzazione desidera supportare la connettività di messaggistica istantanea pubblica con AOL, è necessario utilizzare Windows PowerShell anziché la procedura guidata per richiedere il certificato da assegnare al server perimetrale esterno per il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="cc5e6-127">Il motivo è che il modello Web Server dell'Autorità di certificazione utilizzato dalla Configurazione guidata certificato per richiedere un certificato non supporta la configurazione dell'utilizzo chiavi avanzato (EKU) client.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="cc5e6-128">Prima di utilizzare Windows PowerShell per creare il certificato, l'amministratore della CA deve creare e distribuire un nuovo modello che supporti l'EKU client.</span><span class="sxs-lookup"><span data-stu-id="cc5e6-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

