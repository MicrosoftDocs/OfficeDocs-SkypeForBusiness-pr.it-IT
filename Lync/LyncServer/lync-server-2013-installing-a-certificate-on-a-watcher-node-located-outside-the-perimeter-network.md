---
title: "Lync Server 2013: installazione di un certificato in un nodo Watcher che si trova all'esterno della rete perimetrale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf4519995abf75db7807f8cd80f07ea477c8d4b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498553"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Installazione di un certificato in un nodo Watcher che si trova all'esterno della rete perimetrale di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Gli agenti di System Center Operations Manager in esecuzione in una rete perimetrale, ad esempio un server perimetrale di Lync Server, all'esterno dell'organizzazione (ad esempio un nodo Watcher esterno per le transazioni sintetiche) o in un limite di attendibilità dei servizi di dominio Active Directory, potrebbero richiedere la configurazione di un server Gateway System Center Operations Manager. Questo ruolo del server consente agli agenti che non dispongono di una relazione di trust con il server di gestione principale di emettere avvisi. Per informazioni dettagliate, vedere la sezione relativa alla gestione dei server gateway in Operations Manager 2007 nella libreria TechNet di System Center Operations Manager all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) .

Se si distribuisce un agente in una di queste posizioni, sarà inoltre necessario richiedere e configurare un certificato che consenta al nodo Watcher di inviare avvisi a System Center Operations Manager. Per semplificare questo processo, il team di Operations Manager ha creato un set di utilità che consente di richiedere e installare il tipo di certificato corretto nel computer del nodo di controllo. Per ulteriori informazioni e per scaricare queste utilità, vedere l'articolo su Blog "ottenere certificati per gli agenti non appartenenti a un dominio semplificato con la generazione guidata dei certificati" [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) .

</div>

<span> </span>

</div>

</div>

</div>

