---
title: Abilitare l'integrazione di Outlook Web App e messaggistica istantanea di Exchange 2013
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
ms.openlocfilehash: 0bd9fb94dd0f068547819aa884b608ac6ddf7e39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="d306d-102">Abilitare l'integrazione di Outlook Web App e messaggistica istantanea di Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="d306d-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d306d-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d306d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d306d-104">Per abilitare l'integrazione di Outlook Web Access (OWA) e messaggistica istantanea di Exchange 2013 con Lync Server 2013, è necessario aggiungere il server di accesso client di Exchange 2013 Server (CAS) alla topologia di Lync Server 2013 come server applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="d306d-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="d306d-105">Per creare un pool di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="d306d-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="d306d-106">Avviare Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d306d-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="d306d-107">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="d306d-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="d306d-108">Viene restituita la siteID per il nomesito in cui si sta creando il pool.</span><span class="sxs-lookup"><span data-stu-id="d306d-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="d306d-109">Per informazioni dettagliate, vedere [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d306d-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="d306d-110">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="d306d-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="d306d-111">Per informazioni dettagliate, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d306d-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="d306d-112">L'FQDN di Exchange Server deve essere configurato come nome soggetto del certificato OWA di Exchange (SN) o il nome alternativo soggetto (SAN).</span><span class="sxs-lookup"><span data-stu-id="d306d-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="d306d-113">In Exchange OWA verificare che sia attendibile anche il nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="d306d-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d306d-114">Se il server CAS <EM>non</EM> è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, ignorare i passaggi rimanenti di questa procedura ed eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d306d-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="d306d-115">Se il server CAS è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, completare i passaggi descritti in questa procedura e non eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d306d-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="d306d-116">Eseguire **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="d306d-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="d306d-117">Aprire Generatore di topologia e scaricare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="d306d-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="d306d-118">Nel riquadro sinistro espandere l'albero fino a raggiungere i **server delle applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="d306d-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="d306d-119">Espandere il nodo **Trusted Application Servers** .</span><span class="sxs-lookup"><span data-stu-id="d306d-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="d306d-120">È ora necessario vedere il server CAS di Exchange 2013 elencato come server delle applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="d306d-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="d306d-121">Per creare un'applicazione attendibile per il server CAS di Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="d306d-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="d306d-122">Avviare Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d306d-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="d306d-123">Se il server CAS *non* è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="d306d-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="d306d-124">Per informazioni dettagliate, vedere l'argomento [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d306d-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="d306d-125">Eseguire **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="d306d-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="d306d-126">Nel riquadro sinistro di generatore di topologia espandere l'albero fino a raggiungere i **server delle applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="d306d-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="d306d-127">Espandere il nodo **Trusted Application Servers** .</span><span class="sxs-lookup"><span data-stu-id="d306d-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="d306d-128">È ora necessario vedere il server CAS di Exchange 2013 elencato come server delle applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="d306d-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

