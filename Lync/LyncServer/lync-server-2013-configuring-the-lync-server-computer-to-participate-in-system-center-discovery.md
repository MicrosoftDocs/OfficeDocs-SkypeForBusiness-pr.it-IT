---
title: Configurazione del computer Lync Server per la partecipazione all'individuazione di System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b8e95ead01c89f33346a66a8212245c2350894f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="6b4b0-102">Configurazione del computer Lync Server 2013 per la partecipazione all'individuazione di System Center</span><span class="sxs-lookup"><span data-stu-id="6b4b0-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b4b0-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6b4b0-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6b4b0-104">Per assicurarsi che il nuovo agente Lync Server partecipi al processo di individuazione per System Center Operations Manager, è necessario eseguire la procedura seguente in ogni computer in cui è stata installata la console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="6b4b0-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="6b4b0-105">Nella scheda **Amministrazione** fare clic su **Gestito tramite agente**.</span><span class="sxs-lookup"><span data-stu-id="6b4b0-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="6b4b0-p101">Fare clic con il pulsante destro del mouse sul nome del computer e scegliere **Proprietà**. Nella scheda **Sicurezza** della finestra di dialogo **Proprietà** selezionare **Consenti a questo agente di funzionare come proxy e individuare oggetti gestiti sugli altri computer**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b4b0-p101">Right-click the name of the computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="6b4b0-p102">Dopo aver completato il passaggio 2, riavviare il servizio Agente integrità. Il riavvio del servizio forzerà il rilevamento del nuovo computer. Se non si riavvia il servizio, potrebbero essere necessarie fino a 4 ore prima che il nuovo computer venga rilevato da System Center Operations Manager. Dopo il riavvio del servizio, verificare che nel registro eventi di Operations Manager del computer in questione non vengano registrati eventi di errore.</span><span class="sxs-lookup"><span data-stu-id="6b4b0-p102">After completing step 2, reboot the Health Agent service. (Rebooting the service will “force” discovery of the new machine. If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.). After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

