---
title: 'Lync Server 2013: Componenti e topologie per Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Componenti e topologie per Mediation Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

In questo argomento vengono descritti i componenti in cui è dipendente il Mediation Server e le topologie in cui è possibile distribuire il Mediation Server

<div>

## <a name="dependencies"></a>Dipendenze

Il Mediation Server ha le dipendenze seguenti:

  - **Registrar.** Obbligatorio. Il registrar è l'hop successivo per la segnalazione nelle interazioni di Mediation Server con la rete Lync Server 2013. Si noti che Mediation Server può essere collocato in un server front-end insieme al registrar, oltre ad essere installato in un pool autonomo costituito solo da server di mediazione. Il registrar è collocato con un Mediation Server e un gateway PSTN in un Survivable Branch Appliance.

  - **Server di monitoraggio.** Facoltativo, ma altamente raccomandato. Il server di monitoraggio consente al Mediation Server di registrare le metriche di qualità associate alle proprie sessioni multimediali.

  - **Edge Server.** Obbligatorio per il supporto degli utenti esterni. Il server perimetrale consente al Mediation Server di interagire con gli utenti che si trovano dietro un NAT o un firewall.

</div>

<div>

## <a name="topologies"></a>Tecnologie

Lync Server 2013, Mediation Server è collocato per impostazione predefinita con un'istanza del registrar in un server Standard Edition, un pool Front end o un Survivable Branch Appliance. Tutti i Mediation Server in un pool Front-end devono essere configurati in modo identico.

In caso di problemi di prestazioni, può essere preferibile distribuire uno o più server di mediazione in un pool autonomo dedicato. In alternativa, se si distribuisce il trunking SIP, è consigliabile distribuire un pool di Mediation Server autonomo.

Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool di Mediation Server autonomo. Un pool di Mediation Server autonomo non è necessario perché i gateway qualificati sono in grado di bilanciamento del carico DNS in un pool di server di mediazione e possono ricevere traffico da qualsiasi Mediation Server in un pool.

È anche consigliabile collocare il Mediation Server in un pool Front-end quando si sono distribuiti IP-PBX o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:

  - IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.

  - IP-PBX non supporta il bypass multimediale, ma il pool Front-end che ospita il Mediation Server può gestire la transcodifica vocale per le chiamate a cui il bypass multimediale non si applica.

È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool di front end in cui si vuole collocare il Mediation Server può gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

Per informazioni dettagliate sulla topologia da distribuire, vedere [linee guida per la distribuzione di Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

La figura seguente mostra una semplice topologia costituita da due siti collegati da un collegamento WAN. Mediation Server è collocato con il registrar in un pool Front-End nel sito 1. I Mediation Server del sito 1 controllano sia il gateway PSTN sul sito 1 che il gateway nel sito 2. In questa topologia, il bypass multimediale è abilitato globalmente per l'uso delle informazioni sul sito e le aree geografiche e i trunk per ogni gateway PSTN (GW1 e GW2) hanno un bypass abilitato.

**Esempio di siti collegati da un collegamento WAN a un Mediation Server presso il sito 1 e un gateway PSTN sul sito 2**

![Topologia vocale con topologia vocale gateway WAN Mediation Server](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "con gateway WAN Mediation Server")

Nella figura seguente è illustrata una semplice topologia in cui il Mediation Server è collocato con il registrar nel pool Front-end del sito 1 ed è collegato direttamente al protocollo IP-PBX nel sito 1. In questa figura il Mediation Server controlla anche un gateway PSTN sul sito 2. Supponiamo che gli utenti di Lync esistano in entrambi i siti 1 e 2. Si supponga inoltre che IP-PBX disponga di un processore multimediale associato che deve essere attraversato da tutti gli elementi multimediali provenienti da endpoint di Lync prima di essere inviati agli endpoint multimediali controllati da IP-PBX. In questa topologia, il bypass multimediale è abilitato globalmente per l'uso di informazioni sul sito e le aree geografiche e i Trunks per il PBX e il gateway PSTN sono abilitati per il bypass multimediale.

**Esempio di siti collegati da un collegamento WAN con un Mediation Server presso il sito 1 e un PBX presso il sito 2**

Topologia vocale ![Mediation]server(images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "WAN PBX")

Per informazioni dettagliate sulla pianificazione delle topologie PBX, vedere [linee guida per la distribuzione di Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) e [Opzioni di distribuzione SIP dirette in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

L'ultima figura in questo argomento Mostra una topologia in cui il Mediation Server è connesso all'SBC di un provider di servizi di telefonia Internet. Per informazioni dettagliate sulle topologie trunk SIP, vedere [trunking SIP in Lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

