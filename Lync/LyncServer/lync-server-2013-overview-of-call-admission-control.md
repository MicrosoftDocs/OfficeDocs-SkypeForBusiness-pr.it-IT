---
title: 'Lync Server 2013: Panoramica del controllo di ammissione di chiamata'
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
ms.openlocfilehash: 545355c1746846a16cf51e4147938f9c0a35710a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Panoramica del controllo di ammissione di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-22_

Le comunicazioni in tempo reale sono sensibili alla latenza e alla perdita di pacchetti che possono verificarsi in reti congestionate. Il controllo di ammissione di chiamata determina, in base alla larghezza di banda disponibile, se consentire di stabilire sessioni di comunicazione in tempo reale, ad esempio chiamate vocali o videochiamate. La progettazione del servizio di controllo di ammissione in Lync Server 2013 offre quattro attributi principali:

  - È semplice da distribuire e gestire senza richiedere apparecchiature aggiuntive, ad esempio router configurati in modo speciale.

  - Consente di risolvere casi critici di utilizzo delle comunicazioni unificate, ad esempio relativi a utenti mobili e a più punti di presenza. I criteri di controllo di ammissione di chiamata vengono applicati in base alla posizione dell'endpoint e non a quella in cui risiede l'utente.

  - Oltre alle chiamate vocali, può essere applicato ad altro traffico, ad esempio alle videochiamate e alle sessioni di conferenza audio/video.

  - Offre la flessibilità necessaria per consentire la rappresentazione di diversi tipi di topologie di rete. Per alcuni esempi, vedere [componenti e topologie per il servizio di controllo di ammissione in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Se una nuova sessione vocale o video supera i limiti di larghezza di banda impostati in un collegamento WAN, la sessione viene bloccata (solo per le chiamate telefoniche) o reinstradata alla rete PSTN.

Il controllo di ammissione di chiamata controlla solo il traffico audio e video in tempo reale, ma non il traffico di dati.

Gli amministratori definiscono i criteri di CAC, applicati dal servizio criteri di larghezza di banda installato con tutti i pool Front end. Le impostazioni del servizio di controllo di ammissione vengono propagate automaticamente a tutti i server front end di Lync Server della rete.

Per le chiamate non riuscite a causa di criteri di controllo di ammissione di chiamata, l'ordine di precedenza per il rerouting della chiamata è il seguente:

1.  Internet

2.  PSTN

3.  Segreteria telefonica

Tramite la registrazione dettagli chiamata (CDR) vengono acquisite informazioni sulle chiamate reinstradate alla rete PSTN o alla segreteria telefonica. CDR non consente l'acquisizione di informazioni sulle chiamate reinstradate a Internet, perché Internet viene considerato un percorso alternativo anziché un'opzione secondaria.

<div>


> [!NOTE]  
> L'archiviazione nella segreteria telefonica non viene negata a causa di vincoli di larghezza di banda.



</div>

Il servizio criteri di larghezza di banda genera due tipi di file di registro in formato con valori separati da virgole (CSV). Nel file di registro degli **errori di verifica** vengono acquisite informazioni quando vengono negate richieste di larghezza di banda. Nel file di registro dell'**utilizzo dei collegamenti** viene acquisita un'istantanea dell'utilizzo della larghezza di banda della topologia di rete e del collegamento WAN. Entrambi questi file di registro possono semplificare l'ottimizzazione dei criteri di controllo di ammissione di chiamata in base all'utilizzo.

<div>

## <a name="call-admission-control-considerations"></a>Considerazioni relative al controllo di ammissione di chiamata

L'amministratore seleziona per installare il servizio criteri di larghezza di banda sul primo pool configurato nel sito centrale. Poiché è presente un unico sito centrale per ogni area di rete, è presente un solo servizio criteri di larghezza di banda per ogni area di rete, che consente di gestire i criteri di larghezza di banda per tale area, i siti associati e i collegamenti a tali siti. Il servizio criteri di larghezza di banda viene eseguito come parte dei front end server e quindi la disponibilità elevata è incorporata all'interno di tale pool. Il servizio dei criteri di larghezza di banda in esecuzione su ogni Front End Server Sincronizza ogni 15 secondi. Se il pool Front End ha esito negativo, i criteri di CAC non vengono più applicati per il sito fino a quando il pool Front end e di conseguenza il servizio criteri di larghezza di banda diventeranno di nuovo operativi. Questo implica che tutte le chiamate passeranno per la durata del servizio dei criteri di larghezza di banda non è in servizio. Vi è pertanto la possibilità di oversubscription della larghezza di banda dei collegamenti durante questo periodo

Il servizio criteri di larghezza di banda garantisce una disponibilità elevata all'interno di un pool Front end. Tuttavia, non fornisce la ridondanza nei pool Front end. Il servizio criteri di larghezza di banda non può eseguire il failover da un pool Front end a un altro. Dopo il ripristino del servizio per il pool Front End, il servizio criteri di larghezza di banda viene ripristinato e può applicare di nuovo i controlli dei criteri di larghezza di banda.

<div>

## <a name="network-considerations"></a>Considerazioni sulla rete

Anche se la limitazione della larghezza di banda per l'audio e il video viene applicata dal servizio criteri di larghezza di banda in Lync Server 2013, questa restrizione non viene applicata al router di rete (Layer 2 e 3). Lync Server 2010 CAC non è in grado di impedire l'utilizzo dell'intera larghezza di banda della rete su un collegamento WAN, inclusa la larghezza di banda riservata per audio e video da parte del criterio di controllo di ammissione di chiamata. Per proteggere la larghezza di banda necessaria per la rete, è possibile distribuire un protocollo QoS (Quality of Service), ad esempio servizi differenziati (DiffServ). Pertanto, una procedura consigliata consiste nel coordinare i criteri di larghezza di banda di CAC definiti con eventuali impostazioni QoS che è possibile distribuire.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Percorsi di contenuti multimediali e segnali su VPN

Se l'organizzazione supporta contenuto multimediale tramite VPN, verificare che il flusso multimediale e il flusso dei segnali attraversino la rete VPN o che venga eseguito il routing di entrambi tramite internet. Per impostazione predefinita, i flussi multimediali e dei segnali passano attraverso il tunnel VPN.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Controllo di ammissione di chiamata di utenti esterni

Il controllo di ammissione di chiamata non viene applicato per utenti remoti nei casi in cui il flusso del traffico di rete viene eseguito tramite Internet. Poiché il traffico multimediale attraversa Internet, che non è gestito da Lync Server, non è possibile applicare il servizio di controllo di accesso. Tali controlli verranno tuttavia eseguiti sulla parte della chiamata il cui flusso attraversa la rete aziendale.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Controllo di ammissione di chiamata di connessioni PSTN

Il controllo di ammissione di chiamata è applicabile sul Mediation Server, indipendentemente dal fatto che sia connesso a un IP/PBX, a un gateway PSTN o a un trunk SIP. Poiché il Mediation Server è un agente utente back-to-back (B2BUA), termina il supporto. Ha due lati di connessione: un lato connesso a Lync Server e un lato del gateway, connesso a gateway PSTN, IP/PBX o trunk SIP. Per informazioni dettagliate sulle connessioni PSTN, vedere [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

Il servizio di controllo di ammissione può essere applicato su entrambi i lati del Mediation Server, a meno che non sia abilitato il bypass multimediale. Se il bypass multimediale è abilitato, il traffico multimediale non attraversa il Mediation Server, ma invece scorre direttamente tra il client Lync e il gateway. In questo caso, il controllo di ammissione di chiamata non è necessario. Per informazioni dettagliate, vedere [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

Nella figura seguente viene illustrata l'applicazione di controllo di ammissione di chiamata in connessioni PSTN con o senza il bypass multimediale abilitato.

**Applicazione del controllo di ammissione di chiamata in connessioni alla rete PSTN**

![Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Compatibilità del controllo di ammissione di chiamata con le versioni precedenti di Office Communications Server

Il controllo di ammissione di chiamata può essere abilitato solo sugli endpoint abilitati per Lync Server 2010 e versioni successive.

Non è possibile abilitare il controllo di ammissione di chiamata sugli endpoint che eseguono Office Communicator 2007 R2 o versioni precedenti.

**Applicazione del controllo di ammissione di chiamata in versioni di Lync Server diverse**

![Diagramma di confronto delle versioni di Voice CAC](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagramma di confronto delle versioni di Voice CAC")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

