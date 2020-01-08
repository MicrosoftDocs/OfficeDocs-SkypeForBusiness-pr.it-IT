---
title: 'Lync Server 2013: Avviare servizi nei server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c0c14aea9966e61703e85dd2aff8a2e448d5eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="82cf1-102">Avviare servizi nei server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82cf1-102">Start services on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82cf1-103">_**Argomento Ultima modifica:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="82cf1-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="82cf1-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins o avere le autorizzazioni corrette Delegate.</span><span class="sxs-lookup"><span data-stu-id="82cf1-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="82cf1-105">Per informazioni dettagliate sulla delega delle autorizzazioni, vedere l'argomento [autorizzazioni di configurazione per i delegati in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="82cf1-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="82cf1-106">Dopo l'installazione dell'archivio di configurazione locale nei server, installare i componenti di Lync Server 2013 e configurare i certificati in un front end server o front end server, è necessario avviare i servizi di Lync Server 2013 nel server.</span><span class="sxs-lookup"><span data-stu-id="82cf1-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="82cf1-107">Usare la procedura seguente per avviare i servizi in ogni server front-end della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="82cf1-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="82cf1-108">Per avviare i servizi in una versione standard o front end server</span><span class="sxs-lookup"><span data-stu-id="82cf1-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="82cf1-109">Nella pagina **Lync server 2013** della distribuzione guidata di Lync Server fare clic su **Esegui** accanto al **passaggio 4: avviare i servizi**.</span><span class="sxs-lookup"><span data-stu-id="82cf1-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="82cf1-110">Nella pagina **Start Services** fare clic su **Avanti** per avviare i servizi di Lync Server nel server.</span><span class="sxs-lookup"><span data-stu-id="82cf1-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="82cf1-111">Nella pagina **esecuzione dei comandi** , dopo aver avviato tutti i servizi, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="82cf1-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="82cf1-112">Il comando per avviare i servizi sul server è un metodo di sforzo ottimale per segnalare che i servizi sono effettivamente stati avviati.</span><span class="sxs-lookup"><span data-stu-id="82cf1-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="82cf1-113">Potrebbe non corrispondere allo stato effettivo del servizio.</span><span class="sxs-lookup"><span data-stu-id="82cf1-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="82cf1-114">È consigliabile usare lo stato del servizio di passaggio <STRONG>(facoltativo)</STRONG> subito dopo i <STRONG>Servizi Start</STRONG> per aprire Microsoft Management Console (MMC) e verificare che i servizi siano stati avviati correttamente.</span><span class="sxs-lookup"><span data-stu-id="82cf1-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="82cf1-115">Se un servizio di Lync Server non è stato avviato, è possibile fare clic con il pulsante destro del mouse su tale servizio in MMC e quindi scegliere <STRONG>Avvia</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="82cf1-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

