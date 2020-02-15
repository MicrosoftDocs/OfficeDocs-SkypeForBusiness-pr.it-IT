---
title: 'Lync Server 2013: richiedere i certificati per i componenti perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10e7a724edd6e68602e4655a783f953ad1e2bc2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Richiedere i certificati per i componenti perimetrali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

I certificati necessari per supportare l'accesso utente esterno includono i certificati emessi da un'Autorità di certificazione (CA) pubblica e i certificati emessi da un'autorità di certificazione globale (enterprise) interna:

  - I certificati necessari per l'interfaccia esterna del server perimetrale e il proxy inverso devono essere emessi da un'autorità di certificazione pubblica.

  - I certificati necessari per l'interfaccia interna possono essere emessi da una CA pubblica o da una CA enterprise interna. È consigliabile utilizzare un'autorità di certificazione interna di Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA o Windows Server 2012 R2 per la creazione di questi certificati per il salvataggio a scapito dell'utilizzo di certificati pubblici.

<div>


> [!IMPORTANT]  
> È possibile richiedere del tempo per elaborare le richieste di certificati, in particolare le richieste alle autorità di certificazione pubbliche, pertanto è necessario richiedere certificati per i server perimetrali in anticipo per garantire che siano disponibili quando si avvia la distribuzione dei componenti del server perimetrale. Per un riepilogo dei requisiti relativi ai certificati per i server perimetrali, vedere <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate Requirements for External User Access in Lync Server 2013</A>.



</div>

Anche se per il certificato del perimetro interno è possibile utilizzare un'autorità di certificazione (CA) pubblica, per ridurre al minimo i costi è consigliabile utilizzare una CA globale (enterprise). Per un riepilogo dei requisiti relativi ai certificati per i server perimetrali, vedere [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Quando si installa un server perimetrale, il programma di installazione include una procedura guidata di certificazione che facilita le attività relative alla richiesta, all'assegnazione e all'installazione dei certificati, come descritto nella sezione <A href="lync-server-2013-set-up-edge-certificates.md">set up Edge Certificates for Lync Server 2013</A> . Se si desidera richiedere certificati prima di installare un server perimetrale, ad esempio per risparmiare tempo durante la distribuzione effettiva dei componenti del server perimetrale, è possibile utilizzare i server interni purché si accerti che i certificati siano esportabili e che contengano tutte le nomi alternativi del soggetto richiesti. La presente documentazione non include le procedure per la richiesta dei certificati mediante i server interni.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Richiedere certificati di una CA pubblica

La distribuzione del server perimetrale richiede un singolo certificato pubblico per le interfacce esterne dei server perimetrali, che viene utilizzato per il servizio Access Edge, il servizio Web Conferencing Edge e per il servizio di autenticazione A/V. Questo certificato deve disporre di una chiave privata esportabile per garantire che il servizio di autenticazione A/V utilizzi le stesse chiavi su tutti i server perimetrali in un pool. Il proxy inverso, utilizzato con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, richiede anche un certificato pubblico.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Richiedere certificati a una CA globale (enterprise) interna

I certificati necessari per l'interfaccia perimetrale interna possono essere rilasciati da un'Autorità di certificazione (CA) pubblica oppure interna. È possibile utilizzare una CA globale (enterprise) interna per ridurre al minimo il costo dei certificati. Se nell'organizzazione vi è una CA interna distribuita, i certificati per il perimetro interno devono essere rilasciati dalla CA interna. L'utilizzo di una CA globale (enterprise) interna per i certificati interni consente di ridurre il costo dei certificati.

Per un riepilogo dei requisiti relativi ai certificati per i componenti perimetrali, vedere [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Per informazioni dettagliate sull'utilizzo di un'autorità di certificazione pubblica per ottenere i certificati, vedere [richiesta di certificati per i componenti perimetrali in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Per informazioni dettagliate sulla richiesta, l'installazione e l'assegnazione dei certificati, vedere [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

