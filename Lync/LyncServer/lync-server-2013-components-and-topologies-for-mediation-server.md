---
title: 'Lync Server 2013: componenti e topologie per Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369c7ab74f19b8ccc53ff0c071e0458b21e6e0f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Componenti e topologie per Mediation Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

In questo argomento vengono descritti i componenti in base ai quali il Mediation Server è dipendente e le topologie in cui è possibile distribuire Mediation Server

<div>

## <a name="dependencies"></a>Dipendenze

Il Mediation Server presenta le dipendenze seguenti:

  - **Registrar.** Obbligatorio. Il servizio di registrazione è l'hop successivo per la segnalazione nelle interazioni di Mediation Server con la rete Lync Server 2013. Si noti che Mediation Server può essere collocato in un front end server insieme al registrar, oltre ad essere installato in un pool autonomo costituito da solo Mediation Server. Il servizio di registrazione è collocato con un Mediation Server e un gateway PSTN in un Survivable Branch Appliance.

  - **Monitoring Server.** Facoltativo ma consigliato. Il Monitoring Server consente al Mediation Server di registrare le metriche di qualità associate alle sessioni multimediali.

  - **Edge server (Server perimetrale).** Obbligatorio per il supporto degli utenti esterni. Il server perimetrale consente al Mediation Server di interagire con gli utenti che si trovano dietro un NAT o un firewall.

</div>

<div>

## <a name="topologies"></a>Topologie

Lync Server 2013, Mediation Server è collocato per impostazione predefinita con un'istanza del servizio di registrazione in un server Standard Edition, in un pool Front end o in un Survivable Branch Appliance. Tutti i Mediation Server in un pool Front end devono essere configurati in modo identico.

Se le prestazioni sono un problema, potrebbe essere preferibile distribuire uno o più Mediation Server in un pool autonomo dedicato. In alternativa, se si sta distribuendo il trunking SIP, è consigliabile distribuire un pool Mediation Server autonomo.

Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool Mediation Server autonomo. Ciò è dovuto al fatto che i gateway qualificati possono effettuare il bilanciamento del carico DNS in un pool di Mediation Server e ricevere traffico da qualsiasi Mediation Server di un pool.

È inoltre consigliabile collocare il Mediation Server in un pool Front End se sono stati distribuiti sistemi IP-PBX o si effettua la connessione al Session Border Controller (SBC) di un provider di servizi di telefonia Internet, purché vengano soddisfatte una o più delle condizioni seguenti:

  - Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.

  - Il sistema IP-PBX non supporta il bypass multimediale, ma il pool Front end che ospita il Mediation Server è in grado di gestire la transcodifica vocale per le chiamate a cui non si applica il bypass multimediale.

È possibile utilizzare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool Front end in cui si desidera collocare il Mediation Server è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

Per informazioni dettagliate sulla distribuzione della topologia, vedere [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Nella figura seguente viene illustrata una semplice topologia costituita da due siti connessi tramite un collegamento WAN. Mediation Server è collocato con il servizio di registrazione in un pool Front End nel sito 1. I Mediation Server nel sito 1 controllano sia il gateway PSTN nel sito 1 che il gateway nel sito 2. In questa topologia il bypass multimediale è abilitato a livello globale per utilizzare informazioni su siti e aree ed è abilitato anche per i trunk a ogni gateway PSTN (GW1 e GW2).

**Esempio di siti connessi tramite un collegamento WAN a un server Mediation Server nel sito 1 e a un gateway PSTN nel sito 2**

![Topologia vocale con gateway WAN Mediation Server](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologia vocale con gateway WAN Mediation Server")

Nella figura seguente viene illustrata una topologia semplice in cui il Mediation Server è collocato con il servizio di registrazione nel pool Front end del sito 1 e dispone di una connessione SIP diretta al sistema IP-PBX nel sito 1. In questa figura, Mediation Server controlla anche un gateway PSTN nel sito 2. Si supponga che gli utenti di Lync esistano in entrambi i siti 1 e 2. Si supponga inoltre che il sistema IP-PBX disponga di un processore multimediale associato che deve essere attraversato da tutti i supporti provenienti da endpoint di Lync prima di essere inviati agli endpoint multimediali controllati dall'IP-PBX. In questa topologia, il bypass multimediale è abilitato a livello globale per l'utilizzo delle informazioni relative a siti e aree geografiche, mentre i trunk del PBX e del gateway PSTN dispongono del bypass multimediale abilitato.

**Esempio di siti connessi tramite un collegamento WAN a un server Mediation Server nel sito 1 e a un sistema PBX nel sito 2**

![Topologia vocale Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Topologia vocale Mediation Server WAN PBX")

Per informazioni dettagliate sulla pianificazione delle topologie PBX, vedere [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) e [Direct SIP Deployment Options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

Nell'ultima figura di questo argomento viene illustrata una topologia in cui Mediation Server è connesso all'SBC di un provider di servizi di telefonia Internet. Per informazioni dettagliate sulle topologie trunk SIP, vedere [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

