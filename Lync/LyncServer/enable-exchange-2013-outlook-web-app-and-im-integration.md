---
title: Abilitare l'integrazione di Exchange 2013 Outlook Web App e della messaggistica istantanea
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
ms.openlocfilehash: a67dd3c18525d7a39678b5871d087ea79c502fce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="c807c-102">Abilitare l'integrazione di Exchange 2013 Outlook Web App e della messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="c807c-102">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c807c-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="c807c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c807c-104">Per abilitare l'integrazione di Exchange 2013 Outlook Web Access (OWA) e della messaggistica istantanea con Lync Server 2013, è necessario aggiungere il server Accesso client (CAS) di Exchange 2013 alla topologia di Lync Server 2013 come server applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="c807c-104">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="c807c-105">Per creare un pool di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="c807c-105">To create a trusted application pool</span></span>

1.  <span data-ttu-id="c807c-106">Avviare Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c807c-106">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="c807c-107">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c807c-107">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="c807c-108">Verrà restituito l'ID sito per il nome del sito in cui si sta creando il pool.</span><span class="sxs-lookup"><span data-stu-id="c807c-108">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="c807c-109">Per informazioni dettagliate, vedere [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c807c-109">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="c807c-110">Eseguire il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c807c-110">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="c807c-111">Per ulteriori informazioni, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c807c-111">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="c807c-112">Il nome di dominio completo (FQDN) del server di Exchange deve essere configurato come nome oggetto (SN) del certificato Exchange OWA o come nome alternativo del soggetto (SAN).</span><span class="sxs-lookup"><span data-stu-id="c807c-112">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="c807c-113">In Exchange OWA verificare anche che il nome FQDN del pool sia attendibile.</span><span class="sxs-lookup"><span data-stu-id="c807c-113">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c807c-114">Se il server CAS <EM>non</EM> è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, ignorare i passaggi rimanenti di questa procedura ed eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c807c-114">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="c807c-115">Se il server CAS è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, completare i passaggi descritti in questa procedura e non eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c807c-115">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="c807c-116">Eseguire **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="c807c-116">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="c807c-117">Aprire il Generatore di topologie e scaricare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="c807c-117">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="c807c-118">Nel riquadro di sinistra espandere l'albero finché non si raggiunge **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="c807c-118">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="c807c-119">Espandere il nodo **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="c807c-119">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="c807c-120">È ora necessario vedere il server CAS di Exchange 2013 elencato come server applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="c807c-120">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="c807c-121">Per creare un'applicazione attendibile per il server CAS di Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="c807c-121">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="c807c-122">Avviare Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c807c-122">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="c807c-123">Se il server CAS *non* è collocato nello stesso server che esegue la messaggistica unificata di Exchange 2013, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c807c-123">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="c807c-124">Per ulteriori informazioni, vedere l'argomento [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) nella documentazione di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c807c-124">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="c807c-125">Eseguire **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="c807c-125">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="c807c-126">Nel riquadro di sinistra del Generatore di topologie espandere l'albero finché non si raggiunge **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="c807c-126">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="c807c-127">Espandere il nodo **Server applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="c807c-127">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="c807c-128">È ora necessario vedere il server CAS di Exchange 2013 elencato come server applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="c807c-128">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

