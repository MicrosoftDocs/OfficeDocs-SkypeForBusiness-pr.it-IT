---
title: Configurare le impostazioni globali di bypass multimediale per usare le informazioni sul sito e sull'area geografica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'uso delle informazioni sul sito e sull'area geografica

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

<div>


> [!NOTE]
> Questo argomento presuppone che sia già stato configurato il bypass multimediale per eventuali connessioni trunk da Mediation Server a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un SBC (Session Border Controller) in un servizio di telefonia Internet Provider (ITSP) per un sito o un servizio specifico per cui si vuole che l'elemento multimediale ignori il Mediation Server.<BR>Questo argomento presuppone inoltre che siano stati definiti tutti i siti centrali e i siti di succursale in Generatore di topologia in modo che corrispondano alla configurazione dell'area di rete, del sito di rete e della subnet eseguita in base alla procedura descritta in <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>e <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un sito 2013 di</A> Se non corrispondono, il bypass multimediale non riuscirà.



</div>

Oltre a abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, è anche necessario configurare le impostazioni globali. Se si usano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, il presupposto è che una o entrambe le situazioni seguenti influiscono sulla configurazione:

  - *Non* si dispone di una buona connettività tra endpoint di Lync Server e qualsiasi peer per cui è stato configurato il bypass multimediale nella connessione trunk.

  - Il controllo di ammissione di chiamata (CAC) per la gestione della larghezza di banda è abilitato.
    
    <div>
    

    > [!NOTE]
    > Per informazioni dettagliate sulle considerazioni sia per il controllo dell'ammissione delle chiamate che per il bypass multimediale, vedere la sezione "controllo ammissione chiamata delle connessioni PSTN" in <A href="lync-server-2013-media-bypass-and-mediation-server.md">media bypass e Mediation Server in Lync server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

Le informazioni relative all'area geografica e al sito di rete sono condivise tra il controllo di ammissione delle chiamate e l'esclusione delle funzionalità vocali avanzate dell'organizzazione. Pertanto, se è già stato configurato il controllo di ammissione delle chiamate, non è necessario usare la procedura seguente per modificare le informazioni relative al sito e alla regione in modo specifico per il bypass multimediale. Seguire i passaggi descritti in questa procedura se non sono ancora state configurate le aree geografiche e i siti di rete per il controllo dell'ammissione alle chiamate e si vogliono modificare le impostazioni di bypass multimediale.

In alternativa, seguire questa procedura se si vuole usare le informazioni sul sito e le aree geografiche in esecuzione della decisione di esclusione, ma non si ha intenzione di abilitare il controllo di ammissione alle chiamate. In questo caso, i collegamenti con restrizioni di larghezza di banda dovranno essere rappresentati anche tramite criteri intersito di rete, come descritto in [creare criteri intersito di rete in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). I vincoli di larghezza di banda effettivi non sono importanti in questo caso, perché il controllo di ammissione delle chiamate non è stato abilitato. Questi collegamenti vengono invece usati per partizionare subnet per specificare quelli che non hanno limiti di larghezza di banda e quindi possono usare il bypass multimediale. Tieni presente che questo è vero anche quando il controllo di ammissione delle chiamate e il bypass multimediale sono entrambi abilitati.

Inoltre, perché il bypass funzioni correttamente, è necessario che la coerenza tra un sito sia definito in Generatore di topologie e che venga definita quando si configurano le aree di rete e i siti di rete. Ad esempio, se si ha un sito di succursale definito in Generatore di topologia con un solo gateway PSTN distribuito, il sito di filiale deve essere configurato con un criterio VoIP aziendale che consente agli utenti del sito succursale di avere le chiamate PSTN instradate attraverso la rete PSTN Gateway nel sito della filiale.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>Per configurare le informazioni sul sito e sulle aree geografiche per il bypass multimediale

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare doppio clic sulla configurazione **globale** nella tabella.

4.  Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita esclusione multimediale** .

5.  Fare clic su **Usa configurazione siti e aree**geografiche.

6.  Se necessario, selezionare la casella **di controllo Abilita bypass per i siti non mappati** .
    
    <div>
    

    > [!NOTE]
    > Selezionare questa casella di controllo solo se si hanno uno o più siti di grandi dimensioni associati alla stessa area geografica che non hanno vincoli di larghezza di banda, ad esempio un sito centrale di grandi dimensioni, ma si hanno anche alcuni siti di succursale associati alla stessa area geografica con larghezza di banda vincoli. Quando si Abilita l'esclusione per i siti non mappati, la configurazione viene semplificata in quanto si specificano solo le subnet associate ai siti di succursale, invece di specificare tutte le subnet associate a tutti i siti. È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato.

    
    </div>

7.  Fare clic su **Commit**.

Aggiungere quindi le subnet al sito di rete, come descritto in [associare subnet ai siti di rete per il bypass multimediale in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). Le procedure effettive per l'associazione di subnet con i siti di rete sono descritte in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md). Dopo aver associato tutte le subnet con i siti di rete, la distribuzione di bypass multimediale è completa.

<div>


> [!IMPORTANT]
> Se non sono già state create aree di rete e siti di rete, è necessario prima di tutto crearle prima di procedere con la distribuzione di bypass multimediale. Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync server 2013</A> e <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Associare subnet a siti di rete per il bypass multimediale in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

