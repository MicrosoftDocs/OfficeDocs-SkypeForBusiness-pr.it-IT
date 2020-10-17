---
title: 'Lync Server 2013: testare il Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae7f2945cd3a21ea93969e098110fadec710cb98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519093"
---
# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="b89ac-102">Testare il Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b89ac-102">Test the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b89ac-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b89ac-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b89ac-104">In questa fase, è configurato un server Director o un pool di Director, ma le voci SRV DNS (Domain Name System) sono ancora in grado di eseguire l'accesso dei client tramite un pool o uno Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b89ac-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="b89ac-105">Prima di modificare il record DNS per fare in modo che i client di Lync 2013 accedano automaticamente tramite il server Director, testare un client facendole riferimento manualmente al server Director.</span><span class="sxs-lookup"><span data-stu-id="b89ac-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="b89ac-106">Per testare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="b89ac-106">To test the deployment</span></span>

1.  <span data-ttu-id="b89ac-107">Accedere al computer in cui è installato il pannello di controllo di Lync Server con un account di dominio che fa parte del gruppo **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="b89ac-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="b89ac-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b89ac-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b89ac-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b89ac-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b89ac-110">Nel riquadro di spostamento fare clic su **topologia**e nella colonna **stato** verificare che sia presente un server verde con una freccia, ovvero un' ![icona del server con freccia verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Icona del server con freccia verde"), per il Director o il pool di Director.</span><span class="sxs-lookup"><span data-stu-id="b89ac-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="b89ac-111">Connettere due computer client in cui è installato il client Lync Server 2013 e accedere con un account utente diverso abilitato per Lync Server 2013 su ogni computer.</span><span class="sxs-lookup"><span data-stu-id="b89ac-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="b89ac-112">In uno dei computer client fare clic sul menu **Opzioni** , selezionare il gruppo di impostazioni **personali** , fare clic su **Avanzate**, fare clic su **configurazione manuale**e quindi impostare il **nome o l'indirizzo IP del server interno** sul nome di dominio completo (FQDN) del nuovo Director o del pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="b89ac-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="b89ac-113">Accedere a entrambi i client e verificare che il client che accede utilizzando il Director sia in grado di eseguire l'accesso, vedere lo stato di presenza dell'altro utente e che possano scambiare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="b89ac-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

