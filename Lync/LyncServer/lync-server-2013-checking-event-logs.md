---
title: 'Lync Server 2013: controllo dei log eventi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862d419d9db5d8465b3507c40fde32acd01bb659
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Controllo dei log eventi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-06_

È possibile usare il [Visualizzatore eventi di Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) per visualizzare i registri degli eventi e ottenere informazioni sugli errori di servizio, le operazioni di replica in servizi di dominio Active Directory e gli avvisi relativi alle risorse di sistema, ad esempio la memoria virtuale e lo spazio su disco. Il Visualizzatore eventi è incluso in Windows Server 2008 e 2012.

Nello strumento di registrazione di Lync Server 2013, quando si termina la sessione di debug, fare clic su **Analizza file di log** per visualizzare i file di log usando lo strumento Snooper.

Il Visualizzatore eventi mantiene i registri relativi agli eventi di applicazione, sicurezza e sistema nel computer. Sia Lync Server 2013 che Windows segnalano avvisi e condizioni di errore ai log eventi. Di conseguenza, rivedere i registri eventi ogni giorno.

Usare il Visualizzatore eventi per:

  - Visualizzare e gestire i registri eventi.

  - Ottenere informazioni su hardware, software e problemi di sistema che devono essere risolti.

  - Identificare le tendenze che richiedono un'azione futura.

Un server che esegue Lync Server in un sistema operativo Windows Server registra gli eventi in quattro tipi di log:

  - **Registri applicazioni il**   registro applicazioni contiene gli eventi registrati da applicazioni o programmi. Gli sviluppatori determinano gli eventi da registrare. Ad esempio, un programma di database può registrare un errore di file nel log dell'applicazione. La maggior parte degli eventi correlati a Lync Server 2013 viene visualizzata nel registro applicazioni.

  - **Registri di sicurezza**   il registro di sicurezza registra gli eventi, ad esempio tentativi di accesso validi e non validi, oltre agli eventi correlati all'uso delle risorse, ad esempio la creazione, l'apertura o l'eliminazione di file o altri oggetti. Ad esempio, se il controllo di accesso è abilitato, i tentativi di accesso al sistema vengono registrati nel log di sicurezza.

  - **Registri di sistema**   il registro di sistema contiene gli eventi registrati dai componenti di sistema di Windows. Ad esempio, l'errore di un driver o di un altro componente di sistema da caricare durante l'avvio viene registrato nel registro di sistema. I tipi di evento registrati dai componenti di sistema sono predeterminati dal server.

  - **Lync Server 2013**   lo strumento di registrazione registra eventi significativi correlati all'autenticazione, alle connessioni e alle azioni dell'utente. Dopo l'abilitazione della registrazione diagnostica, è possibile visualizzare le voci del log nel Visualizzatore eventi.

<div>


> [!NOTE]  
> Non è consigliabile usare le impostazioni di registrazione massime, a meno che non venga richiesto da Microsoft Customer Support Services. La registrazione massima consente di svuotare risorse significative e può fornire molti "falsi positivi", ovvero errori che vengono registrati solo al massimo della registrazione, ma che sono realmente attesi e non causano preoccupazioni. Ti consigliamo anche di non abilitare la registrazione diagnostica in modo permanente. Usarlo solo per la risoluzione dei problemi.



</div>

All'interno di ogni log del Visualizzatore eventi, Lync Server 2013 registra eventi informativi, di avviso e di errore. Monitorare attentamente questi registri per tenere traccia dei tipi di transazioni effettuate sui server di Lync Server 2013. È consigliabile archiviare periodicamente i log o usare il rollover automatico per evitare di esaurire lo spazio. Poiché i file di log possono occupare una quantità limitata di spazio, aumentare le dimensioni del log, ad esempio in 50 MB, e impostarlo come sovrascrivere in modo che il server Lync Server 2013 possa continuare a scrivere nuovi eventi.

È anche possibile automatizzare l'amministrazione del log eventi usando gli strumenti e le tecnologie seguenti:

  - System Center Operations Manager monitora l'integrità e l'uso dei server di Lync Server 2013. Lync Server 2013 Management Pack per Operations Manager estende Operations Manager fornendo un monitoraggio specializzato per i server che esegue Lync Server 2013.

  - Il Management Pack di Lync Server 2013 per Operations Manager monitora standard e Enterprise Edition di Lync Server 2013. Questa versione incorpora anche il Management Pack di qualità dell'esperienza (QoE) che in precedenza era un Management Pack separato.

I tipi monitorati sono voci del log eventi, contatori delle prestazioni e monitoraggio con stato di QoE. Questa versione del Management Pack monitora solo Lync Server 2013 e 2010 e non può essere usata per monitorare Office Communications Server 2007.

Il Management Pack offre le caratteristiche seguenti:

  - Avvisi che indicano il servizio che interessa gli eventi

  - Avvisi che indicano la configurazione e altri problemi di impatto non del servizio

  - Monitoraggio dello stato dei servizi Lync Server

  - Informazioni sui prodotti: causa e risoluzione dei problemi identificati

Per altre informazioni su Lync Server 2013 Management Pack, vedere [monitoraggio di Lync server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Pettine eventi lo**   strumento pettine eventi raccoglie eventi specifici dai log eventi di diversi computer in una posizione centrale. Consente di segnalare solo gli ID evento o le origini eventi specificati. Per altre informazioni su pettine eventi, vedere il sito Web degli [strumenti di blocco e di gestione degli account](http://go.microsoft.com/fwlink/?linkid=35607) .

**Trigger di eventi**   in Windows Server 2012 è possibile "allegare un'attività a questo evento" nel Visualizzatore eventi di Windows, dove un amministratore può eseguire un programma, inviare un messaggio di posta elettronica o visualizzare un messaggio su schermo. Per altre informazioni su questa funzionalità, vedere l'argomento Windows Server 2008 R2 [eseguire un'attività in risposta a un evento specifico](http://technet.microsoft.com/en-us/library/cc748900.aspx). Puoi anche usare gli strumenti della riga di comando, ad esempio "EventTrigger. exe", per creare e eseguire query sui registri eventi e associare programmi con eventi registrati specifici. Usando eventtriggers. exe, puoi creare trigger di evento che eseguono programmi quando si verificano eventi specifici.

<div>

## <a name="see-also"></a>Vedere anche


[Visualizzatore eventi di Windows](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

