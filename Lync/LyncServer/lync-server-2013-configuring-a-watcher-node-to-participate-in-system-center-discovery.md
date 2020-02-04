---
title: Configurazione di un nodo Watcher per partecipare all'individuazione di System Center
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
ms.openlocfilehash: 9ca3724f9b5bc8200e2ca006d9fa7445d7368ab7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Configurazione di un nodo Watcher in Lync Server 2013 per partecipare all'individuazione di System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Per assicurarsi che il nodo Watcher partecipi al processo di individuazione di System Center Operations Manager, è necessario completare la procedura seguente in un computer in cui è stata installata la console di System Center Operations Manager:

1.  Nella scheda **Amministrazione** fare clic su **agente gestito**.

2.  Fare clic con il pulsante destro del mouse sul nome del computer del nodo Watcher e quindi scegliere **Proprietà**. Nella scheda **sicurezza** della finestra di dialogo **Proprietà** selezionare **Consenti all'agente di fungere da proxy e individuare gli oggetti gestiti in altri computer**e quindi fare clic su **OK**.

Dopo aver configurato il nodo Watcher per fungere da proxy, riavviare il computer del nodo Watcher. Dopo il riavvio del computer, verificare che non vengano registrati eventi di errore nel log eventi di Operations Manager in tale computer. Dopo aver eseguito per 15 minuti il computer, usare la console di Operations Manager per verificare che i computer di Lync Server siano elencati nella categoria **Lync** .

</div>

<span> </span>

</div>

</div>

</div>

