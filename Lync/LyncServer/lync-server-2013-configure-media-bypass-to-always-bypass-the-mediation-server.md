---
title: 'Lync Server 2013: configurare il bypass multimediale per ignorare sempre il Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76cf44ee24c94b4a243fe84db1f3bbf7a28ba2e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configurare il bypass multimediale in Lync Server 2013 per ignorare sempre il Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-25_

<div>


> [!NOTE]  
> In questo argomento si presuppone che la funzionalità di bypass multimediale sia già stata configurata per qualsiasi connessione trunk a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso un provider di servizi di telefonia Internet ITSP) per un sito o un servizio specifico per il quale si vuole ignorare il Mediation Server.<BR>Non è possibile configurare il contenuto multimediale in modo da ignorare sempre il Mediation Server e abilitare contemporaneamente il servizio Controllo di ammissione di chiamata. Queste impostazioni sono incompatibili e sono quindi impostazioni mutuamente esclusive nell'interfaccia utente del pannello di controllo di Lync Server.



</div>

Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer del Mediation Server, è inoltre necessario configurare le impostazioni globali per il bypass multimediale. Se si utilizzano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presuppone che si disponga di una buona connettività tra gli endpoint di Lync e qualsiasi peer per il quale è stato configurato il bypass multimediale sulla connessione trunk.

Se non si dispone di una buona connettività tra gli endpoint di Lync Server e tutti i peer al Mediation Server di cui sono state abilitate le rispettive connessioni trunk per il bypass multimediale, è necessario configurare le impostazioni globali di bypass multimediale per l'utilizzo delle informazioni relative a siti e aree geografiche quando utilizzo del bypass multimediale. Ciò consente di specificare in modo più preciso quando il contenuto multimediale deve ignorare il Mediation Server. A tale scopo, eseguire la procedura descritta in [Configure Media Bypass Global Settings in Lync server 2013 per utilizzare le informazioni sui siti e le aree](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) geografiche e [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) .

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Per abilitare il bypass multimediale globalmente in modo che il Mediation Server venga ignorato sempre

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.

3.  Fare doppio clic sulla configurazione **Globale** nell'elenco.

4.  Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.

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

