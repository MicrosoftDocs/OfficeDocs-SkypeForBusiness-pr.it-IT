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
ms.openlocfilehash: dd73e1356e42aca8dc4159143287371dd66f0688
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a>Panoramica di A/V Conferencing in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-13_

A/V Conferencing consente di abilitare le comunicazioni audio e video in tempo reale tra gli utenti. Quando si distribuisce il servizio di conferenza, è possibile scegliere di abilitare e utilizzare sia le conferenze Web che le conferenze audio/video oppure solo le conferenze Web.

Per la pianificazione delle conferenze audio/video è necessario conoscere i requisiti di larghezza di banda di rete dei vari tipi di supporti per le conferenze richiesti dall'organizzazione. Questo potrebbe includere audio, video e video panoramici.

Prima di abilitare gli utenti per il servizio A/V Conferencing, verificare che la rete sia in grado di gestire il carico risultante. Senza larghezza di banda di rete sufficiente, l'esperienza utente può essere gravemente degradata. È possibile utilizzare il controllo di ammissione di chiamata per gestire la larghezza di banda di rete utilizzata da A/V Conferencing. Questo è importante per le reti limitate, ad esempio collegamenti a larghezza di banda limitate tra i siti centrali e di succursale. Per ulteriori informazioni, vedere [Panoramica del controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md). Per informazioni dettagliate sui requisiti di larghezza di banda multimediale, vedere [requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).

Se si distribuiscono audioconferenza in rete, gli utenti avranno bisogno di dispositivi audio come gli auricolari per partecipare a una conferenza audio. Se si distribuiscono video Conferencing, è necessario distribuire dispositivi video, ad esempio webcams per gli utenti. È consigliabile utilizzare i dispositivi Unified Communications (UC) certificati da Microsoft per tutti i tipi di dispositivi, per garantire un'esperienza utente ottimale. Per informazioni dettagliate sui dispositivi certificati per le comunicazioni unificate, vedere "telefoni e dispositivi [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)per Lync" all'indirizzo. Per i dispositivi audio o video, la distribuzione dei dispositivi e la formazione degli utenti sono passaggi importanti da considerare e pianificare.

Nelle sezioni seguenti vengono descritte le funzionalità per le conferenze audio e video, incluse le informazioni sulla gestione della larghezza di banda e la selezione dei client adatti.

<div>

## <a name="audio-conferencing-features"></a>Funzionalità di audioconferenza

Lync Server 2013 offre diverse funzionalità che è possibile utilizzare per configurare l'esperienza di audioconferenza per l'utente, incluse le operazioni seguenti:

  - **Disattivazione**   del gruppo il relatore può utilizzare questa impostazione per disattivare l'audio di tutti i partecipanti alla conferenza e inserire la conferenza in uno stato in cui non è possibile riattivare gli utenti.

  - **Annunci di entrata/uscita**   per le conferenze se sono state abilitate le conferenze telefoniche con accesso esterno, i relatori possono utilizzare questa impostazione per attivare o disattivare gli annunci di entrata e uscita per ridurre al minimo le distrazioni mentre è in corso una conferenza.

  - **L'aggiunta di un utente tramite la composizione di**   relatori e partecipanti a cui è stata assegnata l'autorizzazione, può aggiungere numeri PSTN alle conferenze e fare in modo che la conferenza venga disattivata in questi numeri.

</div>

<div>

## <a name="video-conferencing-features"></a>Funzionalità di conferenza video

Lync Server 2013 offre diverse funzionalità che è possibile utilizzare per configurare l'esperienza di videoconferenza per l'utente, incluse le operazioni seguenti:

  - **Visualizzazione raccolta nelle**   conferenze video con più di due persone, gli utenti visualizzano automaticamente tutti i partecipanti alla conferenza. Se la conferenza ha più di cinque partecipanti, il video dei partecipanti più attivi viene visualizzato nella riga superiore e viene visualizzata solo la foto per gli altri partecipanti. Il video a più parti è attivato per impostazione predefinita. Per informazioni dettagliate sulla configurazione o la disattivazione del video in più parti, vedere [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

  - **Video panoramico**   se un dispositivo per conferenze video RoundTable è installato nella sala conferenze, questa funzionalità fornisce una visualizzazione completa di 360 gradi della sala riunioni. La striscia panoramica video è disponibile solo con i dispositivi RoundTable.

  - **Relatore solo**   i presentatori della modalità video possono configurare la riunione in modo che venga visualizzato solo il video del relatore. In questo modo si evitano le distrazioni nelle riunioni di grandi dimensioni quando sono disponibili più flussi video e si bloccano su origini diverse. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable.

  - ****   Gli utenti di video HD possono sperimentare risoluzioni fino a 1080p HD in chiamate a due parti e conferenze con più partecipanti.

  - ****   I relatori video Spotlight possono configurare la riunione in modo che solo il video di un partecipante selezionato che sia un'origine video venga visualizzato dagli altri partecipanti alla conferenza. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable per il video panoramico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

