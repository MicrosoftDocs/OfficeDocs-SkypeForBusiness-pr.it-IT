---
title: 'Lync Server 2013: configurare un servizio informazioni posizione secondario'
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
ms.openlocfilehash: c2b7ee9383939e8df5466d615f6fda4a2af33c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="e2d36-102">Configurare un servizio di informazioni sulla posizione secondaria in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2d36-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2d36-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="e2d36-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="e2d36-104">Lync Server 2013 offre un'interfaccia di servizio Web che può essere usata per puntare il servizio informazioni sulla posizione in un database di origine della posizione secondaria (SLS).</span><span class="sxs-lookup"><span data-stu-id="e2d36-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="e2d36-105">L'interfaccia del servizio Web che si connette al database SLS deve essere conforme al WSDL del servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="e2d36-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="e2d36-106">Se sono configurati sia il database della posizione che il database della posizione secondaria, il servizio informazioni sulla posizione esegue prima di tutto il database della posizione e, se non viene trovata alcuna corrispondenza, Invia la richiesta di posizione dal client al database SLS.</span><span class="sxs-lookup"><span data-stu-id="e2d36-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="e2d36-107">Se la posizione esiste nella SLS, il servizio informazioni sulla posizione restituirà la posizione al client.</span><span class="sxs-lookup"><span data-stu-id="e2d36-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="e2d36-108">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="e2d36-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="e2d36-109">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="e2d36-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="e2d36-110">Per configurare il database delle posizioni secondarie</span><span class="sxs-lookup"><span data-stu-id="e2d36-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="e2d36-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2d36-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2d36-112">Eseguire il cmdlet seguente per configurare l'URL per la posizione del database della posizione secondaria.</span><span class="sxs-lookup"><span data-stu-id="e2d36-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

