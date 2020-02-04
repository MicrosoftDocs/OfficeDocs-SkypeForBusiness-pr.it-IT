---
title: 'Lync Server 2013: componente Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363b277003d7ca1581475ec7c1197bb0f60ccfaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Componente Mediation Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

È necessario distribuire Lync Server 2013, Mediation Server se si distribuisce il carico di lavoro VoIP aziendale. Questa sezione descrive le funzionalità di base, le dipendenze, le topologie base e le linee guida per la pianificazione.

Il Mediation Server traduce la segnalazione e, in alcune configurazioni, il supporto tra l'infrastruttura di Lync Server 2013, le infrastrutture VoIP aziendale e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol). Sul lato Lync Server 2013, Mediation Server è in ascolto su un unico indirizzo di trasporto Mutual TLS (MTLS). Sul lato del gateway, Mediation Server è in ascolto su tutte le porte di ascolto associate associate ai trunk definiti nel documento di topologia. Tutti i gateway qualificati devono supportare TLS, ma possono abilitare anche TCP. TCP è supportato per i gateway che non supportano TLS.

Se si ha anche un PBX (Public Branch Exchange) esistente nell'ambiente, Mediation Server gestisce le chiamate tra gli utenti di VoIP aziendale e il PBX. Se il PBX è un IP-PBX, è possibile creare una connessione SIP diretta tra il PBX e il Mediation Server. Se il PBX è un PBX TDM (Time Division Multiplex), è necessario distribuire anche un gateway PSTN tra Mediation Server e il PBX.

Il Mediation Server è collocato con il front end server per impostazione predefinita. Il Mediation Server può essere distribuito anche in un pool autonomo per motivi di prestazioni oppure se si distribuisce il trunking SIP, in questo caso è consigliabile usare il pool autonomo.

Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool di Mediation Server autonomo. Un pool di Mediation Server autonomo non è necessario perché i gateway qualificati sono in grado di bilanciamento del carico DNS in un pool di server di mediazione e possono ricevere traffico da qualsiasi Mediation Server in un pool.

È anche consigliabile collocare il Mediation Server in un pool Front-end quando si sono distribuiti IP-PBX o connettersi a un SBC (Session Border Controller) di un provider di telefonia Internet, purché siano soddisfatte le condizioni seguenti:

  - IP-PBX o SBC è configurato per ricevere il traffico da qualsiasi Mediation Server nel pool e può instradare il traffico uniformemente a tutti i server di mediazione nel pool.

  - IP-PBX non supporta il bypass multimediale, ma il pool Front-end che ospita il Mediation Server può gestire la transcodifica vocale per le chiamate a cui il bypass multimediale non si applica.

È possibile usare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool di front end in cui si vuole collocare il Mediation Server può gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

Di seguito sono riportate le funzioni principali di Mediation Server:

  - Crittografia e decrittografia di SRTP sul lato server Lync

  - Traduzione di SIP su TCP (per i gateway che non supportano TLS) per il SIP tramite Mutual TLS

  - Traduzione di flussi multimediali tra Lync Server e il peer del gateway del Mediation Server

  - Connettere i client esterni alla rete ai componenti ICE interni, che consentono l'attraversamento multimediale di NAT e firewall

  - Fungendo da intermediario per i flussi di chiamata non supportati da un gateway, ad esempio le chiamate di operatori remoti in un client VoIP aziendale

  - Nelle distribuzioni che includono il trunking SIP, che collabora con il provider di servizi di trunking SIP per ottenere il supporto PSTN, che elimina la necessità di un gateway PSTN

Nella figura seguente vengono illustrati i protocolli di segnalazione e multimediali usati dal Mediation Server quando si comunica con un gateway PSTN di base e con l'infrastruttura VoIP aziendale.

**Segnalazioni e protocolli multimediali usati dal Mediation Server**

![Diagramma dei protocolli del Mediation Server](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramma dei protocolli del Mediation Server")

<div>


> [!NOTE]  
> Se si usa TCP o RTP/RTCP (invece di SRTP o SRTCP) nella rete tra il gateway PSTN e il Mediation Server, è consigliabile adottare misure per garantire la sicurezza e la privacy della rete.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Trunk M:N in Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Servizi di emergenza avanzati e Mediation Server in Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Bypass multimediale e Mediation Server in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Componenti e topologie per Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Linee guida per la distribuzione di Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

