---
title: Abilitare l'integrazione di Exchange 2013 Outlook Web App e della messaggistica istantanea
description: Abilitare l'integrazione di Exchange 2013 Outlook Web App e della messaggistica istantanea.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7fd6e8600f255d6ac4dde52487776cdb5fe1a51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551122"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="b0ade-103">Abilitare l'integrazione di Exchange 2013 Outlook Web App e della messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="b0ade-103">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0ade-104">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b0ade-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b0ade-105">Per abilitare l'integrazione di Exchange 2013 Outlook Web Access (OWA) e della messaggistica istantanea con Lync Server 2013, è necessario aggiungere il server Accesso client (CAS) di Exchange 2013 alla topologia di Lync Server 2013 come server applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="b0ade-105">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="b0ade-106">Per creare un pool di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="b0ade-106">To create a trusted application pool</span></span>

1.  <span data-ttu-id="b0ade-107">Avviare Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0ade-107">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="b0ade-108">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="b0ade-108">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="b0ade-109">Verrà restituito l'ID sito per il nome del sito in cui si sta creando il pool.</span><span class="sxs-lookup"><span data-stu-id="b0ade-109">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="b0ade-110">Per informazioni dettagliate, vedere [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0ade-110">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="b0ade-111">Eseguire il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0ade-111">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="b0ade-112">Per ulteriori informazioni, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0ade-112">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="b0ade-113">Il nome di dominio completo (FQDN) del server di Exchange deve essere configurato come nome oggetto (SN) del certificato Exchange OWA o come nome alternativo del soggetto (SAN).</span><span class="sxs-lookup"><span data-stu-id="b0ade-113">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="b0ade-114">In Exchange OWA verificare anche che il nome FQDN del pool sia attendibile.</span><span class="sxs-lookup"><span data-stu-id="b0ade-114">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b0ade-115">Se il server CAS <EM>non</EM> è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, ignorare i passaggi rimanenti di questa procedura ed eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b0ade-115">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="b0ade-116">Se il server CAS è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, completare i passaggi descritti in questa procedura e non eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b0ade-116">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="b0ade-117">Eseguire **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="b0ade-117">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="b0ade-118">Aprire il Generatore di topologie e scaricare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="b0ade-118">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="b0ade-119">Nel riquadro di sinistra espandere l'albero finché non si raggiunge **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="b0ade-119">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="b0ade-120">Espandere il nodo **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="b0ade-120">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="b0ade-121">È ora necessario vedere il server CAS di Exchange 2013 elencato come server applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="b0ade-121">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="b0ade-122">Per creare un'applicazione attendibile per il server CAS di Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="b0ade-122">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="b0ade-123">Avviare Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0ade-123">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="b0ade-124">Se il server CAS *non* è collocato nello stesso server che esegue la messaggistica unificata di Exchange 2013, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="b0ade-124">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="b0ade-125">Per ulteriori informazioni, vedere l'argomento [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b0ade-125">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="b0ade-126">Eseguire **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="b0ade-126">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="b0ade-127">Nel riquadro di sinistra del Generatore di topologie espandere l'albero finché non si raggiunge **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="b0ade-127">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="b0ade-128">Espandere il nodo **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="b0ade-128">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="b0ade-129">È ora necessario vedere il server CAS di Exchange 2013 elencato come server applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="b0ade-129">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

