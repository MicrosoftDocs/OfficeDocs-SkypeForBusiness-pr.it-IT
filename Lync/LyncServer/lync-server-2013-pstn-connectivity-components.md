---
title: 'Lync Server 2013: componenti di connettività PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecda38b4164a70cd4dbb21271ff6efedb08cd498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Componenti di connettività PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Una soluzione VoIP di livello aziendale deve prevedere le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun calo di qualità del servizio (QoS). Inoltre, gli utenti non devono essere consapevoli della tecnologia sottostante quando effettuano e ricevono chiamate. Dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN dovrebbe sembrare solo un'altra sessione SIP.

Per le connessioni PSTN, è possibile distribuire un trunk SIP o un gateway PSTN (con un PBX, noto anche come collegamento SIP diretto o senza PBX).

<div>

## <a name="sip-trunking"></a>Trunking SIP

In alternativa all'uso di gateway PSTN, è possibile connettere la soluzione VoIP aziendale alla rete PSTN usando il trunking SIP. Il trunking SIP consente gli scenari seguenti:

  - Un utente aziendale all'interno o all'esterno del firewall aziendale può effettuare una chiamata locale o interurbana specificata da un numero conforme E. 164 che viene terminato sulla rete PSTN come servizio del provider di servizi corrispondente.

  - Qualsiasi abbonato PSTN può contattare un utente aziendale all'interno o all'esterno del firewall aziendale componendo un numero DID (Direct inwarded Dialing) associato all'utente aziendale.

L'uso di questa soluzione di distribuzione richiede un provider di servizi di trunking SIP.

</div>

<div>

## <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN sono dispositivi di terze parti che traducono segnali e elementi multimediali tra l'infrastruttura VoIP aziendale e una rete PSTN o PBX. I gateway PSTN collaborano con il Mediation Server per presentare una chiamata PSTN o PBX a un client VoIP aziendale. Il Mediation Server presenta anche le chiamate dei client VoIP aziendale al gateway PSTN per il routing alla rete PSTN o PBX. Per un elenco dei partner che collaborano con Microsoft per la fornitura di dispositivi compatibili con Lync Server, vedere il sito Web Microsoft Unified Communications [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Partners.

</div>

<div>

## <a name="private-branch-exchanges"></a>Scambi di branch privati

Se si dispone di un'infrastruttura vocale esistente che usa un PBX (Private Branch Exchange), è possibile usare il PBX con Lync Server Enterprise Voice.

Gli scenari di integrazione Voice-PBX supportati di Enterprise sono i seguenti:

  - IP-PBX che supporta il bypass multimediale, con un Mediation Server.

  - IP-PBX che richiede un gateway PSTN autonomo.

  - PBX TDM (Time Division Multiplexing) con un gateway PSTN autonomo.

<div>


> [!NOTE]  
> Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>at.



</div>

Per informazioni dettagliate sui partner che offrono soluzioni VoIP aziendale, vedere il sito Web Microsoft Unified Communications Partners [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).

Per informazioni dettagliate sui partner che offrono soluzioni hardware VoIP aziendale, inclusi i gateway PSTN, vedere il sito Web [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Microsoft Unified Communications Partners.

</div>

</div>

<span> </span>

</div>

</div>

</div>

