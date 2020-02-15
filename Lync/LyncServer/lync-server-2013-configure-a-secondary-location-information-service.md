---
title: 'Lync Server 2013: configurare un servizio informazioni percorso secondario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50d63d8316c9ce18bdf8677686a655046601b326
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="5773b-102">Configurare un servizio informazioni percorso secondario in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5773b-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5773b-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="5773b-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="5773b-104">Lync Server 2013 fornisce un'interfaccia del servizio Web che è possibile utilizzare per configurare il servizio informazioni percorso in un database di origine percorso secondario (SLS).</span><span class="sxs-lookup"><span data-stu-id="5773b-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="5773b-105">L'interfaccia del servizio Web che si connette al database SLS deve essere conforme al WSDL del servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="5773b-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="5773b-106">Se sono configurati sia il database delle posizioni che il database delle posizioni secondarie, il servizio informazioni percorso prima esegue una query nel database delle posizioni e, se non viene trovata alcuna corrispondenza, Invia la richiesta di posizione dal client al database SLS.</span><span class="sxs-lookup"><span data-stu-id="5773b-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="5773b-107">Se la posizione esiste nella SLS, il servizio informazioni percorso invierà il percorso al client.</span><span class="sxs-lookup"><span data-stu-id="5773b-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="5773b-108">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5773b-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="5773b-109">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="5773b-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="5773b-110">Per configurare il database delle posizioni secondarie</span><span class="sxs-lookup"><span data-stu-id="5773b-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="5773b-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5773b-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5773b-112">Eseguire il cmdlet seguente per configurare l'URL per il percorso del database del percorso secondario.</span><span class="sxs-lookup"><span data-stu-id="5773b-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

