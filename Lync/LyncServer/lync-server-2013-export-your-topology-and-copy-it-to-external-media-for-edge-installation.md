---
title: Esportare la topologia e copiarla su supporto esterno per l'installazione perimetrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Dopo aver pubblicato la topologia, la distribuzione guidata di Lync Server deve accedere ai dati di Central Management store per avviare il processo di distribuzione nel server. Nella rete interna i dati sono disponibili direttamente dai server, ma i server perimetrali non inclusi nel dominio interno non possono accedere ai dati. Per rendere disponibili i dati di configurazione della topologia per una distribuzione di Edge Server, è necessario esportare i dati della topologia in un file e copiarli in elementi multimediali esterni, ad esempio un'unità USB o una condivisione di rete disponibile dall'Edge Server, prima di eseguire la protezione esecuzione programmi di Lync Server loyment guidata nel server perimetrale. Usare la procedura seguente per rendere disponibili i dati di configurazione della topologia nell'Edge Server che si sta distribuendo.

<div>


> [!NOTE]
> Dopo l'installazione di Lync Server 2013 in un server perimetrale, è possibile gestire il server perimetrale usando gli strumenti di amministrazione della rete interna, che riproducono automaticamente la configurazione in qualsiasi server perimetrale della distribuzione. L'unica eccezione è l'assegnazione e l'installazione di certificati e l'arresto e l'avvio dei servizi, che devono essere eseguiti nel server perimetrale.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Per rendere disponibili i dati della topologia in un server perimetrale tramite Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  In Lync Server Management Shell eseguire il cmdlet seguente:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copiare il file esportato in elementi multimediali esterni, ad esempio un'unità USB o una condivisione di rete disponibile dall'Edge Server durante la distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

