---
title: 'Lync Server 2013: avviare i servizi nei server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cab7d2e53b981cc971284cfad37f89ca4749590
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="0aac1-102">Avviare servizi nei server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0aac1-102">Start services on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0aac1-103">_**Ultimo argomento modificato:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="0aac1-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="0aac1-104">Per eseguire questa procedura, è necessario accedere come utente membro del gruppo RTCUniversalServerAdmins o disporre della delega delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="0aac1-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="0aac1-105">Per informazioni dettagliate su come delegare le autorizzazioni, vedere l'argomento [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0aac1-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="0aac1-106">Dopo l'installazione dell'archivio di configurazione locale nei server, l'installazione dei componenti di Lync Server 2013 e la configurazione dei certificati in un front end server o front end server, è necessario avviare i servizi Lync Server 2013 sul server.</span><span class="sxs-lookup"><span data-stu-id="0aac1-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="0aac1-107">Utilizzare la procedura seguente per avviare i servizi in ogni front end server della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0aac1-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="0aac1-108">Per avviare i servizi in un server Standard Edition o front end</span><span class="sxs-lookup"><span data-stu-id="0aac1-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="0aac1-109">Nella distribuzione guidata di Lync Server, nella pagina **Lync server 2013** , fare clic su **Esegui** accanto a **passaggio 4: Avvia servizi**.</span><span class="sxs-lookup"><span data-stu-id="0aac1-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="0aac1-110">Nella pagina **Avvia servizi** fare clic su **Avanti** per avviare i servizi Lync Server nel server.</span><span class="sxs-lookup"><span data-stu-id="0aac1-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="0aac1-111">Nella pagina **Esecuzione comandi in corso**, dopo l'avvio di tutti i servizi, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0aac1-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0aac1-112">Il comando per avviare i servizi nel server è un metodo di sforzo ottimale per segnalare che i servizi sono stati effettivamente avviati.</span><span class="sxs-lookup"><span data-stu-id="0aac1-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="0aac1-113">Potrebbe non rispecchiare lo stato effettivo del servizio.</span><span class="sxs-lookup"><span data-stu-id="0aac1-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="0aac1-114">È consigliabile utilizzare lo stato del servizio di passaggio <STRONG>(facoltativo)</STRONG> subito dopo l' <STRONG>avvio dei servizi</STRONG> per aprire Microsoft Management Console (MMC) e verificare che i servizi siano stati avviati correttamente.</span><span class="sxs-lookup"><span data-stu-id="0aac1-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="0aac1-115">Se un servizio di Lync Server non è stato avviato, è possibile fare clic con il pulsante destro del mouse su tale servizio in MMC e quindi scegliere <STRONG>Avvia</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0aac1-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

