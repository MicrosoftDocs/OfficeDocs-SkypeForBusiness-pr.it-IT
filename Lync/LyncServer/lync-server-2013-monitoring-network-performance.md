---
title: 'Lync Server 2013: monitoraggio delle prestazioni della rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aafea72c7e30644f8a882f1cf556c665e1e285ad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Monitoraggio delle prestazioni di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-04-27_

Lync Server 2013 è una tecnologia di comunicazione in tempo reale che si basa fortemente sulla rete per abilitare la comunicazione tra gli utenti, tramite la messaggistica istantanea (IM), le chiamate vocali o la comunicazione video. È pertanto importante monitorare continuamente le prestazioni della rete per garantire che la modalità di comunicazione scelta dall'utente offra la migliore esperienza possibile.

Le prestazioni di rete possono essere misurate a due livelli:

  - **Prestazioni di rete complessive**   questo livello di misura delle prestazioni consentirà a un'organizzazione di creare una visualizzazione "Big-Picture" della propria rete e di solito viene implementata attraverso sistemi di monitoraggio della rete di terze parti. Questi sistemi riceveranno i dati sulle prestazioni e la capacità dei dispositivi di rete remota, come i router e commutati in tutta la rete, per consentire agli amministratori di determinare l'integrità di un determinato componente di rete in qualsiasi momento della giornata.

  - **Prestazioni dei singoli server**   questo livello di misura delle prestazioni è limitato a un server specifico e consente agli amministratori di valutare le prestazioni di rete di un server specifico per facilitare la risoluzione dei problemi di prestazioni specifici o per misurare le prestazioni del rispettivo server in un determinato periodo nell'ambito di un processo di pianificazione della capacità.

È possibile monitorare la rete utilizzando gli strumenti descritti nelle sezioni seguenti.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>Strumenti per il monitoraggio globale delle prestazioni della rete

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager fornisce la gestione dei servizi end-to-end facile da personalizzare ed estendere per migliorare i livelli di servizio in un ambiente IT. Questo consente alle operazioni e ai team di gestione IT di identificare e risolvere i problemi relativi all'integrità dei servizi IT distribuiti. La gestione dei servizi end-to-end non è limitata agli ambienti basati su Microsoft. Il supporto per i servizi Web per la gestione (WS-Management), il protocollo SNMP (Simple Network Management Protocol) e le soluzioni partner consentono sistemi che non eseguono sistemi operativi e hardware Microsoft da includere nel monitoraggio del servizio all'interno di System Center Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 e soluzioni di gestione della rete di terze parti

**EMC Smarts**   EMC Solutions for Operations Manager consente di risolvere rapidamente i problemi che interessano i livelli di servizio in tutto. Utilizzando soluzioni EMC per Operations Manager, è possibile gestire e monitorare la propria intera catena di servizi IT con una soluzione integrata e automatizzata. È possibile identificare facilmente le cause principali dei problemi relativi a prestazioni e disponibilità e risolverli in modo più rapido, riducendo gli effetti e i costi. I principali vantaggi sono i seguenti:

  - Lo stato di gestione avanzato e facile da usare per la distribuzione di un valore aziendale strategico invece di ordinare manualmente e filtrare gli avvisi confusi.

  - **Risoluzione più rapida**   risolvere i problemi IT e rispondere alle esigenze aziendali più velocemente, riducendo gli effetti e i costi.

  - **Le operazioni**   semplificate impediscono la complessità della it mediante la combinazione di più strumenti di gestione, applicazioni e terminali.

Per ulteriori informazioni, vedere:

[Microsoft System Center Operations Manager](https://go.microsoft.com/fwlink/p/?linkid=243651)

[Soluzioni per Microsoft System Center Operations Manager](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Soluzioni di terze parti

HP Network **Management Center (precedentemente noto come HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) fornisce la gestione integrata dei guasti e delle prestazioni per migliorare la disponibilità e le prestazioni della rete. Network Management Center fa parte della soluzione HP di gestione della rete automatizzata che unifica la gestione dei guasti, delle prestazioni, della configurazione e delle modifiche.

**Cisco Network Management and Automation Products**   for the Enterprise, Cisco dispone di diversi prodotti di gestione, tra cui la soluzione di gestione LAN di CiscoWorks e il modulo di analisi di rete Cisco, per migliorare l'efficienza operativa e ridurre i tempi di inattività della rete. Per ulteriori informazioni su questi prodotti, vedere il sito Web Cisco all' [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html)indirizzo.

Simple Network Management Protocol (SNMP) Simple Network Management Protocol (SNMP) è uno standard di gestione della rete che definisce una strategia per la gestione delle reti TCP/IP. SNMP consente di acquisire informazioni sulla configurazione e sullo stato della rete e di inviare le informazioni a un computer designato per il monitoraggio degli eventi. Questo protocollo di gestione della rete basato su standard utilizza un'architettura distribuita che include gli elementi seguenti:

  - Più nodi gestiti, ognuno con un'entità SNMP chiamata agente che fornisce accesso remoto alla strumentazione di gestione.

  - Almeno un'entità SNMP nota come Manager che esegue le applicazioni di gestione per monitorare e controllare gli elementi gestiti. Gli elementi gestiti sono dispositivi, ad esempio host, router e così via. Sono monitorate e controllate tramite l'accesso alle informazioni di gestione.

  - Un protocollo di gestione, SNMP, viene utilizzato per comunicare informazioni di gestione tra le stazioni di gestione e gli agenti. Le informazioni di gestione si riferiscono a un insieme di oggetti gestiti che vivono in un archivio di informazioni virtuale denominato un MIB (Management Information Base).

<div>


> [!NOTE]  
> Di seguito sono riportati alcuni esempi di soluzioni di monitoraggio della rete di terze parti. Questo elenco non è definitivo e Microsoft non privilegia una soluzione specifica del fornitore. Consultare un provider di servizi di rete o il rispettivo provider di tecnologia per determinare la migliore soluzione di monitoraggio della rete per l'organizzazione.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>Strumenti per il monitoraggio delle prestazioni di rete di singoli server

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 consente agli amministratori di visualizzare le prestazioni di rete dei singoli server tramite il Management Pack di Windows Server 2012: il Management Pack del sistema operativo Windows Server include un Management Pack "performance" che consenta agli amministratori di monitorare le prestazioni della scheda di rete e l'integrità dell'adattatore.

</div>

<div>

## <a name="windows-network-monitor"></a>Windows Network Monitor

Raccoglie, Visualizza, analizza l'utilizzo delle risorse in un server e misura il traffico di rete. Network Monitor esegue esclusivamente il monitoraggio delle attività di rete. Tramite l'acquisizione e l'analisi dei dati di rete e l'utilizzo di tali dati con i registri delle prestazioni, è possibile determinare l'utilizzo della rete, identificare i problemi di rete e prevedere le future esigenze di rete.

Per ulteriori informazioni su Network Monitor 3,4 e per sapere come installare e configurare Network Monitor e acquisire e analizzare i dati, vedere la sessione seguente: Network Monitor 3,3 Overview. Esaminare inoltre il [Blog di Network Monitor](https://blogs.technet.com/b/netmon/).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

