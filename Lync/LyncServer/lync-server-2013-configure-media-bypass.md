---
title: 'Lync Server 2013: Configurare il bypass multimediale'
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
ms.openlocfilehash: 8be022e5b1b16bff432873e27ddda5f388db02f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>Configurare il bypass multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

In questa sezione si presuppone che sia già stato pubblicato e configurato almeno uno o più server di mediazione (come descritto in [definire un Mediation Server in Generatore di topologie in Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) e [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md)oppure in [definire e configurare un pool Front end o un server Standard Edition in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) e [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md), nella documentazione di distribuzione

Questa sezione presuppone inoltre che sia stato definito almeno un peer del gateway per specificare la connettività PSTN, come descritto in [definire un gateway in Generatore di topologia in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Se il peer a cui si connette è il SBC di un provider di trunking SIP, verificare che il provider sia un provider qualificato e che il provider supporti il bypass multimediale. Ad esempio, molti provider di trunking SIP consentiranno solo a SBC di ricevere il traffico dal Mediation Server. In caso affermativo, l'esclusione non deve essere abilitata per il trunk in questione. Non è inoltre possibile abilitare il bypass multimediale a meno che l'organizzazione non riveli gli indirizzi IP di rete interni al provider di trunking SIP.

<div>


> [!NOTE]  
> Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>at.



</div>

Questa sezione descrive come abilitare il bypass multimediale per ridurre l'elaborazione necessaria per il Mediation Server. Prima di abilitare il bypass multimediale, verificare che l'ambiente soddisfi le condizioni necessarie per supportare il bypass multimediale, come descritto in [pianificazione per il bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella documentazione relativa alla pianificazione. Verificare inoltre di aver usato le informazioni in [pianificazione per il bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) per decidere se abilitare le impostazioni globali di bypass multimediale per ignorare sempre il Mediation Server o per usare le informazioni sul sito e le aree geografiche per determinare se ignorare il Mediation Server.

Se è già stato configurato facoltativamente il controllo di ammissione alle chiamate (CAC), un'altra funzionalità di VoIP aziendale avanzata, si noti che la prenotazione di larghezza di banda eseguita tramite il controllo di ammissione delle chiamate non si applica alle chiamate per cui è impiegato il bypass multimediale. La verifica dell'uso del bypass multimediale viene eseguita per prima e, se il bypass multimediale viene impiegato, il controllo di ammissione delle chiamate non viene usato per la chiamata; solo se il controllo del bypass multimediale non riesce, viene eseguito il controllo per l'ammissione alla chiamata. Le due caratteristiche si escludono quindi a vicenda per qualsiasi chiamata specifica indirizzata alla rete PSTN. Questa è la logica perché il bypass multimediale presuppone che i vincoli di larghezza di banda non esistano tra gli endpoint multimediali di una chiamata; il bypass multimediale non può essere eseguito sui collegamenti con larghezza di banda limitata. Di conseguenza, una delle operazioni seguenti verrà applicata a una chiamata PSTN: a) l'elemento multimediale ignora il Mediation Server e il controllo di ammissione delle chiamate non riserva la larghezza di banda per la chiamata; o b) il controllo dell'ammissione alle chiamate applica la prenotazione della larghezza di banda alla chiamata e il supporto viene elaborato dal Mediation Server coinvolto nella chiamata.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Passaggi successivi: abilitare il bypass multimediale nella connessione trunk

Dopo aver configurato le impostazioni iniziali per la connettività PSTN (dial plan, criteri vocali, record di utilizzo PSTN, route di chiamata in uscita e regole di traduzione), avviare il processo di abilitazione del bypass multimediale tramite la procedura descritta in [configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configurare il bypass multimediale in Lync Server 2013 per ignorare sempre il Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'uso delle informazioni sul sito e sull'area geografica](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

