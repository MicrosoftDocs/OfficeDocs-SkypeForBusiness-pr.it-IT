---
title: Impedire nuove connessioni a Lync Server per la manutenzione del server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc787dee62152e9ace76663a084fe5c1c428b1f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Impedire nuove connessioni a Lync Server 2013 per la manutenzione del server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Lync Server consente di utilizzare un server offline, ad esempio per applicare aggiornamenti software o hardware, senza perdita di servizio per gli utenti.

Quando si specifica l'opzione per impedire nuove connessioni o chiamate a un server di un pool, smette di accettare nuove connessioni e chiamate non appena si implementa questa opzione. Le nuove connessioni e le nuove chiamate vengono indirizzate attraverso altri server del pool. Un server che impedisce nuove connessioni consente alle sessioni su connessioni esistenti di continuare fino alla loro fine naturale. Quando tutte le sessioni esistenti sono terminate, il server è pronto per essere portato offline.

Quando si impediscono nuove connessioni a un front end server, alcune funzionalità e servizi di Lync Server si basano sul bilanciamento del carico DNS per garantire che funzioni correttamente. Se non si utilizza il bilanciamento del carico DNS sul pool, le connessioni tramite questi servizi potrebbero non essere reinstradate ad altri server durante il periodo in cui il server sta impedendo nuove connessioni e, pertanto, quando il server viene portato in modalità non in linea alcune sessioni e le chiamate possono essere interrotto. Le caratteristiche che si basano sul bilanciamento del carico DNS per garantire che questa opzione funzioni correttamente sono le seguenti:

  - Operatore

  - Applicazione Annuncio conferenza

  - Applicazione Response Group

  - Applicazione Annuncio

  - Applicazione Parcheggio di chiamata

Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.

Oltre a impedire nuove connessioni per tutti i servizi su un server che esegue Lync Server, è inoltre possibile impedire nuove connessioni per singoli servizi di Lync Server. Ad esempio, questo metodo è utile in una situazione in cui è necessario applicare un aggiornamento di Lync Server che non richiede l'arresto dell'intero server. Si noti che quando si impediscono le connessioni per un servizio, è necessario selezionare un servizio nel modo in cui è raggruppato e visualizzato nell'elenco dei servizi di Windows. Ad esempio, il servizio front-end di Lync Server e l'agente di raccolta dati per il monitoraggio sono servizi di Lync Server distinti, ma nell'elenco dei servizi di Windows vengono consolidati e visualizzati come servizio front end di Lync Server. È possibile impedire le nuove connessioni per il servizio front end di Lync Server, ma non è possibile impedire la presenza di nuove connessioni per i due singoli servizi di Lync Server sottostanti.

<div>


> [!IMPORTANT]
> Quando si imposta un server per impedire nuove connessioni e quindi si riavvia il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitarlo, impostare il server solo per la sospensione e la ripresa manuali, prima di riavviarlo.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Per impedire nuove connessioni a Lync Server:

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Aprire la console snap-in Servizi: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Servizi**.

3.  Nell'elenco fare doppio clic sul servizio Windows Lync Server per cui si desidera impedire nuove connessioni.

4.  In **Stato servizio: In sospeso** nella finestra di dialogo Proprietà fare clic su **Pausa**.

5.  Accanto a **Tipo di avvio** fare clic su **Manuale**. Questa operazione è facoltativa, ma consigliata.
    
    <div>
    

    > [!IMPORTANT]
    > Quando si imposta un server per impedire nuove connessioni e quindi si riavvia il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitarlo, impostare il server solo per la sospensione e la ripresa manuali, prima di riavviarlo.

    
    </div>

6.  Al termine, fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

