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
ms.openlocfilehash: 8cec18903f1621d5a616debbbdd16f3c834ac21c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="359f6-102">Configurazione del computer Lync Server 2013 per partecipare all'individuazione di System Center</span><span class="sxs-lookup"><span data-stu-id="359f6-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="359f6-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="359f6-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="359f6-104">Per assicurarsi che il nuovo agente Lync Server partecipi al processo di individuazione di System Center Operations Manager, è necessario completare la procedura seguente in tutti i computer in cui è stata installata la console di System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="359f6-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="359f6-105">Nella scheda **Amministrazione** fare clic su **agente gestito**.</span><span class="sxs-lookup"><span data-stu-id="359f6-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="359f6-106">Fare clic con il pulsante destro del mouse sul nome del computer e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="359f6-106">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="359f6-107">Nella scheda **sicurezza** della finestra di dialogo **Proprietà** selezionare **Consenti all'agente di fungere da proxy e individuare gli oggetti gestiti in altri computer**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="359f6-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="359f6-108">Dopo aver completato il passaggio 2, riavviare il servizio Agente integrità.</span><span class="sxs-lookup"><span data-stu-id="359f6-108">After completing step 2, reboot the Health Agent service.</span></span> <span data-ttu-id="359f6-109">Il riavvio del servizio consente di "forzare" l'individuazione del nuovo computer.</span><span class="sxs-lookup"><span data-stu-id="359f6-109">(Rebooting the service will “force” discovery of the new machine.</span></span> <span data-ttu-id="359f6-110">Se il servizio non viene riavviato, potrebbero essere necessarie fino a 4 ore prima che il nuovo computer venga individuato da System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="359f6-110">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.).</span></span> <span data-ttu-id="359f6-111">Dopo il riavvio del servizio, verificare che non vengano registrati eventi di errore nel log eventi di Operations Manager in tale computer.</span><span class="sxs-lookup"><span data-stu-id="359f6-111">After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

