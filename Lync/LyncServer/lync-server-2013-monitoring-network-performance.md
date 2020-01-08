---
title: 'Lync Server 2013: monitoraggio delle prestazioni di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Monitoraggio delle prestazioni di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-04-27_

Lync Server 2013 è una tecnologia di comunicazione in tempo reale che si basa molto sulla rete per consentire la comunicazione tra gli utenti, tramite messaggistica istantanea, chiamate vocali o comunicazioni video. È quindi importante monitorare continuamente le prestazioni della rete per garantire che la modalità di comunicazione scelta dall'utente fornisca la migliore esperienza possibile.

Le prestazioni di rete possono essere misurate a due livelli:

  - **Prestazioni di rete complessive**   questo livello di misurazione delle prestazioni consentirà a un'organizzazione di creare una visualizzazione "Big-Picture" della propria rete e di solito viene implementata tramite sistemi di monitoraggio della rete di terze parti. Questi sistemi riceveranno i dati sulle prestazioni e la capacità da dispositivi di rete remoti come i router e commutati in tutta la rete per consentire agli amministratori di determinare l'integrità di un determinato componente di rete in qualsiasi momento della giornata.

  - **Prestazioni dei singoli server**   questo livello di misurazione delle prestazioni è limitato a un server specifico e aiuta gli amministratori a valutare le prestazioni della rete di un server specifico per facilitare la risoluzione dei problemi di prestazioni o per misurare le prestazioni del server in un determinato periodo nell'ambito di un processo di pianificazione della capacità.

È possibile monitorare la rete usando gli strumenti descritti nelle sezioni seguenti.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Strumenti per il monitoraggio complessivo delle prestazioni di rete

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager offre una gestione dei servizi end-to-end facile da personalizzare ed estendere per migliorare i livelli di servizio in un ambiente IT. Questo consente alle operazioni e ai team di gestione IT di identificare e risolvere i problemi che interessano l'integrità dei servizi IT distribuiti. La gestione dei servizi end-to-end non è limitata agli ambienti basati su Microsoft. Il supporto per servizi Web per la gestione (WS-Management), SNMP (Simple Network Management Protocol) e soluzioni partner consente sistemi che non eseguono sistemi operativi Microsoft e hardware da includere nel monitoraggio del servizio all'interno di System Center Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 e soluzioni di gestione della rete di terze parti

**EMC Smarts**   EMC Solutions per Operations Manager consente di risolvere rapidamente i problemi che interessano i livelli di servizio. Usando soluzioni EMC per Operations Manager, è possibile gestire e monitorare l'intera catena di servizi IT con una soluzione integrata e automatizzata. Potrai identificare facilmente le cause principali dei problemi di prestazioni e disponibilità e risolverli più rapidamente, riducendo gli effetti e i costi. I vantaggi principali includono i seguenti:

  - Lo stato di gestione avanzato e di facile utilizzo consente di fornire un valore aziendale strategico anziché ordinare manualmente e filtrare gli avvisi confusi.

  - **Risoluzione più rapida**   risolvere i problemi e rispondere alle esigenze aziendali più rapidamente, riducendo l'effetto e il costo.

  - **Le operazioni**   semplificate evitano la complessità combinando più strumenti di gestione, applicazioni e terminali.

Altre informazioni possono essere trovate qui:

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Soluzioni per Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Soluzioni di terze parti

HP **Network Management Center (precedentemente noto come HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) offre una gestione integrata delle prestazioni e degli errori per migliorare la disponibilità e le prestazioni della rete. Network Management Center fa parte della soluzione HP per la gestione della rete automatizzata che unifica l'errore, le prestazioni, la configurazione e la gestione delle modifiche.

**Cisco Network Management and Automation Products**   for the Enterprise, Cisco offre diversi prodotti di gestione, tra cui la soluzione di gestione LAN CiscoWorks e il modulo Cisco Network Analysis, per migliorare l'efficienza operativa e ridurre i tempi di inattività della rete. Per ulteriori informazioni su questi prodotti, vedere il sito Web Cisco all' [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)indirizzo.

Il protocollo SNMP (Simple Network Management Protocol) SNMP è uno standard di gestione della rete che definisce una strategia per la gestione delle reti TCP/IP. SNMP consente di acquisire informazioni sulla configurazione e sullo stato della rete e inviare le informazioni a un computer designato per il monitoraggio degli eventi. Questo protocollo di gestione della rete basato su standard usa un'architettura distribuita che include le operazioni seguenti:

  - Più nodi gestiti, ognuno con un'entità SNMP denominata agente che consente l'accesso remoto alla strumentazione di gestione.

  - Almeno un'entità SNMP nota come Manager che esegue le applicazioni di gestione per monitorare e controllare gli elementi gestiti. Gli elementi gestiti sono dispositivi come host, router e così via. Vengono monitorate e controllate accedendo alle informazioni di gestione.

  - Un protocollo di gestione, SNMP, viene usato per comunicare le informazioni di gestione tra le stazioni di gestione e gli agenti. Le informazioni di gestione fanno riferimento a una raccolta di oggetti gestiti che vivono in un archivio di informazioni virtuale denominato MIB (Management Information Base).

<div>


> [!NOTE]  
> Sono disponibili alcuni esempi di soluzioni di monitoraggio della rete di terze parti. Questo elenco non è definitivo e Microsoft non favorisce alcuna soluzione specifica del fornitore. Consultarsi con un provider di servizi di rete e il rispettivo provider di tecnologia per determinare la soluzione di monitoraggio della rete migliore per l'organizzazione.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Strumenti per il monitoraggio delle prestazioni delle singole reti del server

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 consente agli amministratori di visualizzare le prestazioni di rete dei singoli server tramite il Management Pack di Windows Server 2012: il Management Pack del sistema operativo Windows Server include un Management Pack "prestazioni" Ciò consentirebbe agli amministratori di monitorare le prestazioni della scheda di rete e l'integrità della scheda.

</div>

<div>

## <a name="windows-network-monitor"></a>Windows Network Monitor

Raccoglie, Visualizza, analizza l'utilizzo delle risorse in un server e misura il traffico di rete. Network Monitor monitora in esclusiva l'attività di rete. Tramite l'acquisizione e l'analisi dei dati di rete e l'uso di questi dati con i registri delle prestazioni, è possibile determinare l'utilizzo della rete, identificare i problemi di rete e prevedere le future esigenze di rete.

Per altre informazioni su Network Monitor 3,4 e per scoprire come installare e configurare Network Monitor e acquisire e analizzare i dati, rivedere questa sessione: Panoramica di Network Monitor 3,3. Esaminare inoltre il [Blog di Network Monitor](http://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

