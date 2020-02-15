---
title: 'Lync Server 2013: controllo di ammissione di chiamata in un trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ae55f6146e59931b55ec384d374ea837eeb598c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Controllo di ammissione di chiamata in un trunk SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-22_

Per distribuire il servizio Controllo di ammissione di chiamata in un trunk SIP, creare un sito di rete per rappresentare il provider di servizi di telefonia Internet (ITSP). Per applicare i valori dei criteri di larghezza di banda nel trunk SIP, creare criteri tra siti tra il sito di rete dell'organizzazione e il sito di rete creato per rappresentare l'ITSP.

Nella figura seguente è illustrato un esempio di distribuzione del servizio Controllo di ammissione di chiamata in un trunk SIP.

**Configurazione del servizio Controllo di ammissione di chiamata in un trunk SIP**

![Diagramma del trunking SIP del controllo di ammissione di chiamata](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagramma del trunking SIP del controllo di ammissione di chiamata")

Per configurare il servizio Controllo di ammissione di chiamata in un trunk SIP, è necessario eseguire le operazioni seguenti durante la distribuzione del servizio:

1.  Creare un sito di rete per rappresentare l'ITSP. Associare il sito di rete a un'area di rete appropriata e allocare una larghezza di banda pari a zero per audio e video per il sito di rete. Per ulteriori informazioni, vedere [Configure Network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) nella documentazione relativa alla distribuzione.
    
    <div>
    

    > [!NOTE]  
    > Per l'ITSP, questa configurazione del sito di rete non è funzionale. I valori dei criteri di larghezza di banda vengono effettivamente applicati nel passaggio 2.

    
    </div>

2.  Creare un collegamento tra siti per il trunk SIP utilizzando i valori dei parametri rilevanti per il sito creato nel passaggio 1. Utilizzare, ad esempio, il nome del sito di rete dell'organizzazione come valore del parametro NetworkSiteID1 e il sito di rete dell'ITSP come valore del parametro NetworkSiteID2. Per informazioni dettagliate, vedere [create Network intersite Policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) nella documentazione relativa alla distribuzione. Vedere anche la documentazione di Lync Server Management Shell per il cmdlet New-CsNetworkInterSitePolicy.

3.  Ottenere l'indirizzo IP del punto di terminazione multimediale SBC (Session Border Controller) dall'ITSP. Aggiungere tale indirizzo IP con una subnet mask di 32 al sito di rete che rappresenta l'ITSP. Per ulteriori informazioni, vedere [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

</div>

<span> </span>

</div>

</div>

</div>

