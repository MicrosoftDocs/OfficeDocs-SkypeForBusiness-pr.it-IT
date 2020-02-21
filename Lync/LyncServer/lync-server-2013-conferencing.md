---
title: Lync Server 2013 Conferencing
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c015397b1c29bec50f05feeab4f21d54d3f1e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Servizi di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-11_

Con Unified Conferencing in Lync Server 2013, gli utenti possono collaborare, condividere informazioni e coordinare i propri sforzi in tempo reale. Tutti gli utenti possono avvalersi dell'intera gamma di strumenti per la collaborazione spontanea, le riunioni pianificate e le riunioni. Le funzionalità per conferenze audio e video possono essere utilizzate da qualsiasi posizione con una connessione Internet e gli utenti lontani da un computer possono partecipare a conferenze audio chiamando con un telefono PSTN (Public Switched Telephone Network) .

Gli strumenti per riunioni integrati in Outlook consentono agli organizzatori di pianificare una riunione o avviare una conferenza improvvisata con un solo clic e rendere altrettanto semplice per i partecipanti partecipare. Un client Web estende le funzionalità di conferenza ricche ai partecipanti che non eseguono la versione desktop di Lync.

<div>

## <a name="audio-and-video-conferencing"></a>Conferenze audio e video

Lync Server fornisce un'esperienza utente che ha familiarità con gli utenti dei servizi di Bridge audio tradizionali, compresi i servizi di accesso esterno PSTN con i comandi di controllo delle chiamate Touch-Tone. Sono allo stesso tempo incluse funzionalità avanzate per pianificazione, partecipazione e gestione disponibili solo con una piattaforma di comunicazioni unificate integrata.

Con un solo clic, gli utenti possono programmare una riunione da Outlook. I dettagli, ad esempio la durata della riunione, la posizione e i partecipanti, seguono il modello di Outlook noto. Inoltre, vengono inserite automaticamente informazioni specifiche per le chiamate di conferenza, ad esempio il numero di accesso esterno, gli ID riunione e i promemoria PIN (Personal Identification Number).

Per garantire che solo le persone autorizzate partecipino a una chiamata, Lync Server fornisce più livelli di autenticazione per i partecipanti. Gli utenti che si connettono utilizzando Lync sono già autenticati da servizi di dominio Active Directory e non devono immettere un PIN, un codice di passaggio o un ID riunione.

Lync semplifica l'esperienza utente per le conferenze video incorporando video nel client unificato, in modo che la pianificazione di una riunione con video o l'escalation del video sia spontanea e senza problemi.

Lync Server rende più semplice aggiungere video a una chiamata telefonica standard con un solo clic. Se alla chiamata video o a una conferenza partecipano più utenti, ogni utente può vedere il video di un massimo di cinque altri utenti contemporaneamente e un relatore può scegliere una sola origine video per essere l'unico a essere visibile per tutti i partecipanti.

Video ad alta definizione (risoluzione 1270 x 720; proporzioni 16:9) e video VGA (risoluzione 640 x 480; proporzioni 4:3) sono supportati per le chiamate peer-to-peer tra gli utenti che eseguono Lync nei computer di fascia alta. La risoluzione disponibile per ogni partecipante a una singola conversazione può essere diversa, a seconda delle capacità video del rispettivo hardware di ogni utente.

Gli amministratori IT possono impostare criteri per limitare o disabilitare il video ad alta definizione o VGA nei client, in base alle caratteristiche del computer, alla larghezza di banda della rete e alla presenza di videocamere in grado di offrire la risoluzione richiesta. Questi criteri vengono applicati tramite il provisioning di tipo in-band.

</div>

<div>

## <a name="web-conferencing"></a>Conferenze Web

Lync Server integra funzionalità di condivisione delle conferenze quali desktop, applicazioni, allegati, lavagne, poll e PowerPoint nel Lync semplificato. In combinazione con le funzionalità per conferenze audio o video, il risultato è una sessione di collaborazione molto coinvolgente e facile da coordinare.

Per migliorare l'esperienza complessiva degli utenti che presentano o visualizzano presentazioni di PowerPoint, Lync Server 2013 utilizza Office Web Apps per gestire le presentazioni di PowerPoint. Gli utenti possono condividere un'immagine o copiare e incollare il testo utilizzando una lavagna nella riunione di Lync. I relatori possono effettuare sondaggi nella riunione di Lync per richiedere commenti e suggerimenti da parte dei partecipanti.

La condivisione desktop consente ai relatori di trasmettere in tempo reale eventuali elementi visivi, applicazioni, pagine Web, documenti, software o parte dei desktop ai partecipanti remoti, direttamente da Lync. I partecipanti possono seguire anche i movimenti del mouse e le immissioni da tastiera. I relatori possono scegliere di condividere l'intero schermo o solo una parte. Con la condivisione dei desktop, i relatori possono intrattenere il pubblico con dimostrazioni di prodotti o software interattive da qualsiasi luogo.

Con la condivisione delle applicazioni i relatori possono condividere il controllo del software sul desktop senza perdere di vista i commenti e suggerimenti o le domande testuali dei partecipanti. I relatori hanno inoltre la possibilità di delegare il controllo dell'applicazione ai partecipanti alla riunione.

</div>

<div>

## <a name="dial-in-conferencing"></a>Conferenza telefonica con accesso esterno

Per gli utenti che non utilizzano un computer personale, sono disponibili diversi metodi per l'aggiunta di una conferenza telefonica di Lync Server. Un utente PSTN può comporre un numero di accesso, accedere al ponte della riunione e quindi immettere l'ID della riunione. Per una maggiore sicurezza delle riunioni, è inoltre possibile che all'utente venga richiesto di immettere il PIN per l'autenticazione in Active Directory. Lync Server supporta anche i dispositivi Lync Phone Edition, che sono dispositivi IP di telefonia autonoma forniti da Microsoft Partners.

</div>

</div>

<span> </span>

</div>

</div>

</div>

