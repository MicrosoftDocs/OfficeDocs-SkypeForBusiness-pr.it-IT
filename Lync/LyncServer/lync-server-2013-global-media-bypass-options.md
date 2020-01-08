---
title: 'Lync Server 2013: opzioni di bypass multimediale globale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Opzioni di bypass multimediale globale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

<div>


> [!NOTE]  
> Questo argomento presuppone che sia già stato configurato il bypass multimediale per i Trunks in un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un session border controller (SBC) presso un provider di servizi di telefonia Internet) per un sito o un servizio specifico per cui si vuole che l'elemento multimediale ignori il Mediation Server.



</div>

Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, devi anche abilitare il bypass multimediale a livello globale. Le impostazioni di bypass multimediale globale possono specificare che il bypass multimediale viene sempre tentato per le chiamate alla rete PSTN o che il bypass multimediale viene usato usando il mapping delle subnet ai siti di rete e alle aree di rete, in modo simile a quanto avviene tramite il controllo di ammissione delle chiamate, un altro funzionalità vocale avanzata. Quando il bypass multimediale e il controllo dell'ammissione alle chiamate sono entrambi abilitati, viene usata automaticamente l'area di rete, il sito di rete e le informazioni di subnet specificate per il controllo di ammissione di chiamata per determinare se usare il bypass multimediale. Ciò significa che non è possibile specificare che il bypass multimediale venga sempre tentato per le chiamate al PSTN quando il controllo di ammissione delle chiamate è abilitato.

Questo argomento descrive come usare il pannello di controllo di Lync Server e Lync Server Management Shell insieme per configurare le impostazioni di bypass multimediale globale.

<div>


> [!NOTE]  
> Quando si usano questi passaggi per configurare il bypass multimediale, si presume che si disponga di una buona connettività tra i client e il peer Mediation Server, ad esempio un gateway PSTN, un IP-PBX o un SBC presso un provider di trunking SIP. Se sono presenti limitazioni della larghezza di banda per il collegamento, non è possibile applicare l'esclusione multimediale alla chiamata. Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC. Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>at.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Passaggi successivi: scegliere le impostazioni di bypass multimediale globale

Dopo aver abilitato il bypass multimediale in tutte le connessioni trunk a un peer per siti o servizi specifici, usare il contenuto seguente per eseguire una delle operazioni seguenti:

  - Abilita sempre il bypass multimediale, come descritto in [configurare il bypass multimediale in Lync Server 2013 per aggirare sempre il server Mediation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - In alternativa, configurare il bypass multimediale per l'uso delle informazioni sul sito e sulle aree geografiche, come descritto in [configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'uso delle informazioni sul sito e sull'area](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk con il bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Configurare il bypass multimediale in Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Bypass multimediale e Mediation Server in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

