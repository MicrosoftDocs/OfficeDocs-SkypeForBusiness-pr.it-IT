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
ms.openlocfilehash: e8ddc21554ce57601f61e4b37d1988ca3e4dad65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513753"
---
# <a name="mediation-server-component-in-lync-server-2013"></a>Componente Mediation Server in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Se si distribuisce il carico di lavoro VoIP aziendale, è necessario distribuire Lync Server 2013, Mediation Server. In questa sezione vengono descritte la funzionalità di base, le dipendenze, le topologie di base e le linee guida per la pianificazione.

Il Mediation Server converte la segnalazione e, in alcune configurazioni, i supporti tra il Lync Server 2013, l'infrastruttura VoIP aziendale e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol). Sul fianco di Lync Server 2013, Mediation Server è in attesa su un singolo indirizzo di trasporto Mutual TLS (MTLS). Sul lato del gateway, Mediation Server si pone in attesa su tutte le porte di attesa associate ai trunk definiti nel documento della topologia. Tutti i gateway qualificati devono supportare TLS, ma possono abilitare anche TCP. TCP è supportato per i gateway che non supportano TLS.

Se nel proprio ambiente è presente anche un PBX (Public Branch Exchange), Mediation Server gestisce le chiamate tra gli utenti di VoIP aziendale e il sistema PBX. Se il sistema PBX è un IP-PBX, è possibile creare una connessione SIP diretta tra il PBX e il Mediation Server. Se il PBX è un PBX TDM (Time Division Multiplex), è necessario distribuire anche un gateway PSTN tra Mediation Server e il sistema PBX.

Il Mediation Server è collocato con il front end server per impostazione predefinita. Il Mediation Server può anche essere distribuito in un pool autonomo per motivi di prestazioni oppure se si distribuisce il trunking SIP, nel qual caso è consigliabile utilizzare il pool autonomo.

Se si distribuiscono connessioni SIP dirette a un gateway PSTN qualificato che supporta il bypass multimediale e il bilanciamento del carico DNS, non è necessario disporre di un pool Mediation Server autonomo. Ciò è dovuto al fatto che i gateway qualificati possono effettuare il bilanciamento del carico DNS in un pool di Mediation Server e ricevere traffico da qualsiasi Mediation Server di un pool.

È inoltre consigliabile collocare il Mediation Server in un pool Front End se sono stati distribuiti sistemi IP-PBX o si effettua la connessione al Session Border Controller (SBC) di un provider di servizi di telefonia Internet, purché vengano soddisfatte una o più delle condizioni seguenti:

  - Il sistema IP-PBX o SBC è configurato per la ricezione di traffico da qualsiasi server Mediation Server nel pool e può eseguire il routing del traffico in modo uniforme a tutti i server Mediation Server nel pool.

  - Il sistema IP-PBX non supporta il bypass multimediale, ma il pool Front end che ospita il Mediation Server è in grado di gestire la transcodifica vocale per le chiamate a cui non si applica il bypass multimediale.

È possibile utilizzare Microsoft Lync Server 2013, strumento di pianificazione per valutare se il pool Front end in cui si desidera collocare il Mediation Server è in grado di gestire il carico. Se l'ambiente non soddisfa questi requisiti, è necessario distribuire un pool di Mediation Server autonomo.

Di seguito sono riportate le funzioni principali del Mediation Server:

  - Crittografia e decrittografia di SRTP sul server di Lync

  - Conversione di SIP su TCP (per i gateway che non supportano TLS) in SIP su Mutual TLS

  - Conversione di flussi multimediali tra Lync Server e il peer gateway del Mediation Server

  - Connessione di client esterni alla rete a componenti ICE interni per consentire l'attraversamento multimediale di NAT e firewall

  - Fungere da intermediario per i flussi di chiamata che un gateway non supporta, ad esempio le chiamate provenienti da utenti remoti su un client VoIP aziendale

  - Utilizzo del provider di servizi trunking SIP, nelle distribuzioni che includono il trunking SIP, per fornire il supporto PSTN eliminando la necessità di un gateway PSTN

Nella figura seguente vengono illustrati i protocolli di segnalazione e multimediali utilizzati dal Mediation Server per la comunicazione con un gateway PSTN di base e l'infrastruttura VoIP aziendale.

**Protocolli di segnalazione e multimediali utilizzati dal Mediation Server**

![Diagramma protocolli Mediation Server](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramma protocolli Mediation Server")

<div>


> [!NOTE]  
> Se si utilizza TCP o RTP/RTCP (invece di SRTP o SRTCP) sulla rete tra il gateway PSTN e il Mediation Server, è consigliabile adottare misure per garantire la sicurezza e la privacy della rete.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Trunk M:N in Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Controllo di ammissione di chiamata e Mediation Server in Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Enhanced 9-1-1 (E9-1-1) e Mediation Server in Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Bypass multimediale e Mediation Server in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Componenti e topologie per Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Linee guida per la distribuzione di Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

