---
title: 'Lync Server 2013: trunk M:N'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accb2efafddc9253deda7fa20006dd9093e32496
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>Trunk M:N in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Lync Server 2013 supporta una maggiore flessibilità nella definizione di un trunk per il routing delle chiamate dalle versioni precedenti. Un trunk è un'associazione logica tra un Mediation Server e il numero di porta di ascolto con un gateway e un numero di porta di attesa. Questo implica diverse operazioni: un Mediation Server può disporre di più trunk allo stesso gateway; un Mediation Server può disporre di più trunk per Gateway diversi; viceversa, un gateway può disporre di più trunk per diversi Mediation Server.

È comunque necessario che venga creato un trunk radice quando viene aggiunto un gateway alla topologia di Lync tramite Generatore di topologie. Il numero di gateway che un determinato Mediation Server può gestire dipende dalla capacità di elaborazione del server durante le ore di punta occupato. Se si distribuisce un Mediation Server sull'hardware che supera i requisiti hardware minimi per Lync Server 2013, come descritto in [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità, la stima del numero di chiamate non di bypass attive che un Mediation Server autonomo è in grado di gestire è approssimativamente 1000 chiamate. Quando si distribuisce sull'hardware per soddisfare queste specifiche, è previsto che il Mediation Server esegua la transcodifica, ma ancora instradare le chiamate per più gateway anche se i gateway non supportano il bypass multimediale.

Quando si definisce una route di chiamata, è necessario specificare i trunk associati a tale route, ma non si specifica quali Mediation Server sono associati a tale route. In alternativa, è possibile utilizzare il generatore di topologie per associare trunk a Mediation Server. In altre parole, il routing determina quale trunk utilizzare per una chiamata e, successivamente, il Mediation Server associato a tale trunk viene inviato alla segnalazione per la chiamata.

Il Mediation Server può essere distribuito come pool. questo pool può essere collocato con un pool Front end oppure può essere distribuito come pool autonomo. Quando un Mediation Server è collocato con un pool Front End, le dimensioni del pool possono essere al massimo 12 (il limite delle dimensioni del pool di registrazione). Insieme, queste nuove funzionalità aumentano la flessibilità di affidabilità e distribuzione per i Mediation Server, ma richiedono funzionalità associate nelle entità peer seguenti:

  - **Gateway PSTN.** Un gateway qualificato di Lync Server 2013 deve implementare il bilanciamento del carico DNS, che consente a un gateway PSTN (Public Switched Telephone Network) qualificato di fungere da servizio di bilanciamento del carico per un pool di Mediation Server e, quindi, per il bilanciamento del carico delle chiamate tra il pool.

  - **Session border controller.** Per un trunk SIP, l'entità peer è un session border controller (SBC) in un provider di servizi di telefonia Internet. Nella direzione del pool di Mediation Server verso l'SBC, l'SBC può ricevere connessioni da qualsiasi Mediation Server nel pool. Nella direzione da SBC al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Un metodo per raggiungere questo obiettivo avviene tramite il bilanciamento del carico DNS, se supportato dal provider di servizi e dal servizio SBC. Un'alternativa consiste nel fornire al provider di servizi gli indirizzi IP di tutti i Mediation Server nel pool e il provider di servizi provisionerà questi nel proprio SBC come trunk SIP separato per ogni Mediation Server. Il provider di servizi gestirà quindi il bilanciamento del carico per i propri server. Non tutti i provider di servizi o SBCs possono supportare queste funzionalità. Inoltre, è possibile che il provider di servizi richieda una tariffa supplementare per questa funzionalità. In genere, ciascun trunk SIP per il SBC comporta una tariffa mensile.

  - **IP-PBX.** Nella direzione dal pool di Mediation Server alla terminazione SIP IP-PBX, l'IP-PBX può ricevere connessioni da qualsiasi Mediation Server nel pool. Nella direzione da IP-PBX al pool, il traffico può essere inviato a qualsiasi Mediation Server nel pool. Poiché la maggior parte dei sistemi IP-PBX non supporta il bilanciamento del carico DNS, è consigliabile definire singole connessioni SIP dirette dall'IP-PBX a ogni Mediation Server nel pool. Il sistema IP-PBX gestirà quindi il bilanciamento del carico distribuendo il traffico sul gruppo di trunk. Si presuppone che il gruppo di trunk disponga di un insieme coerente di regole di routing nel sistema IP-PBX. Se un determinato IP-PBX supporta questo concetto di gruppo Trunk e la modalità di intersezione con la ridondanza e l'architettura di clustering del sistema IP-PBX deve essere determinata prima di poter decidere se un cluster di Mediation Server può interagire correttamente con un IP-PBX.

Un pool di Mediation Server deve disporre di una visualizzazione uniforme del gateway peer con cui interagisce. Questo significa che tutti i membri del pool accedono alla stessa definizione del gateway peer dall'archivio di configurazione e sono ugualmente suscettibili di interagire con esso per le chiamate in uscita. Pertanto, non esiste alcun modo per segmentare il pool in modo che alcuni Mediation Server comunicano con solo alcuni peer gateway per le chiamate in uscita. Se tale segmentazione è necessaria, è necessario utilizzare un pool separato di Mediation Server. Questo è il caso, ad esempio, se le funzionalità associate nei gateway PSTN, trunk SIP o IP-PBX per interagire con un pool come descritto in precedenza in questo argomento non sono presenti.

Un particolare gateway PSTN, IP-PBX o peer trunk SIP può essere instradato a più server Mediation o trunk. Il numero di gateway che un pool specifico di Mediation Server può controllare dipende dal numero di chiamate che utilizzano il bypass multimediale. Se un numero elevato di chiamate utilizza il bypass multimediale, un Mediation Server nel pool è in grado di gestire molte più chiamate, perché è necessario solo l'elaborazione dei layer di segnalazione.

</div>

<span> </span>

</div>

</div>

</div>

