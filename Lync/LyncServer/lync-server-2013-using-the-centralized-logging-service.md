---
title: 'Lync Server 2013: uso del servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03b5e4e2582c7b1738f0a6072197643f4df99238
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Uso del servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Il servizio di registrazione centralizzato è una nuova funzionalità di Lync Server 2013. Si tratta di una sostituzione avanzata per gli strumenti **OCSLogger** e **OCSTracer** forniti nelle versioni precedenti. È possibile usare il servizio di registrazione centralizzato per eseguire le attività seguenti:

  - Avviare la registrazione in uno o più computer e pool da un'unica posizione e comando.

  - Interrompere la registrazione in uno o più computer e pool da un'unica posizione e comando.

  - Eseguire ricerche nei registri in uno o più computer e pool per una singola posizione e un comando. È possibile personalizzare il comando Cerca per restituire l'intera aggregazione dei log acquisiti e archiviati in tutti i computer oppure restituire un risultato ritagliato che acquisisce dati specifici.

  - Configurare le sessioni di registrazione nel modo seguente:
    
      - Definire uno **scenario**oppure usare uno scenario predefinito. Uno *scenario* in un servizio di registrazione centralizzato è costituito da un ambito (globale o sito), un nome di scenario per identificare lo scopo dello scenario e uno o più provider. È possibile eseguire due scenari in qualsiasi momento in un computer.
    
      - Utilizzare un *provider* esistente o creare un nuovo provider. Un *provider* definisce la raccolta della sessione di registrazione, il livello di dettaglio, i componenti da tracciare e i contrassegni applicati.
        
        <div>
        

        > [!TIP]  
        > Se si ha familiarità con OCSLogger, i <EM>provider</EM> di termini fanno riferimento alla raccolta di <STRONG>componenti</STRONG> (ad esempio, S4, SipStack), a un <STRONG>tipo di registrazione</STRONG> (ad esempio, WPP, EventLog o Logfile di IIS), a un <STRONG>livello di traccia</STRONG> , ad esempio all, Verbose, debug, e ai <STRONG>Contrassegni</STRONG> , ad esempio TF_COMPONENT, TF_DIAG. Questi elementi sono definiti nel provider (una variabile di Windows PowerShell) e passati al comando servizio registrazione centralizzato.

        
        </div>
    
      - Configurare i computer e i pool da cui si vogliono raccogliere i log.
    
      - Definire l'ambito per la sessione di registrazione dal **sito** delle opzioni (eseguire le acquisizioni di registrazione nei computer solo in questo sito) oppure **globale** (eseguire l'acquisizione di registrazione in tutti i computer della distribuzione).

Il servizio di registrazione centralizzato è estremamente potente e può soddisfare quasi tutte le esigenze di risoluzione dei problemi, ovvero grandi o piccoli. Dall'analisi causa radice ai problemi di prestazioni, il servizio di registrazione centralizzato può essere uno strumento importante per qualsiasi amministratore. Tutti gli esempi vengono visualizzati con Lync Server Management Shell. Esiste un componente della riga di comando per il servizio di registrazione centralizzato denominato **CLSController. exe**. La guida viene fornita per lo strumento della riga di comando tramite lo strumento stesso. Tuttavia, esiste un set limitato di funzioni che è possibile eseguire dalla riga di comando. L'uso di Lync Server Management Shell consente di accedere a un insieme di caratteristiche molto più ampio e configurabile. Quando si usa il servizio di registrazione centralizzato, è consigliabile considerare sempre Lync Server Management Shell come primo e più importante metodo.

Gli argomenti di questa sezione spiegano come usare il servizio di registrazione centralizzato ed esempi di come usare le numerose funzionalità.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Uso di Start per il servizio di registrazione centralizzato per acquisire i registri in Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Uso di stop per il servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Uso della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lettura dei registri di acquisizione dal servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

