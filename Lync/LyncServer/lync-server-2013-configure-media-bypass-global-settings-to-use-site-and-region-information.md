---
title: Configurare le impostazioni globali di bypass multimediale per l'utilizzo delle informazioni sul sito e sulla regione
description: Configurare le impostazioni globali di bypass multimediale per l'utilizzo delle informazioni sul sito e sulla regione.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a65dcec966030262d6d0fb5530b94f2411003c7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559802"
---
# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'utilizzo delle informazioni sui siti e sulle aree geografiche

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

<div>


> [!NOTE]
> In questo argomento si presuppone che il bypass multimediale (Media Bypass) sia già stato configurato per qualsiasi connessione trunk dal Mediation Server a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un Session Border Controller (SBC) presso un provider di servizi di telefonia Internet o ITSP) per un sito o un servizio specifico per il quale si desidera ignorare il Mediation Server.<BR>In questo argomento si presuppone inoltre che siano stati definiti tutti i siti centrali e i siti di succursale in Generatore di topologie in modo che corrispondano all'area di rete, al sito di rete e alla configurazione della subnet eseguite seguendo i passaggi descritti in <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>e <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un 2013 sito</A> Se non corrispondono, il bypass multimediale avrà esito negativo.



</div>

Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, è necessario configurare le impostazioni globali. Se si utilizza la procedura illustrata in questo argomento per configurare le impostazioni globali per il bypass multimediale, il presupposto è che una o entrambe le situazioni seguenti incidano sulla configurazione:

  - *Non* si dispone di una buona connettività tra gli endpoint di Lync Server e tutti i peer per cui è stato configurato il bypass multimediale sulla connessione trunk.

  - Il controllo di ammissione di chiamata per la gestione della larghezza di banda è abilitato.
    
    <div>
    

    > [!NOTE]
    > Per informazioni dettagliate sulle considerazioni sia per il controllo di ammissione di chiamata che per il bypass multimediale, vedere la sezione "controllo di ammissione di chiamata per le connessioni PSTN" in <A href="lync-server-2013-media-bypass-and-mediation-server.md">media bypass e Mediation Server in Lync server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

Le informazioni relative alle aree di rete e ai siti di rete vengono condivise tra le caratteristiche di VoIP aziendale avanzate del controllo di ammissione di chiamata e del bypass multimediale, quando entrambi sono abilitati. Se il controllo di ammissione di chiamata è già configurato, non sarà pertanto necessario eseguire la procedura seguente per modificare le informazioni sui siti e sulle aree in modo specifico per il bypass multimediale. Eseguire questa procedura se le aree e i siti di rete non sono stati ancora configurati per il controllo di ammissione di chiamata e si desidera modificare le impostazioni per il bypass multimediale.

In alternativa, eseguire questa procedura se si desidera utilizzare le informazioni sui siti e sulle aree per prendere una decisione relativa al bypass, ma non si ha alcuna intenzione di abilitare il controllo di ammissione di chiamata. In tal caso, i collegamenti con restrizioni di larghezza di banda dovranno comunque essere rappresentati tramite criteri intersito di rete, come descritto in [creare criteri intersito di rete in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). Gli effettivi vincoli di larghezza di banda in questa circostanza sono meno importanti perché il controllo di ammissione di chiamata non è stato abilitato. Questi collegamenti vengono invece utilizzati per suddividere le subnet in modo da specificare quelle senza limiti di larghezza di banda e che possono quindi utilizzare il bypass multimediale. Ciò si verifica anche quando il controllo di ammissione di chiamata e il bypass multimediale sono entrambi abilitati.

Inoltre, affinché il bypass funzioni correttamente, è necessario che esista una coerenza tra un sito come definito in Generatore di topologie e come viene definito quando si configurano le aree di rete e i siti di rete. Ad esempio, se si dispone di un sito di succursale definito in Generatore di topologie per la distribuzione di un solo gateway PSTN, il sito di succursale deve essere configurato con un criterio VoIP aziendale che consenta agli utenti di siti di succursale di fare in modo che le chiamate PSTN vengano instradate attraverso il gateway PSTN nel sito di succursale.

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>Per configurare le informazioni relative ai siti e alle aree per il bypass multimediale

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.

3.  Fare doppio clic sulla configurazione **Globale** nella tabella.

4.  Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.

5.  Fare clic su **Utilizza configurazione siti e aree**.

6.  Se necessario, selezionare la casella di controllo **Abilita bypass per siti non mappati**.
    
    <div>
    

    > [!NOTE]
    > Selezionare questa casella di controllo solo se alla stessa area sono associati uno o più siti di grandi dimensioni senza vincoli di larghezza di banda, ad esempio un grande sito centrale, ma anche siti di succursale con vincoli di larghezza di banda. Quando si abilita il bypass per i siti non mappati, la configurazione viene snellita perché è necessario specificare esclusivamente le subnet associate ai siti di succursale anziché tutte le subnet associate a tutti i siti. È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato.

    
    </div>

7.  Fare clic su **Commit**.

Successivamente, aggiungere le subnet al sito di rete, come descritto in [associare subnet a siti di rete per il bypass multimediale in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md). Le procedure effettive per l'associazione di subnet a siti di rete sono descritte in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md). Dopo aver associato tutte le subnet a siti di rete, la distribuzione di bypass multimediale è stata completata.

<div>


> [!IMPORTANT]
> Se non sono stati ancora creati i siti e le aree di rete, è necessario crearli prima di poter proseguire con la distribuzione del bypass multimediale. Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync server 2013</A> e <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.



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

