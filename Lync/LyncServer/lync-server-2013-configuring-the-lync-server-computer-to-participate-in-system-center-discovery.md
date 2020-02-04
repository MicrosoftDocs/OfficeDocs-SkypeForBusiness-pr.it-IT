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

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Configurazione del computer Lync Server 2013 per partecipare all'individuazione di System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

Per assicurarsi che il nuovo agente Lync Server partecipi al processo di individuazione di System Center Operations Manager, è necessario completare la procedura seguente in tutti i computer in cui è stata installata la console di System Center Operations Manager:

1.  Nella scheda **Amministrazione** fare clic su **agente gestito**.

2.  Fare clic con il pulsante destro del mouse sul nome del computer e quindi scegliere **Proprietà**. Nella scheda **sicurezza** della finestra di dialogo **Proprietà** selezionare **Consenti all'agente di fungere da proxy e individuare gli oggetti gestiti in altri computer**e quindi fare clic su **OK**.

Dopo aver completato il passaggio 2, riavviare il servizio Agente integrità. Il riavvio del servizio consente di "forzare" l'individuazione del nuovo computer. Se il servizio non viene riavviato, potrebbero essere necessarie fino a 4 ore prima che il nuovo computer venga individuato da System Center Operations Manager. Dopo il riavvio del servizio, verificare che non vengano registrati eventi di errore nel log eventi di Operations Manager in tale computer.

</div>

<span> </span>

</div>

</div>

</div>

