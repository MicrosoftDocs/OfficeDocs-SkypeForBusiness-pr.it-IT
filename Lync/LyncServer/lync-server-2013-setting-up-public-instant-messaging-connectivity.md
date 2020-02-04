---
title: 'Lync Server 2013: Configurazione della connettività per la messaggistica istantanea pubblica'
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
ms.openlocfilehash: 871f513170fcb0491f6732751cfc1b23877526b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="2309c-102">Configurazione della connettività per la messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2309c-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2309c-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2309c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2309c-104">Se l'organizzazione vuole supportare la connettività di messaggistica istantanea pubblica con AOL, non è possibile usare la distribuzione guidata di Lync Server per richiedere il certificato.</span><span class="sxs-lookup"><span data-stu-id="2309c-104">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="2309c-105">Eseguire invece i passaggi descritti nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="2309c-105">Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="2309c-106">Configurazione della connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="2309c-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="2309c-107">In un server front-end aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="2309c-107">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="2309c-108">Espandere pool di bordi e quindi fare clic con il pulsante destro del mouse sull'Edge Server o sul pool Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2309c-108">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="2309c-109">Selezionare Modifica proprietà.</span><span class="sxs-lookup"><span data-stu-id="2309c-109">Select Edit properties.</span></span>

2.  <span data-ttu-id="2309c-110">In modifica proprietà in generale selezionare Abilita federazione per questo pool di bordi (porta 5061).</span><span class="sxs-lookup"><span data-stu-id="2309c-110">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="2309c-111">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2309c-111">Click OK.</span></span>

3.  <span data-ttu-id="2309c-112">Fare clic su azione, selezionare topologia, quindi pubblica.</span><span class="sxs-lookup"><span data-stu-id="2309c-112">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="2309c-113">Quando viene richiesto di pubblicare la topologia, fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="2309c-113">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="2309c-114">Al termine della pubblicazione, fare clic su fine.</span><span class="sxs-lookup"><span data-stu-id="2309c-114">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="2309c-115">Nell'Edge Server aprire la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2309c-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="2309c-116">Fare clic su Installa o aggiorna Lync Server System, quindi fare clic su Imposta o Rimuovi componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2309c-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="2309c-117">Fare di nuovo clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="2309c-117">Click Run Again.</span></span>

5.  <span data-ttu-id="2309c-118">In configurazione componenti di Lync Server fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="2309c-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="2309c-119">La schermata di riepilogo mostrerà le azioni Man mano che vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="2309c-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="2309c-120">Dopo aver completato la distribuzione, fare clic su Visualizza log per visualizzare i file di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="2309c-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="2309c-121">Fare clic su fine per completare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2309c-121">Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="2309c-122">Per creare una richiesta di certificato per l'interfaccia esterna di Edge Server per supportare la connettività di messaggistica istantanea pubblica con AOL</span><span class="sxs-lookup"><span data-stu-id="2309c-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="2309c-123">Quando il modello richiesto è disponibile per la CA, usare il cmdlet di Windows PowerShell seguente da su Edge Server per richiedere il certificato</span><span class="sxs-lookup"><span data-stu-id="2309c-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="2309c-124">Il nome del certificato predefinito del modello usato per Lync Server è Web Server.</span><span class="sxs-lookup"><span data-stu-id="2309c-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="2309c-125">Specifica il nome \<\> del modello solo se devi usare un modello diverso dal modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="2309c-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2309c-126">Se l'organizzazione vuole supportare la connettività di messaggistica istantanea pubblica con AOL, è necessario usare Windows PowerShell invece della procedura guidata certificato per richiedere che il certificato venga assegnato al bordo esterno per il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="2309c-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="2309c-127">Questo avviene perché il modello di server Web dell'autorità di certificazione (CA) che la creazione guidata certificato usa per richiedere un certificato non supporta la configurazione EKU client.</span><span class="sxs-lookup"><span data-stu-id="2309c-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="2309c-128">Prima di usare Windows PowerShell per creare il certificato, l'amministratore della CA deve creare e distribuire un nuovo modello che supporti EKU client.</span><span class="sxs-lookup"><span data-stu-id="2309c-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

