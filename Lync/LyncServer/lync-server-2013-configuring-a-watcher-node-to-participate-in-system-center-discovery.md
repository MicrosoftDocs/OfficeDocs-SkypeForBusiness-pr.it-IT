---
title: Configurazione di un nodo Watcher per la partecipazione all'individuazione di System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49b34e623b885bb7e85afc258c1d533c2a8feb46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527003"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="71d7d-102">Configurazione di un nodo Watcher in Lync Server 2013 per la partecipazione all'individuazione di System Center</span><span class="sxs-lookup"><span data-stu-id="71d7d-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71d7d-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="71d7d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="71d7d-104">Per assicurarsi che il nodo Watcher partecipi al processo di individuazione per System Center Operations Manager, è necessario eseguire la procedura seguente in un computer in cui è stata installata la console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="71d7d-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="71d7d-105">Nella scheda **Amministrazione** fare clic su **Gestito tramite agente**.</span><span class="sxs-lookup"><span data-stu-id="71d7d-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="71d7d-p101">Fare clic con il pulsante destro del mouse sul nome del computer del nodo Watcher e scegliere **Proprietà**. Nella scheda **Sicurezza** della finestra di dialogo **Proprietà** selezionare **Consenti a questo agente di funzionare come proxy e individuare oggetti gestiti sugli altri computer**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="71d7d-p101">Right-click the name of the watcher node computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="71d7d-108">Dopo aver configurato il nodo Watcher affinché funga da proxy, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="71d7d-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="71d7d-109">Dopo aver riavviato il computer, verificare che non vengano registrati eventi di errore nel registro eventi di Operations Manager in quel computer.</span><span class="sxs-lookup"><span data-stu-id="71d7d-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="71d7d-110">Una volta che il computer è stato in esecuzione per 15 minuti, utilizzare la console di Operations Manager per verificare che i computer Lync Server siano elencati nella categoria **Lync** .</span><span class="sxs-lookup"><span data-stu-id="71d7d-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

