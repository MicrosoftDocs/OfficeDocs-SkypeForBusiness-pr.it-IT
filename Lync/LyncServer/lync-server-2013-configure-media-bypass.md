---
title: 'Lync Server 2013: configurare il bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fe9bb93ad32c0871dd51d3818d2ca788327dc5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>Configurare il bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

In questa sezione si presuppone che sia stato già pubblicato e configurato almeno uno o più Mediation Server, come descritto in [define a Mediation Server in Generatore di topologie in Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) e [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md)oppure in [define and Configure a front end pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) e [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md), rispettivamente, tutti nella documentazione relativa alla

In questa sezione si presuppone inoltre che sia stato definito almeno un peer gateway per fornire la connettività PSTN, come descritto in [define a gateway in Generatore di topologie in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Se il peer a cui ci si connette è l'SBC di un provider di trunking SIP, assicurarsi che il provider sia un provider qualificato e che il provider supporti il bypass multimediale. Ad esempio, molti provider di trunking SIP consentiranno solo a SBC di ricevere traffico dal Mediation Server. In caso affermativo, non è necessario abilitare il bypass per il trunk in questione. Inoltre, non è possibile abilitare il bypass multimediale, a meno che l'organizzazione non riveli gli indirizzi IP della rete interna al provider di trunking SIP.

<div>


> [!NOTE]  
> Il bypass multimediale non interagisce con ogni gateway PSTN, ogni IP-PBX e ogni SBC. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>at.



</div>

In questa sezione viene descritto come abilitare il bypass multimediale per ridurre l'elaborazione necessaria del Mediation Server. Prima di abilitare il bypass multimediale, verificare che l'ambiente soddisfi le condizioni necessarie per il supporto del bypass multimediale, come descritto in [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella documentazione relativa alla pianificazione. Assicurarsi inoltre di utilizzare le informazioni in [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) per decidere se abilitare le impostazioni globali di bypass multimediale per ignorare sempre il Mediation Server o per utilizzare le informazioni sul sito e le aree geografiche quando si determina se ignorare il Mediation Server.

Se è già stato configurato facoltativamente il controllo di ammissione di chiamata (CAC), un'altra funzionalità di VoIP aziendale avanzata, si noti che la prenotazione di larghezza di banda eseguita dal controllo di ammissione di chiamata non è applicabile alle chiamate per le quali viene utilizzato il bypass multimediale. La verifica dell'utilizzo del bypass multimediale viene eseguita per prima e, se il bypass multimediale è occupato, il controllo di ammissione di chiamata non viene utilizzato per la chiamata. solo se il controllo bypass multimediale ha esito negativo è la verifica eseguita per il controllo di ammissione di chiamata. Le due caratteristiche sono quindi esclusive per una chiamata specifica instradata alla rete PSTN. Questa è la logica perché il bypass multimediale presuppone che non esistano vincoli di larghezza di banda tra gli endpoint multimediali di una chiamata. il bypass multimediale non può essere eseguito sui collegamenti con larghezza di banda limitata. Di conseguenza, una delle seguenti operazioni si applicherà a una chiamata PSTN: a) il contenuto multimediale ignora il Mediation Server e il controllo di ammissione di chiamata non riserva la larghezza di banda per la chiamata. o b) il controllo di ammissione di chiamata applica la prenotazione della larghezza di banda alla chiamata e il supporto viene elaborato dal Mediation Server coinvolto nella chiamata.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Passaggi successivi: abilitare il bypass multimediale sulla connessione trunk

Dopo aver configurato le impostazioni iniziali per la connettività PSTN (dial plan, criteri vocali, record di utilizzo PSTN, route di chiamata in uscita e regole di conversione), iniziare il processo di abilitazione del bypass multimediale tramite la procedura descritta in [Configure a Trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurare il bypass multimediale in Lync Server 2013 per ignorare sempre il Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'utilizzo delle informazioni sui siti e sulle aree geografiche](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

