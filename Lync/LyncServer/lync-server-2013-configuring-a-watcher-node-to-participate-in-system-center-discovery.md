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
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Configurazione di un nodo Watcher in Lync Server 2013 per la partecipazione all'individuazione di System Center

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Per assicurarsi che il nodo Watcher partecipi al processo di individuazione per System Center Operations Manager, è necessario eseguire la procedura seguente in un computer in cui è stata installata la console di System Center Operations Manager:

1.  Nella scheda **Amministrazione** fare clic su **Gestito tramite agente**.

2.  Fare clic con il pulsante destro del mouse sul nome del computer del nodo Watcher e scegliere **Proprietà**. Nella scheda **Sicurezza** della finestra di dialogo **Proprietà** selezionare **Consenti a questo agente di funzionare come proxy e individuare oggetti gestiti sugli altri computer**, quindi fare clic su **OK**.

Dopo aver configurato il nodo Watcher affinché funga da proxy, riavviare il computer. Dopo aver riavviato il computer, verificare che non vengano registrati eventi di errore nel registro eventi di Operations Manager in quel computer. Una volta che il computer è stato in esecuzione per 15 minuti, utilizzare la console di Operations Manager per verificare che i computer Lync Server siano elencati nella categoria **Lync** .

</div>

<span> </span>

</div>

</div>

</div>

