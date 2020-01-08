---
title: 'Lync Server 2013: distribuzione del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>Distribuzione del monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-17_

Sono state apportate modifiche importanti all'infrastruttura di monitoraggio di Microsoft Lync Server 2013, a partire dal fatto che il ruolo del server di monitoraggio è deprecato. Invece dei ruoli distinti del server di monitoraggio (che in genere richiedevano alle organizzazioni di configurare computer dedicati per fungere da server di monitoraggio), i servizi di monitoraggio sono ora collocati in ogni server front-end. Tra le altre cose, questa modifica consente di:

  - Ridurre il numero di ruoli del server necessari per l'implementazione di Lync Server 2013. In questo caso, il decremento del ruolo del server di monitoraggio consente anche di ridurre i costi eliminando la necessità di gestire server dedicati per il monitoraggio.

  - Ridurre la complessità della configurazione e dell'amministrazione di Lync Server. La collocazione automatica dei servizi di monitoraggio in ogni server front-end non è più necessario installare, configurare e gestire il ruolo del server di monitoraggio.

<div>


> [!NOTE]  
> Il ruolo del server di archiviazione è stato deprecato anche in Lync Server 2013. Come i servizi di monitoraggio, i servizi di archiviazione di Lync Server 2013 sono ora collocati in ogni server front-end. Questa operazione è importante da notare semplicemente perché il monitoraggio e l'archiviazione condividono spesso la stessa istanza di database di SQL Server.



</div>

Come si può prevedere, queste modifiche hanno un impatto importante sul modo in cui vengono installati e gestiti i servizi di monitoraggio. Poiché il ruolo del server di monitoraggio non esiste più, ad esempio, il nodo server di monitoraggio è stato rimosso dal generatore di topologia di Lync Server. a sua volta, questo significa che non è più possibile usare la procedura guidata nuovo server di monitoraggio di generatore di topologia per aggiungere un nuovo server di monitoraggio alla topologia. (La procedura guidata non esiste più) Al contrario, in genere implementiamo i servizi di monitoraggio all'interno della topologia completando i due passaggi seguenti:

1.  Abilitazione del monitoraggio contemporaneamente alla configurazione di un nuovo pool di Lync Server. In Lync Server 2013 il monitoraggio viene abilitato o disabilitato in base al pool. Tieni presente che puoi abilitare il monitoraggio per un pool senza raccogliere effettivamente i dati di monitoraggio, un processo spiegato nella sezione configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza di questa documentazione.

2.  Associazione di un archivio di monitoraggio (ovvero un database di monitoraggio) con il nuovo pool. Tieni presente che un singolo archivio di monitoraggio può essere associato a più pool. A seconda del numero di utenti ospitati nei pool di registrar, significa che non è necessario configurare un database di monitoraggio separato per ogni pool. Un singolo archivio di monitoraggio può invece essere usato da più pool.

Anche se spesso è più semplice abilitare il monitoraggio quando si crea un nuovo pool, è anche possibile creare un nuovo pool con il monitoraggio disabilitato. In questo caso, puoi usare il generatore di topologie in seguito per abilitare il servizio: generatore di topologie consente di abilitare o disabilitare il monitoraggio per un pool o di associare un pool a un altro archivio di monitoraggio. Tenere presente che, anche se non è più presente un ruolo di monitoraggio del server, sarà comunque necessario creare uno o più archivi di monitoraggio: i database di backend usati per archiviare i dati raccolti dal servizio di monitoraggio. Questi database back-end possono essere creati usando Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.

<div>


> [!NOTE]  
> Se il monitoraggio è stato abilitato per un pool, è possibile disabilitare il processo di raccolta dei dati di monitoraggio senza dover modificare la topologia: Lync Server Management Shell consente di disabilitare (e quindi riabilitare) la registrazione dettagli chiamata (CDR) o la qualità raccolta dati di Experience (QoE). Per altre informazioni, vedere la sezione configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza di questo documento.



</div>

Un altro importante miglioramento per il monitoraggio in Lync Server 2013 è il fatto che i report di monitoraggio di Lync Server ora supportano IPv6: i report che usano il campo indirizzo IP visualizzeranno indirizzi IPv4 o IPv6 in base a: 1) la query SQL in uso; e 2) dove l'indirizzo IPv6 viene archiviato o meno nel database di monitoraggio.

<div>


> [!NOTE]  
> Verificare che il tipo di avvio del servizio di SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza SQL che tiene i database di monitoraggio, in modo che i processi di manutenzione di SQL Server di monitoraggio predefiniti possano essere eseguiti nella loro base pianificata sotto il controllo del servizio agente SQL Server.



</div>

Questa documentazione illustra il processo di installazione e configurazione dei report di monitoraggio e monitoraggio per Lync Server 2013. La documentazione include istruzioni dettagliate che ti aiuteranno a:

  - Abilitare il monitoraggio nella topologia e associare un archivio di monitoraggio a un pool Front-end.

  - Installare SQL Server Reporting Services e i report di monitoraggio di Lync Server. I report di monitoraggio sono report preconfigurati che contengono visualizzazioni diverse delle informazioni archiviate in un database di monitoraggio.

  - Configurare la raccolta di dati per la registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE). La registrazione dei dettagli delle chiamate consente di tenere traccia dell'uso delle funzionalità di Lync Server, ad esempio chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni. Le metriche QoE tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, inclusi i problemi relativi al numero di pacchetti di rete persi, al rumore di fondo e alla quantità di "jitter" (differenze nel ritardo del pacchetto).

  - Eliminare manualmente i record CDR e/o QoE dal database di monitoraggio.

</div>

<span> </span>

</div>

</div>

</div>

