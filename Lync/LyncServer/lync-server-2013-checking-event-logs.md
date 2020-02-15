---
title: 'Lync Server 2013: controllo dei registri eventi'
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
ms.openlocfilehash: a15fb690dc213dbe22377b988f82dd59d6eb8a03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Controllo dei registri eventi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-06_

È possibile utilizzare il [Visualizzatore eventi di Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) per visualizzare i registri eventi e ottenere informazioni sugli errori relativi ai servizi, sui problemi di replica in servizi di dominio Active Directory e sugli avvisi relativi alle risorse di sistema, ad esempio la memoria virtuale e lo spazio su disco. Il Visualizzatore eventi è incluso in Windows Server 2008 e 2012.

Nello strumento di registrazione di Lync Server 2013, quando si termina la sessione di debug, fare clic su **Analizza file di registro** per visualizzare i file di registro utilizzando lo strumento Snooper.

Il Visualizzatore eventi gestisce i registri sugli eventi relativi a applicazioni, sicurezza e sistema nel computer. Sia Lync Server 2013 che Windows segnalano gli avvisi e le condizioni di errore nei registri eventi. Pertanto, esaminare i registri eventi tutti i giorni.

Utilizzare il Visualizzatore eventi per:

  - Visualizzare e gestire i registri eventi.

  - Ottenere informazioni sui problemi di hardware, software e di sistema che devono essere risolti.

  - Identificare le tendenze che richiedono un'azione futura.

Un server che esegue Lync Server in un sistema operativo Windows Server registra gli eventi in quattro tipi di registri:

  - **Registri applicazioni il**   registro applicazioni contiene eventi registrati da applicazioni o programmi. Gli sviluppatori determinano gli eventi da registrare. Ad esempio, un programma di database potrebbe registrare un errore di file nel Registro applicazioni. La maggior parte degli eventi relativi a Lync Server 2013 viene visualizzata nel registro applicazioni.

  - **Registri di sicurezza**   il registro di sicurezza registra eventi quali tentativi di accesso validi e non validi oltre agli eventi relativi all'utilizzo delle risorse, ad esempio la creazione, l'apertura o l'eliminazione di file o altri oggetti. Ad esempio, se il controllo all'accesso è abilitato, i tentativi di accedere al sistema vengono registrati nel Registro di protezione.

  - **Registri di sistema**   il registro di sistema contiene gli eventi registrati dai componenti di sistema di Windows. Ad esempio, l'errore di caricamento di un driver o di un altro componente del sistema all'avvio viene registrato nel Registro di sistema. I tipi di eventi registrati dai componenti del sistema sono predeterminati dal server.

  - **Lync Server 2013**   lo strumento di registrazione registra eventi significativi relativi all'autenticazione, alle connessioni e alle azioni degli utenti. Dopo aver abilitato la registrazione diagnostica, è possibile visualizzare le voci del registro nel Visualizzatore eventi.

<div>


> [!NOTE]  
> Non è consigliabile utilizzare le impostazioni di registrazione massime, a meno che non venga richiesto dal servizio supporto tecnico clienti Microsoft. La registrazione massima consente di drenare risorse significative e può fornire molti "falsi positivi", ovvero errori che vengono registrati solo alla registrazione massima ma che sono realmente previsti e che non sono causa di preoccupazione. È inoltre consigliabile non abilitare la registrazione diagnostica in modo permanente. Utilizzarla solo quando si esegue la risoluzione dei problemi.



</div>

All'interno di ogni log del Visualizzatore eventi, Lync Server 2013 registra gli eventi informativi, di avviso e di errore. Monitorare attentamente i registri per tenere conto dei tipi di transazioni eseguite nei server Lync Server 2013. Si consiglia di archiviare periodicamente i registri o di utilizzare il rollover automatico per evitare di esaurire lo spazio sul disco. Poiché i file di registro possono occupare una quantità di spazio limitata, aumentare le dimensioni del registro, ad esempio a 50 MB, e impostarlo su Overwrite affinché il server Lync Server 2013 possa continuare a scrivere nuovi eventi.

È inoltre possibile automatizzare l'amministrazione del registro eventi utilizzando gli strumenti e le tecnologie seguenti:

  - System Center Operations Manager monitora l'integrità e l'utilizzo dei server Lync Server 2013. Lync Server 2013 Management Pack per Operations Manager estende Operations Manager fornendo il monitoraggio specializzato per i server che eseguono Lync Server 2013.

  - Lync Server 2013 Management Pack per Operations Manager monitora standard e Enterprise Edition di Lync Server 2013. Questa versione include anche il Management Pack per la qualità di esperienza (QoE) precedentemente costituito da un Management Pack separato.

I tipi monitorati sono le voci del registro eventi, i contatori delle prestazioni e il monitoraggio dello stato di QoE. Questa versione del Management Pack monitora solo Lync Server 2013 e 2010 e non può essere utilizzata per monitorare Office Communications Server 2007.

Il Management Pack fornisce le caratteristiche seguenti:

  - Avvisi che indicano gli eventi che interessano il servizio

  - Avvisi che indicano la configurazione e altri problemi di impatto non del servizio

  - Monitoraggio dello stato dei servizi di Lync Server

  - Conoscenza del prodotto: causa e risoluzione dei problemi identificati

Per ulteriori informazioni su Lync Server 2013 Management Pack, fare riferimento a [monitoraggio di Lync server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Comb**   eventi lo strumento pettini eventi raccoglie eventi specifici dai registri eventi di più computer in una posizione centrale. Consente di segnalare solo gli ID eventi o le origini eventi specificate. Per ulteriori informazioni su pettine eventi, vedere il sito Web [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) .

**Trigger di evento**   in Windows Server 2012 è possibile "collegare un'attività a questo evento" all'interno del Visualizzatore eventi di Windows, in cui un amministratore può eseguire un programma, inviare un messaggio di posta elettronica o visualizzare un messaggio sullo schermo. Per ulteriori informazioni su questa funzionalità, vedere l'argomento Windows Server 2008 R2 [eseguire un'attività in risposta a un determinato evento](http://technet.microsoft.com/library/cc748900.aspx). È inoltre possibile utilizzare gli strumenti della riga di comando, ad esempio ' EventTrigger. exe ', per creare e query registri eventi e associare programmi con eventi registrati specifici. Utilizzando eventtriggers. exe, è possibile creare trigger di evento che eseguono programmi quando si verificano eventi specifici.

<div>

## <a name="see-also"></a>Vedere anche


[Visualizzatore eventi di Windows](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

