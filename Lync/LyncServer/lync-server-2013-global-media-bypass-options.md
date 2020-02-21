---
title: 'Lync Server 2013: opzioni di bypass multimediale globale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96c97301221e50873ab53dc06452721c74ed6627
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Opzioni di bypass multimediale globale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

<div>


> [!NOTE]  
> In questo argomento si presuppone che sia già stato configurato il bypass multimediale per qualsiasi trunk a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un session border controller (SBC) presso un provider di servizi di telefonia Internet) per un sito o un servizio specifico per in cui si desidera che il supporto per il Mediation Server venga ignorato.



</div>

Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, è necessario abilitarlo globalmente. Le impostazioni globali di bypass multimediale possono specificare che il bypass multimediale viene sempre tentato per le chiamate alla rete PSTN oppure che il bypass multimediale viene utilizzato utilizzando il mapping delle subnet ai siti di rete e alle aree di rete, analogamente a quanto avviene tramite il controllo di ammissione di chiamata, un altro funzionalità vocale avanzata. Quando il bypass multimediale e il controllo di ammissione di chiamata sono entrambi abilitati, vengono utilizzate automaticamente le informazioni relative all'area di rete, al sito di rete e alla subnet specificate per il controllo di ammissione di chiamata quando si determina se utilizzare il bypass multimediale. Ciò significa che non è possibile specificare che il bypass multimediale venga sempre tentato per le chiamate alla rete PSTN quando è abilitato il controllo di ammissione di chiamata.

In questo argomento viene descritto come utilizzare il pannello di controllo di Lync Server e Lync Server Management Shell insieme per configurare le impostazioni di bypass multimediale globale.

<div>


> [!NOTE]  
> Quando si utilizzano queste procedure per configurare il bypass multimediale, si presuppone che si disponga di una buona connettività tra i client e il peer Mediation Server, ad esempio un gateway PSTN, un sistema IP-PBX o un SBC (Session Border Controller) in un provider di trunking SIP. Se sono previsti limiti di larghezza di banda sul collegamento, non è possibile applicare il bypass multimediale alla chiamata. Il bypass multimediale non funziona con tutti i gateway PSTN, i sistemi IP-PBX e i Session Border Controller. Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco. Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>at.



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Passaggi successivi: scegliere le impostazioni di bypass multimediale globali

Dopo aver abilitato il bypass multimediale sulle connessioni trunk a un peer per siti o servizi specifici, utilizzare il contenuto indicato di seguito per eseguire una delle operazioni seguenti:

  - Abilitare il bypass multimediale sempre, come descritto in [Configure Media Bypass in Lync server 2013 per ignorare sempre il](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)Mediation Server.

  - In alternativa, configurare il bypass multimediale per l'utilizzo delle informazioni sui siti e sulle aree geografiche, come descritto in [Configure Media Bypass Global Settings in Lync Server 2013 per l'utilizzo di informazioni sul sito e sulla regione](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare un trunk con bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Configurare il bypass multimediale in Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Bypass multimediale e Mediation Server in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

