---
title: 'Lync Server 2013: Richiedere i certificati per i componenti perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e848e5fb8ea120bab2251dff776e2c9c27eacca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Richiedere i certificati per i componenti perimetrali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

I certificati necessari per supportare l'accesso degli utenti esterni includono certificati emessi da un'autorità di certificazione pubblica (CA) e certificati emessi da una CA aziendale interna:

  - I certificati necessari per l'interfaccia esterna di Edge Server e il proxy inverso devono essere emessi da una CA pubblica.

  - I certificati necessari per l'interfaccia interna possono essere emessi da una CA pubblica o da una CA interna dell'organizzazione. È consigliabile usare una CA interna di Windows Server 2008, Windows Server 2008 R2, CA, Windows Server 2012 CA o Windows Server 2012 R2 per la creazione di questi certificati per il salvataggio a spese dell'uso di certificati pubblici.

<div>


> [!IMPORTANT]  
> Può essere necessario un po' di tempo per elaborare le richieste di certificato, in particolare le richieste alle autorità di certificazione pubbliche, in modo da richiedere i certificati per i server perimetrali abbastanza presto per verificare che siano disponibili quando si avvia la distribuzione dei componenti del server perimetrale. Per un riepilogo dei requisiti di certificato per Edge Server, vedere <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013</A>.



</div>

Anche se è possibile scegliere di usare una CA pubblica per il certificato di bordo interno, è consigliabile usare una CA aziendale interna per gli altri certificati per ridurre al minimo il costo dei certificati. Per un riepilogo dei requisiti di certificato per Edge Server, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Quando si installa un server perimetrale, il programma di installazione include una procedura guidata per il certificato che facilita le attività di richiesta, assegnazione e installazione dei certificati, come descritto nella sezione <A href="lync-server-2013-set-up-edge-certificates.md">configurare i certificati di Edge per Lync Server 2013</A> . Se si vogliono richiedere certificati prima di installare un server perimetrale, ad esempio per risparmiare tempo durante la distribuzione effettiva dei componenti di Edge Server, è possibile usare i server interni purché si accerti che i certificati siano esportabili e contengano tutte le nomi di oggetto alternativi obbligatori. Questa documentazione non offre procedure per l'uso dei server interni per richiedere certificati.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Richiedere certificati da una CA pubblica

La distribuzione di Edge Server richiede un singolo certificato pubblico per le interfacce esterne di Edge Server, usato per il servizio Access Edge, il servizio Web Conferencing Edge e per il servizio di autenticazione A/V. Questo certificato deve avere una chiave privata esportabile per verificare che il servizio di autenticazione A/V usi le stesse chiavi in tutti i server perimetrali in un pool. Il proxy inverso, usato con Microsoft Internet Security and Acceleration (ISA) Server 2006 o Microsoft Forefront Threat Management Gateway 2010, richiede anche un certificato pubblico.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Richiedere certificati da una CA aziendale interna

I certificati necessari per l'interfaccia Edge interna possono essere emessi da un'autorità di certificazione pubblica (CA) o da una CA interna. È possibile usare una CA aziendale interna per ridurre al minimo il costo dei certificati. Se l'organizzazione ha una CA interna distribuita, i certificati per il bordo interno devono essere emessi dalla CA interna. L'uso di una CA aziendale interna per i certificati interni può ridurre il costo dei certificati.

Per un riepilogo dei requisiti di certificato per i componenti di Edge, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Per informazioni dettagliate sull'uso di una CA pubblica per ottenere i certificati, vedere [richiedere certificati per i componenti di Edge in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Per informazioni dettagliate sulla richiesta, l'installazione e l'assegnazione di certificati, vedere [configurare i certificati di Edge per Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

