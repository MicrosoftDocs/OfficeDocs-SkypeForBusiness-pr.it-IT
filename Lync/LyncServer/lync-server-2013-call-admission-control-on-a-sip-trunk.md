---
title: 'Lync Server 2013: Controllo di ammissione di chiamata in un trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36734aa67e350b6c6f5ea5e9da57ce47f57e3d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Controllo di ammissione di chiamata in un trunk SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-22_

Per distribuire il controllo di ammissione di chiamata (CAC) in un trunk SIP, è possibile creare un sito di rete per rappresentare il provider del servizio di telefonia Internet (ITSP). Per applicare i valori dei criteri di larghezza di banda nel trunk SIP, è possibile creare un criterio tra siti tra il sito di rete dell'organizzazione e il sito di rete creato per rappresentare il ITSP.

La figura seguente mostra un esempio di distribuzione di CAC in un trunk SIP.

**Configurazione di CAC in un trunk SIP**

![Controllo dell'ammissione alle chiamate schema del trunking SIP](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "controllo di ammissione di chiamata")

Per configurare CAC in un trunk SIP, sarà necessario eseguire le attività seguenti durante la distribuzione di CAC:

1.  Creare un sito di rete per rappresentare il ITSP. Associa il sito di rete a un'area di rete appropriata e assegna la larghezza di banda pari a zero per l'audio e il video per questo sito di rete. Per informazioni dettagliate, vedere [configurare i siti di rete per CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) nella documentazione relativa alla distribuzione.
    
    <div>
    

    > [!NOTE]  
    > Per ITSP, questa configurazione del sito di rete non è funzionale. I valori dei criteri di larghezza di banda vengono effettivamente applicati nel passaggio 2.

    
    </div>

2.  Creare un collegamento tra siti per il trunk SIP usando i valori di parametro rilevanti per il sito creato nel passaggio 1. Ad esempio, usa il nome del sito di rete nell'organizzazione come valore del parametro NetworkSiteID1 e il sito di rete ITSP come valore del parametro NetworkSiteID2. Per informazioni dettagliate, vedere [creare criteri di intersito di rete in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) nella documentazione relativa alla distribuzione. Vedere anche la documentazione di Lync Server Management Shell per il cmdlet New-CsNetworkInterSitePolicy.

3.  Ottenere l'indirizzo IP del punto di terminazione multimediale della sessione (SCB) del controller di bordo del ITSP. Aggiungere l'indirizzo IP con una subnet mask di 32 al sito di rete che rappresenta il ITSP. Per informazioni dettagliate, vedere [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

</div>

<span> </span>

</div>

</div>

</div>

