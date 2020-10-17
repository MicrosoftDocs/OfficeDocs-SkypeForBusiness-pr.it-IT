---
title: 'Lync Server 2013: aggiornamento dalla versione di valutazione'
description: 'Lync Server 2013: aggiornamento dalla versione di valutazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 340badf9f5d2506c50cf8c03faa82223eabbd5af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546252"
---
# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Aggiornamento dalla versione di valutazione di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-20_

Se è stata installata la versione di valutazione di Microsoft Lync Server 2013, sarà necessario aggiornare l'installazione di una copia con licenza del software. Ciò è dovuto al fatto che la versione di valutazione scade 180 giorni dopo l'installazione. Non sarà tuttavia necessario disinstallare completamente la versione di valutazione e quindi installare la versione con licenza. Al contrario, dopo aver ottenuto un codice di licenza valido, è possibile aggiornare la versione di valutazione di Lync Server 2013 eseguendo la procedura seguente in ogni computer che funge da server front-end di Lync Server, Director o server perimetrale. Si noti che non è necessario aggiornare i computer che svolgono altri ruoli del server, ad esempio Monitoring Server o server di archiviazione.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Aggiornamento dalla versione di valutazione di Microsoft Lync Server 2013

Per aggiornare un computer dalla versione di valutazione di Lync Server 2013 alla versione con licenza del software:

**Aggiornamento dalla versione di valutazione di Microsoft Lync Server 2013**

1.  Accedere al computer come amministratore locale.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.

3.  In Lync Server Management Shell, digitare il comando seguente e quindi premere INVIO:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Si noti che potrebbe essere necessario specificare il percorso completo del file server.msi. Questo file può essere trovato nella cartella Setup dei file di installazione del volume multimediale di Lync Server.

4.  Al termine dell'esecuzione del programma di installazione, digitare il comando seguente al prompt dei comandi e quindi premere INVIO:
    
        Enable-CsComputer

5.  Ripetere questa procedura in qualsiasi altro server front-end, Director o server perimetrale che esegua una copia di valutazione di Lync Server. Questa procedura deve essere eseguita anche su tutti i server di succursale distribuiti mediante i file di installazione dei supporti di Lync Server.

Se non si è certi che la versione di valutazione di Lync Server sia in esecuzione in un determinato computer, è possibile verificare che eseguendo il comando seguente da Lync Server Management Shell:

    Get-CsServerVersion

Il cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analizzerà il computer locale e fornirà una delle indicazioni seguenti:

  - Che il codice di licenza del volume di Lync Server è stato installato nel computer, il che significa che non è necessario alcun aggiornamento.

  - Che è stato installato il codice di licenza di valutazione di Lync Server, il che significa che il computer deve essere aggiornato.

  - Non è necessario alcun codice di contratto multilicenza nel computer. L'aggiornamento dalla versione di valutazione a quella con licenza è necessaria solo nei Front End Server, nei server Director e nei server perimetrali.

</div>

</div>

<span> </span>

</div>

</div>

</div>

