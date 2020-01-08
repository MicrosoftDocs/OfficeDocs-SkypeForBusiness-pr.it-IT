---
title: Installazione dei file di base di Lync Server 2013 e del database RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99eccdd8d6473c25c6096c370f616975c7da141f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Installazione dei file di base di Lync Server 2013 e del database RTCLocal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

Per installare i file principali di Lync Server 2013 in un computer, eseguire la procedura seguente. Il database RTCLocal viene installato automaticamente quando si installano i file di base. Tieni presente che non è necessario installare SQL Server nei nodi Watcher. In alternativa, SQL Server Express viene installato automaticamente.

Per installare i file di base di Lync Server 2013 e il database di RTCLocal:

1.  Nel computer del nodo Watcher fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

2.  Nella finestra della console digitare il comando seguente e quindi premere INVIO, usando il percorso appropriato per i file di configurazione di Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Per verificare che i componenti di base di Lync Server siano stati installati correttamente, fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**. In Lync Server 2013 Management Shell digitare il comando di Windows PowerShell seguente e quindi premere INVIO:

    Get-CsWatcherNodeConfiguration

La prima volta che si esegue questo comando non vengono restituiti dati perché non sono ancora stati configurati i computer dei nodi Watcher. Purché il comando venga eseguito senza restituire un errore, è possibile supporre che la configurazione del server Lync sia stata completata correttamente.

Se il computer del nodo Watcher si trova all'interno della rete perimetrale, è possibile eseguire il comando seguente per verificare l'installazione di Lync Server 2013:

    Get-CsPinPolicy

Verranno ricevute informazioni simili a quelle seguenti, a seconda del numero di criteri PIN (Personal Identification Number) configurati per l'uso nell'organizzazione:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Se vengono visualizzate informazioni sui criteri PIN, significa che sono stati installati correttamente i componenti principali.

</div>

<span> </span>

</div>

</div>

</div>

