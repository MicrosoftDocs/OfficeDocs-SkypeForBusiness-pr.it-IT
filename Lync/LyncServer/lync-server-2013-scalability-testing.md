---
title: Test di scalabilità di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Test di scalabilità in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Lync Server 2013 offre l'infrastruttura server per tutte le comunicazioni in tempo reale di Lync Server, tra cui messaggistica istantanea e presenza, conferenza e VoIP aziendale. Sono incluse tutte le caratteristiche che usano le risorse hardware di un pool di Lync Server 2013 e quindi incidono sulle prestazioni e sulle proporzioni. Tutte le organizzazioni non usano tutte le funzionalità in modo uniforme.

Ad esempio, alcune organizzazioni potrebbero usare il video in conferenze molto duramente, mentre altri potrebbero avere poco o nessun utilizzo video. Alcune organizzazioni preferiscono la condivisione di diapositive di PowerPoint nella condivisione delle applicazioni, mentre altre preferiscono il contrario. Le organizzazioni che distribuiscono Enterprise Voice potrebbero non usare molto l'applicazione Response Group. La maggior parte delle organizzazioni distribuisce server di monitoraggio, ma non molti distribuiscono i server di archiviazione. Inoltre, le organizzazioni non hanno tutte le stesse infrastrutture, incluse le capacità hardware, le capacità di rete e il numero di pool e le dimensioni dei pool distribuiti. La diversità delle caratteristiche e delle infrastrutture rappresenta una sfida per i test di scalabilità: non è possibile simulare tutte le possibili combinazioni di funzionalità e infrastrutture.

Per determinare il supporto della scalabilità per Lync Server, conduciamo test usando tutte le funzionalità di Lync Server contemporaneamente, in base a un modello di utilizzo medio (modello utente). Per determinare un modello utente appropriato per i carichi di lavoro di Lync Server, analizziamo molti punti dati, inclusi i sondaggi dei clienti, il feedback del programma Microsoft Customer Experience Improvement, i dati di utilizzo di Lync Server dal reparto IT interno di Microsoft, e i dati estratti dal nostro servizio Live Meeting. In molti casi, il modello utente ha una distorsione nei confronti di carichi più pesanti per ottenere un margine comodo per l'utilizzo all'interno di un'organizzazione.

Nei test di scalabilità abbiamo configurato i pool di Lync Server 2013 in base alle specifiche hardware e software consigliate, inclusi i componenti dell'infrastruttura, ad esempio i servizi di dominio Active Directory, i dispositivi di bilanciamento del carico hardware e i firewall. Configuriamo gli ambienti di Lync Server il più vicino possibile agli ambienti reali del mondo reale. Viene quindi usato lo strumento di esecuzione dello stress e delle prestazioni di Lync Server 2013 per simulare i carichi di Lync Server 2013 (in base al modello di utente). .

Eseguiamo più iterazioni di test di scalabilità (tra cui più esecuzioni di test di tre settimane). Usiamo i risultati di tutti i test per facilitare l'ottimizzazione delle prestazioni e per verificare il supporto per i numeri di scalabilità nel modello di utente.

</div>

<span> </span>

</div>

</div>

</div>

