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
ms.openlocfilehash: 5f5c313bab7c307a0dbc1a8e78269a94663d9c67
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Configurazione del computer Lync Server 2013 per la partecipazione all'individuazione di System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

Per assicurarsi che il nuovo agente Lync Server partecipi al processo di individuazione per System Center Operations Manager, è necessario eseguire la procedura seguente in ogni computer in cui è stata installata la console di System Center Operations Manager:

1.  Nella scheda **Amministrazione** fare clic su **Gestito tramite agente**.

2.  Fare clic con il pulsante destro del mouse sul nome del computer e scegliere **Proprietà**. Nella scheda **Sicurezza** della finestra di dialogo **Proprietà** selezionare **Consenti a questo agente di funzionare come proxy e individuare oggetti gestiti sugli altri computer**, quindi fare clic su **OK**.

Dopo aver completato il passaggio 2, riavviare il servizio Agente integrità. Il riavvio del servizio forzerà il rilevamento del nuovo computer. Se non si riavvia il servizio, potrebbero essere necessarie fino a 4 ore prima che il nuovo computer venga rilevato da System Center Operations Manager. Dopo il riavvio del servizio, verificare che nel registro eventi di Operations Manager del computer in questione non vengano registrati eventi di errore.

</div>

<span> </span>

</div>

</div>

</div>

