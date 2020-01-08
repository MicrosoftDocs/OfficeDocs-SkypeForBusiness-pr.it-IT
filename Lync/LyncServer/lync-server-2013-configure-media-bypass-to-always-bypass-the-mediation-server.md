---
title: 'Lync Server 2013: configurare il bypass multimediale per ignorare sempre il Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aca094110036692c5ac5327b166a3f81e4b769f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configurare il bypass multimediale in Lync Server 2013 per ignorare sempre il Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-25_

<div>


> [!NOTE]  
> Questo argomento presuppone che sia già stato configurato il bypass multimediale per tutte le connessioni trunk a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un SBC (Session Border Controller) presso un provider di servizi di telefonia Internet (ITSP)) per uno specifico sito o servizio per cui si vuole che l'elemento multimediale ignori il Mediation Server.<BR>Non è possibile configurare l'elemento multimediale per evitare sempre il Mediation Server, ma anche per abilitare il controllo di ammissione delle chiamate. Queste impostazioni sono incompatibili e quindi sono impostazioni mutuamente esclusive nell'interfaccia utente del pannello di controllo di Lync Server.



</div>

Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer al Mediation Server, è anche necessario configurare le impostazioni globali per il bypass multimediale. Se si usano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presume che si disponga di una buona connettività tra endpoint Lync e qualsiasi peer per cui è stato configurato il bypass multimediale nella connessione trunk.

Se non si dispone di una buona connettività tra endpoint di Lync Server e tutti i peer al Mediation Server di cui sono state abilitate le rispettive connessioni trunk per il bypass multimediale, è necessario configurare le impostazioni di bypass multimediale globale per usare le informazioni sul sito e le aree geografiche quando utilizzo del bypass multimediale. In questo modo è possibile determinare un maggiore controllo quando l'elemento multimediale ignora il Mediation Server. A questo scopo, eseguire la procedura descritta in [configurare le impostazioni globali di bypass multimediale in Lync server 2013 per usare le informazioni sul sito e le aree](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) geografiche e [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) .

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Per abilitare il bypass multimediale a livello globale per ignorare sempre il Mediation Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare doppio clic sulla configurazione **globale** nell'elenco.

4.  Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita esclusione multimediale** .

5.  Fare clic su **Ignora sempre**.

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare il bypass multimediale in Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opzioni di bypass multimediale globale in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Bypass multimediale e Mediation Server in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Pianificazione del bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

