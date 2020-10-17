---
title: 'Lync Server 2013: componenti di connettività PSTN'
description: 'Lync Server 2013: componenti di connettività PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2ae5a6a7bc5db1cd7a23c44719d7123a624317d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565682"
---
# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Componenti di connettività PSTN in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Una soluzione VoIP di livello aziendale deve essere in grado di garantire le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun decadimento della qualità del servizio (QoS). Gli utenti non devono inoltre preoccuparsi della tecnologia sottostante quando effettuano e ricevono chiamate. Dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN deve risultare del tutto analoga a qualsiasi altra sessione SIP.

Per le connessioni PSTN, è possibile distribuire un trunk SIP o un gateway PSTN (con un sistema PBX, noto anche come collegamento SIP diretto o senza PBX).

<div>

## <a name="sip-trunking"></a>Trunking SIP

Come alternativa all'utilizzo di gateway PSTN, è possibile connettere la soluzione VoIP aziendale alla rete PSTN tramite trunking SIP. Il trunking SIP consente gli scenari seguenti:

  - Un utente aziendale interno o esterno al firewall aziendale può effettuare una chiamata locale o interurbana tramite un numero compatibile con E.164, che viene terminata nella rete PSTN come servizio del provider di servizi corrispondente.

  - Qualsiasi sottoscrittore PSTN può contattare un utente aziendale interno o esterno al firewall aziendale componendo un numero DID (Direct Inward Dialing) associato a tale utente.

Per l'utilizzo di questa soluzione di distribuzione è necessario un provider di servizi di trunking SIP.

</div>

<div>

## <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN sono dispositivi di terze parti che convertono i segnali e i contenuti multimediali tra l'infrastruttura VoIP aziendale e una rete PSTN o un PBX. I gateway PSTN operano con Mediation Server per presentare una chiamata PSTN o PBX a un client VoIP aziendale. Mediation Server presenta inoltre le chiamate da client VoIP aziendale al gateway PSTN per il routing alla rete PSTN o al PBX. Per un elenco dei partner che collaborano con Microsoft per fornire dispositivi che funzionano con Lync Server, vedere il sito Web Microsoft Unified Communications Partners all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

</div>

<div>

## <a name="private-branch-exchanges"></a>Centralini

Se si dispone di un'infrastruttura vocale esistente che utilizza un sistema PBX (Private Branch Exchange), è possibile utilizzare il PBX con Lync Server VoIP aziendale.

Gli scenari di integrazione tra VoIP aziendale e PBX supportati sono i seguenti:

  - IP-PBX che supporta Media Bypass, con un server Mediation Server.

  - IP-PBX che richiede un gateway PSTN autonomo.

  - PBX TDM (Time Division Multiplexing), con un gateway PSTN autonomo.

<div>


> [!NOTE]  
> Media Bypass non funziona con tutti i gateway PSTN, i sistemi IP-PBX e i servizi SBC. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

Per informazioni dettagliate sui partner che offrono soluzioni VoIP aziendale, vedere il sito Web Microsoft Unified Communications Partners all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

Per informazioni dettagliate sui partner che offrono soluzioni hardware VoIP aziendale, tra cui i gateway PSTN, vedere il sito Web Microsoft Unified Communications Partners [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

