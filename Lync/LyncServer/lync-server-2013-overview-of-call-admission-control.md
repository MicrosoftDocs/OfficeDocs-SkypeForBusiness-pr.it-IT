---
title: 'Lync Server 2013: Panoramica del controllo di ammissione alle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Panoramica del controllo di ammissione alle chiamate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-22_

Le comunicazioni in tempo reale sono sensibili alla latenza e alla perdita di pacchetti che possono verificarsi nelle reti congestionate. Il controllo di ammissione di chiamata (CAC) determina, in base alla larghezza di banda della rete disponibile, se consentire la creazione di sessioni di comunicazioni in tempo reale, ad esempio chiamate vocali o videochiamate. La progettazione CAC in Lync Server 2013 offre quattro attributi principali:

  - È semplice eseguire la distribuzione e la gestione senza richiedere ulteriori dispositivi, ad esempio router appositamente configurati.

  - Risolve i casi di utilizzo delle comunicazioni unificate critiche, ad esempio utenti mobili e più punti di presenza. I criteri di CAC vengono applicati in base al punto in cui si trova l'endpoint, non in cui è ospitato l'utente.

  - Oltre alle chiamate vocali, può essere applicato ad altri traffici, ad esempio videochiamate e sessioni di conferenze audio/video.

  - Offre la flessibilità necessaria per consentire la rappresentazione di vari tipi di topologie di rete. Per gli esempi, vedere [componenti e topologie per CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Se una nuova sessione vocale o video supera i limiti di larghezza di banda impostati in un collegamento WAN, la sessione viene bloccata oppure (solo per le chiamate telefoniche) viene reinstradata alla rete PSTN.

CAC controlla il traffico in tempo reale solo per voce e video. Non controlla il traffico dati.

Gli amministratori definiscono i criteri di CAC, applicati dal servizio dei criteri di larghezza di banda installato con ogni pool Front-end. Le impostazioni di CAC vengono propagate automaticamente a tutti i server front-end di Lync in rete.

Per le chiamate che non riescono a causa di criteri di CAC, l'ordine di precedenza per il reinstradamento della chiamata è il seguente:

1.  Internet

2.  PSTN

3.  Segreteria telefonica

La registrazione dei dettagli delle chiamate (CDR) acquisisce informazioni sulle chiamate reinstradate alla rete PSTN o alla segreteria telefonica. CDR non acquisisce informazioni sulle chiamate reinstradate a Internet, poiché Internet viene considerato come percorso alternativo anziché come opzione secondaria.

<div>


> [!NOTE]  
> I depositi della segreteria telefonica non verranno negati a causa di vincoli di larghezza di banda.



</div>

Il servizio criteri di larghezza di banda genera due tipi di file di log in formato CSV (comma separated values). Il file di log degli **errori di controllo** acquisisce informazioni quando le richieste di larghezza di banda vengono negate. Il file di log di **utilizzo del collegamento** acquisisce uno snapshot della topologia di rete e dell'utilizzo della larghezza di banda dei collegamenti WAN. Entrambi i file di log possono aiutarti a ottimizzare i criteri di CAC in base all'utilizzo.

<div>

## <a name="call-admission-control-considerations"></a>Considerazioni sul controllo dell'ammissione alle chiamate

L'amministratore seleziona per installare il servizio criteri di larghezza di banda nel primo pool configurato nel sito centrale. Poiché esiste un unico sito centrale per ogni area di rete, esiste un solo servizio per i criteri di larghezza di banda per ogni area di rete, che gestisce i criteri di larghezza di banda per l'area geografica, i siti associati e i collegamenti a tali siti. Il servizio criteri di larghezza di banda viene eseguito come parte dei server front-end e quindi la disponibilità elevata è incorporata all'interno di tale pool. Il servizio criteri di larghezza di banda eseguito in ogni server front-end viene sincronizzato ogni 15 secondi. Se il pool Front-end non riesce, i criteri di CAC non vengono più applicati per il sito fino al pool Front-end e di conseguenza il servizio dei criteri di larghezza di banda diventa operativo. Questo implica che tutte le chiamate verranno effettuate per tutta la durata del servizio per i criteri di larghezza di banda fuori servizio. È quindi possibile che l'oversubscription della larghezza di banda dei collegamenti durante questo periodo

Il servizio criteri di larghezza di banda offre una disponibilità elevata all'interno di un pool Front End; Tuttavia, non offre ridondanza nei pool Front-end. Il servizio criteri di larghezza di banda non può eseguire il failover da un pool Front-end a un altro. Una volta ripristinato il servizio al pool Front-End, il servizio criteri di larghezza di banda viene ripreso e può applicare di nuovo i controlli dei criteri di larghezza di banda.

<div>

## <a name="network-considerations"></a>Considerazioni sulla rete

Anche se la restrizione della larghezza di banda per l'audio e il video viene applicata dal servizio criteri di larghezza di banda in Lync Server 2013, questa restrizione non viene applicata al router di rete (Layer 2 e 3). Lync Server 2010 CAC non può impedire a un'applicazione dati, ad esempio, di consumare l'intera larghezza di banda della rete su un collegamento WAN, inclusa la larghezza di banda riservata per l'audio e il video in base ai criteri di CAC. Per proteggere la larghezza di banda necessaria nella rete, è possibile distribuire un protocollo QoS (Quality of Service), ad esempio servizi differenziati (DiffServ). Una procedura consigliata consiste quindi nel coordinare i criteri di larghezza di banda CAC definiti con le impostazioni QoS eventualmente distribuite.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Percorsi multimediali e di segnalazione su VPN

Se l'organizzazione supporta i contenuti multimediali tramite VPN, verificare che sia il flusso multimediale che il flusso di segnalazione passano attraverso la rete VPN oppure vengono instradati attraverso Internet. Per impostazione predefinita, i flussi di elementi multimediali e di segnalazione passano attraverso il tunnel VPN.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Controllo dell'ammissione delle chiamate degli utenti esterni

Il controllo di ammissione alle chiamate non viene applicato per gli utenti remoti in cui il traffico di rete scorre su Internet. Poiché il traffico multimediale sta attraversando Internet, che non è gestito da Lync Server, non è possibile applicare CAC. I controlli CAC verranno eseguiti, tuttavia, nella parte della chiamata che scorre attraverso la rete aziendale.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Controllo ammissione chiamata delle connessioni PSTN

Il controllo di ammissione delle chiamate è impostabile sul server Mediation indipendentemente dal fatto che sia connesso a un IP/PBX, a un gateway PSTN o a un trunk SIP. Poiché il Mediation Server è un agente utente back-to-back (B2BUA), termina media. Ha due lati di connessione: un lato connesso a Lync Server e un lato del gateway, che è connesso a gateway PSTN, IP/PBX o trunk SIP. Per informazioni dettagliate sulle connessioni PSTN, vedere [pianificazione della connettività PSTN in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

CAC può essere applicato su entrambi i lati del Mediation Server, a meno che non sia abilitato il bypass multimediale. Se il bypass multimediale è abilitato, il traffico multimediale non attraversa il Mediation Server, bensì fluisce direttamente tra il client Lync e il gateway. In questo caso, CAC non è necessario. Per informazioni dettagliate, vedere [pianificazione di un bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

Nella figura seguente viene illustrato il modo in cui CAC viene applicato alle connessioni PSTN con e senza bypass multimediale abilitato.

**Applicazione controllo ammissione chiamata sulle connessioni alla rete PSTN**

![Applicazione del controllo di ammissione di chiamata vocale con bypass multimediale sulle connessioni](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Applicazione del controllo di ammissione di chiamata vocale con bypass multimediale sulle connessioni")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Compatibilità del controllo di ammissione alle chiamate con versioni precedenti di Office Communications Server

Il controllo di ammissione delle chiamate può essere abilitato solo sugli endpoint abilitati per Lync Server 2010 e versioni successive.

Non è possibile abilitare il controllo ammissione chiamata in endpoint con Office Communicator 2007 R2 o versioni precedenti.

**Applicazione di CAC in diverse versioni di Lync Server**

![Diagramma di confronto tra le versioni per il controllo di ammissione di chiamata vocale](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagramma di confronto tra le versioni per il controllo di ammissione di chiamata vocale")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

