---
title: Panoramica di Lync Server 2013 A/V Conferencing
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 405d44f9128ef4c8120a6a8389f8d566b6880b2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Panoramica delle conferenze A/V in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-13_

A/V Conferencing consente le comunicazioni audio e video in tempo reale tra gli utenti. Quando si distribuiscono i servizi di conferenza, è possibile scegliere di abilitare e usare servizi di conferenza Web e conferenze A/V o solo servizi di conferenza Web.

Per pianificare i servizi di conferenza A/V, è necessario comprendere la larghezza di banda della rete necessaria per il tipo di supporto per i servizi di conferenza richiesto dall'organizzazione. Questo potrebbe includere l'audio, il video e il video panoramico.

Prima di abilitare gli utenti per le conferenze A/V, assicurati che la rete possa gestire il carico risultante. Senza una sufficiente larghezza di banda della rete, l'esperienza utente potrebbe essere gravemente degradata. Puoi usare il controllo di ammissione chiamata (CAC) per gestire la larghezza di banda della rete usata da servizi di conferenza A/V. Questa operazione è importante per le reti con restrizioni, ad esempio i collegamenti a larghezza di banda limitati tra siti centrali e succursali. Per informazioni dettagliate, vedere [Panoramica del controllo di ammissione alle chiamate in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Per informazioni dettagliate sui requisiti di larghezza di banda multimediali, vedere [requisiti di larghezza di banda della rete per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Se si distribuiscono i servizi di audioconferenza nella rete, gli utenti avranno bisogno di dispositivi audio come auricolari per partecipare a una conferenza audio. Se si distribuiscono videoconferenze, è necessario distribuire dispositivi video, ad esempio webcam per gli utenti. Ti consigliamo di usare i dispositivi Unified Communications (UC) certificati da Microsoft per tutti i tipi di dispositivi, per garantire un'esperienza utente ottimale. Per informazioni dettagliate sui dispositivi certificati UC, vedere "telefoni e dispositivi per Lync" all' [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)indirizzo. Per i dispositivi audio o video, la distribuzione di dispositivi e la formazione degli utenti sono passaggi importanti da considerare e pianificare.

Le sezioni seguenti descrivono le funzionalità per le conferenze audio e video, incluse le informazioni sulla gestione della larghezza di banda e la selezione dei client appropriati.

<div>

## <a name="audio-conferencing-features"></a>Funzionalità di conferenza audio

Lync Server 2013 offre diverse funzionalità che possono essere usate per configurare l'esperienza di audioconferenza per l'utente, inclusi i seguenti:

  - **Disattivazione del pubblico**   il relatore può usare questa impostazione per disattivare l'audio di tutti i partecipanti alla conferenza e inserire la conferenza in uno stato in cui non è possibile riattivare gli utenti.

  - **Annunci di entrata/uscita per conferenze**   se sono stati abilitati i servizi di conferenza telefonica con accesso esterno, i relatori possono usare questa impostazione per attivare o disattivare gli annunci di entrata e uscita per ridurre al minimo le distrazioni mentre è in corso una conferenza.

  - **L'aggiunta di un utente tramite la chiamata di**   relatori e partecipanti a cui è stata assegnata l'autorizzazione può aggiungere numeri PSTN alle conferenze e effettuare la chiamata in uscita per i numeri.

</div>

<div>

## <a name="video-conferencing-features"></a>Funzionalità di conferenza video

Lync Server 2013 offre diverse funzionalità che è possibile usare per configurare l'esperienza di videoconferenza per l'utente, inclusi i seguenti:

  - **Visualizzazione raccolta in**   videoconferenze con più di due persone, gli utenti vedranno automaticamente tutti i partecipanti alla conferenza. Se la conferenza include più di cinque partecipanti, il video dei partecipanti più attivi viene visualizzato nella riga superiore e viene visualizzata solo la foto per gli altri partecipanti. Il video a più parti è attivato per impostazione predefinita. Per informazioni dettagliate sulla configurazione o disattivazione di un video con più parti, vedere [configurazione della larghezza di banda video in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Video panoramico**   se un dispositivo di videoconferenza RoundTable è installato nella sala conferenze, questa caratteristica offre una visualizzazione completa di 360 gradi della sala riunioni. La striscia video panoramica è disponibile solo con i dispositivi RoundTable.

  - **Relatore solo**   i presentatori della modalità video possono configurare la riunione in modo che venga visualizzato solo il video del relatore. In questo modo si evitano le distrazioni nelle riunioni di grandi dimensioni quando sono disponibili più flussi video e si bloccano in origini diverse. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable.

  - ****   Gli utenti di video HD possono provare risoluzioni fino a 1080p HD in chiamate in due parti e conferenze multiparte.

  - ****   I relatori dei riflettori video possono configurare la riunione in modo che solo il video di un partecipante selezionato che è un'origine video sia visibile dagli altri partecipanti alla conferenza. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable per il video panoramico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

