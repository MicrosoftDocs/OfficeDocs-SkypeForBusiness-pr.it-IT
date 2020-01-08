---
title: 'Lync Server 2013: aggiornamento dalla versione di valutazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b00fed276229cbaf0e960e28e622e490fb0bfbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Aggiornamento dalla versione di valutazione di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-20_

Se è stata installata la versione di valutazione di Microsoft Lync Server 2013, sarà necessario aggiornare l'installazione di una copia concessa in licenza del software; il motivo è che la versione di valutazione scade 180 giorni dopo l'installazione. Tuttavia, non dovrai disinstallare completamente la versione di valutazione e quindi installare la versione con licenza. Dopo aver ottenuto un codice di licenza valido, è invece possibile aggiornare la versione di valutazione di Lync Server 2013 eseguendo la procedura seguente in tutti i computer che agiscono come server front-end di Lync Server, Director o Edge Server. Si noti che non è necessario aggiornare i computer che eseguono altri ruoli del server, ad esempio un server di monitoraggio o un server di archiviazione.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Aggiornamento dalla versione di valutazione di Microsoft Lync Server 2013

Per aggiornare un computer dalla versione di valutazione di Lync Server 2013 alla versione con licenza del software:

**Aggiornamento dalla versione di valutazione di Microsoft Lync Server 2013**

1.  Accedere al computer come amministratore locale.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Lync Server 2013**e quindi su **Lync Server Management Shell**.

3.  In Lync Server Management Shell digitare il comando seguente e quindi premere INVIO:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Tieni presente che potresti dover specificare il percorso completo del file server. msi. Questo file può essere trovato nella cartella Setup dei file di installazione del volume media di Lync Server.

4.  Al termine dell'esecuzione della configurazione, digitare quanto segue dal prompt dei comandi e quindi premere INVIO:
    
        Enable-CsComputer

5.  Ripetere questa procedura in qualsiasi altro server front-end, Director o Edge Server che esegua una copia di valutazione di Lync Server. Questa procedura deve essere eseguita anche in tutti i server di succursale distribuiti tramite i file di installazione di Lync Server media.

Se non si è certi che la versione di valutazione di Lync Server sia in esecuzione in un computer specifico, è possibile verificare che eseguendo il comando seguente all'interno di Lync Server Management Shell:

    Get-CsServerVersion

Il cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analizza il computer locale e riporta una delle opzioni seguenti:

  - Che il codice di licenza del volume di Lync Server è stato installato nel computer, quindi non è necessario alcun aggiornamento.

  - Che il codice di licenza di valutazione di Lync Server è stato installato, quindi il computer deve essere aggiornato.

  - Non è necessario alcun codice di licenza volume nel computer. L'aggiornamento dalla versione di valutazione alla versione con licenza è richiesto solo nei server front-end, nei direttori e nei server perimetrali.

</div>

</div>

<span> </span>

</div>

</div>

</div>

