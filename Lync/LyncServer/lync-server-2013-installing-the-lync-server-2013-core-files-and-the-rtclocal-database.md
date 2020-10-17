---
title: Installazione dei file principali di Lync Server 2013 e del database di RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc12092e08980fcb1863b18805260ac307cc6d3d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534863"
---
# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Installazione dei file principali di Lync Server 2013 e del database di RTCLocal

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

Per installare i file di base di Lync Server 2013 in un computer, eseguire la procedura seguente. Il database RTCLocal viene installato automaticamente con i file principali. Si noti che non è necessario installare SQL Server nei nodi Watcher. Al contrario, SQL Server Express viene installato automaticamente.

Per installare i file di base di Lync Server 2013 e il database di RTCLocal:

1.  Nel computer del nodo Watcher fare clic su **Start**, scegliere **Tutti i programmi**, **Accessori**, quindi fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

2.  Nella finestra della console digitare il comando seguente e quindi premere INVIO, utilizzando il percorso appropriato per i file di installazione di Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Per verificare che i componenti di base di Lync Server siano stati installati correttamente, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server 2013**e quindi **Lync Server Management Shell**. In Lync Server 2013 Management Shell, digitare il comando di Windows PowerShell seguente e quindi premere INVIO:

    Get-CsWatcherNodeConfiguration

Quando si esegue questo comando per la prima volta, non viene restituito alcun dato perché non è ancora stato configurato alcun computer del nodo Wwatcher. Se il comando viene eseguito senza restituire un errore, è possibile presumere che il programma di installazione di Lync Server sia stato completato correttamente.

Se il computer del nodo Watcher si trova all'interno della rete perimetrale, è possibile eseguire il comando riportato di seguito per verificare l'installazione di Lync Server 2013:

    Get-CsPinPolicy

Verranno restituite informazioni, a seconda del numero di criteri PIN configurati per l'uso nell'organizzazione:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Se vengono restituite informazioni sui criteri PIN, i componenti principali sono stati correttamente installati.

</div>

<span> </span>

</div>

</div>

</div>

