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
ms.openlocfilehash: db1637b711d2743d5a2e1fb8a5138949fc3a21ec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

Dopo aver pubblicato la topologia, la distribuzione guidata di Lync Server deve accedere ai dati dell'archivio di gestione centrale al fine di avviare il processo di distribuzione sul server. Nella rete interna, i dati sono disponibili direttamente dai server, ma i server perimetrali che non sono nel dominio interno non possono accedere ai dati. Per rendere disponibili i dati di configurazione della topologia per una distribuzione di server perimetrali, è necessario esportare i dati della topologia in un file e copiarli in un supporto esterno, ad esempio un'unità USB o una condivisione di rete disponibile dal server perimetrale, prima di eseguire la funzionalità di protezione esecuzione programmi di Lync Server. loyment Wizard sul server perimetrale. Utilizzare la procedura seguente per rendere disponibili i dati di configurazione della topologia nel server perimetrale che si sta distribuendo.

<div>


> [!NOTE]
> Dopo aver installato Lync Server 2013 in un server perimetrale, è possibile gestire il server perimetrale utilizzando gli strumenti di amministrazione della rete interna, che replicano automaticamente la configurazione in tutti i server perimetrali della distribuzione. L'unica eccezione è l'assegnazione e l'installazione di certificati e l'arresto e l'avvio dei servizi, che devono essere entrambi eseguiti nel server perimetrale.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Per rendere disponibili i dati della topologia in un server perimetrale tramite Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  In Lync Server Management Shell, eseguire il cmdlet seguente:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copiare il file esportato in un supporto esterno, ad esempio un'unità USB o una condivisione di rete disponibile dal server perimetrale durante la distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

