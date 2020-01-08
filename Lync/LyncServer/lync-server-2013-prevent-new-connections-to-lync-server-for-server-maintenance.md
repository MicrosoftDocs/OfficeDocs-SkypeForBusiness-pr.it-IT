---
title: Impedire nuove connessioni a Lync Server per la manutenzione del server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3838af59a6a91699fa6d38b8aa2912e2b30012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Impedire le nuove connessioni a Lync Server 2013 per la manutenzione del server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Lync Server consente di prendere un server offline, ad esempio per applicare aggiornamenti software o hardware, senza perdere il servizio agli utenti.

Quando si specifica l'opzione per impedire le nuove connessioni o le chiamate a un server in un pool, smette di accettare nuove connessioni e chiamate non appena si implementa questa opzione. Queste nuove connessioni e chiamate vengono instradate tramite altri server nel pool. Un server che impedisce le nuove connessioni consente di continuare le sessioni sulle connessioni esistenti finché non terminano naturalmente. Quando tutte le sessioni esistenti sono terminate, il server è pronto per essere preso offline.

Quando si impediscono nuove connessioni a un server front-end, alcune caratteristiche e servizi di Lync Server si basano sul bilanciamento del carico DNS per verificare che funzioni correttamente. Se non si usa il bilanciamento del carico DNS sul pool, le connessioni tramite questi servizi potrebbero non essere reindirizzate ad altri server durante il periodo in cui il server impedisce le nuove connessioni e quindi quando il server viene disconnesso alcune sessioni e le chiamate possono essere interrotti. Le caratteristiche che si basano sul bilanciamento del carico DNS per verificare che questa opzione funzioni correttamente sono le seguenti:

  - Operatore

  - Applicazione per l'annuncio di conferenza

  - Response Group Application

  - Applicazione annuncio

  - Applicazione Parcheggio di chiamata

Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.

Oltre a impedire le nuove connessioni per tutti i servizi in un server che gestisce Lync Server, è anche possibile evitare nuove connessioni per singoli servizi di Lync Server. Questo metodo, ad esempio, è utile in una situazione in cui è necessario applicare un aggiornamento di Lync Server che non richiede l'arresto dell'intero server. Si noti che quando si impediscono le connessioni per un servizio, è necessario selezionare un servizio mentre viene raggruppato e visualizzato nell'elenco di servizi di Windows. Ad esempio, il servizio front-end di Lync Server e l'agente di raccolta dati per il monitoraggio sono servizi di Lync Server distinti, ma nell'elenco dei servizi Windows vengono consolidati e visualizzati come servizio front-end di Lync Server. Puoi impedire le nuove connessioni per il servizio front-end di Lync Server, ma non puoi impedire le nuove connessioni per questi due singoli servizi di Lync Server sottostante separatamente.

<div>


> [!IMPORTANT]
> Quando si imposta un server per impedire nuove connessioni e quindi riavviare il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitare questo problema, imposta il server solo per sospendere e riprendere manualmente, prima di riavviare il server.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Per evitare nuove connessioni a Lync Server:

1.  Accedere al computer locale come membro del gruppo Administrators.

2.  Aprire la console snap-in Servizi: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Servizi**.

3.  Nell'elenco fare doppio clic sul servizio Windows Lync Server a cui si vogliono impedire le nuove connessioni.

4.  Nella finestra di dialogo Proprietà, in **stato del servizio: avviato**, fare clic su **Sospendi**.

5.  Facoltativamente, ma consigliato, accanto a **tipo di avvio**, fare clic su **manuale**.
    
    <div>
    

    > [!IMPORTANT]
    > Quando si imposta un server per impedire nuove connessioni e quindi riavviare il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitare questo problema, imposta il server solo per sospendere e riprendere manualmente, prima di riavviare il server.

    
    </div>

6.  Al termine, fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

