---
title: "Lync Server 2013: installazione di un certificato in un nodo Watcher situato all'esterno della rete perimetrale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1479ffdd7f6652b96f3015e047194d76bf1e8978
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Installazione di un certificato in un nodo Watcher situato all'esterno della rete perimetrale di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Gli agenti di System Center Operations Manager eseguiti in una rete perimetrale, ad esempio un server Edge Lync Server, all'esterno dell'organizzazione, ad esempio un nodo di Watcher delle transazioni sintetiche esterne o in un limite di attendibilità dei servizi di dominio Active Directory, potrebbero richiedere la configurazione di un server gateway di System Center Operations Manager. Questo ruolo del server consente agli agenti che non hanno una relazione di trust con il server di gestione radice di generare avvisi. Per informazioni dettagliate, vedere "gestione dei server gateway in Operations Manager 2007" nella raccolta TechNet di System Center Operations [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)Manager.

Se si distribuisce un agente in una di queste posizioni, sarà anche necessario richiedere e configurare un certificato che consenta al nodo Watcher di inviare avvisi a System Center Operations Manager. Per semplificare questo processo, il team di Operations Manager ha creato un set di utilità che consentono di richiedere e installare il tipo corretto di certificato nel computer del nodo Watcher. Per informazioni dettagliate e per scaricare queste utilità, vedere l'articolo su [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)Blog "ottenere i certificati per gli agenti non appartenenti a un dominio con la creazione guidata di certificati".

</div>

<span> </span>

</div>

</div>

</div>

