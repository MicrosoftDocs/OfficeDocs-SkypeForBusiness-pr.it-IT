---
title: 'Lync Server 2013: Testare il server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889d548ddc9b177113aa3e395ac181095de8008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="2f890-102">Testare il server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f890-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f890-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2f890-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2f890-104">A questo punto, è configurato un pool di Director o Director, ma le voci SRV di Domain Name System (DNS) devono ancora puntare i client per accedere tramite un pool o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2f890-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="2f890-105">Prima di modificare il record DNS in modo che i client di Lync 2013 accedano automaticamente tramite il Director, testare un client manualmente puntando il puntatore del mouse sul Director.</span><span class="sxs-lookup"><span data-stu-id="2f890-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="2f890-106">Per testare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="2f890-106">To test the deployment</span></span>

1.  <span data-ttu-id="2f890-107">Accedere al computer in cui è installato il pannello di controllo di Lync Server con un account di dominio che fa parte del gruppo **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="2f890-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="2f890-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f890-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f890-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2f890-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f890-110">Nel riquadro di spostamento fare clic su **topologia**e nella colonna **stato** verificare che sia presente un server verde con una freccia, ovvero l'icona del server con l'icona del server ![freccia verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "con freccia verde"), per il pool di Director o Director.</span><span class="sxs-lookup"><span data-stu-id="2f890-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="2f890-111">Connettere due computer client con il client Lync Server 2013 installato e accedere con un account utente diverso abilitato per Lync Server 2013 a ogni computer.</span><span class="sxs-lookup"><span data-stu-id="2f890-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="2f890-112">In uno dei computer client fare clic sul menu **Opzioni** , selezionare il gruppo impostazioni **personali** , fare clic su **Avanzate**, su **configurazione manuale**e quindi impostare il **nome del server interno o l'indirizzo IP** per il nome di dominio completo (FQDN) del nuovo pool di Director o Director.</span><span class="sxs-lookup"><span data-stu-id="2f890-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="2f890-113">Accedere a entrambi i client e verificare che il client che esegue l'accesso tramite il Director sia in grado di accedere correttamente, vedere lo stato presenza dell'altro utente e che possano scambiare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="2f890-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

