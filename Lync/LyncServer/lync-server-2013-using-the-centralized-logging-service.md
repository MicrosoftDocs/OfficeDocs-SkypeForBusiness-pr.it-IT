---
title: 'Lync Server 2013: utilizzo del servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565c71a2a4e52b50b4807d7a5c5673e24c0a1a71
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a>Utilizzo del servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Il servizio di registrazione centralizzato è una nuova funzionalità di Lync Server 2013. È una versione sostitutiva e migliorata degli strumenti **OCSLogger** e **OCSTracer** presenti nelle versioni precedenti. È possibile utilizzare il servizio di registrazione centralizzato per eseguire le attività seguenti:

  - Avviare la registrazione su uno o più computer e pool da una località singola, con un singolo comando.

  - Interrompere la registrazione su uno o più computer e pool da una località singola, con un singolo comando.

  - Cercare registri su uno o più computer e pool per località singola o singolo comando. È possibile personalizzare il comando di ricerca affinché restituisce l'intera aggregazione di registri raccolti e archiviati su tutti i computer, o affinché restituisca un risultato più filtrato, contenente soltanto dati specifici.

  - Configurare sessioni di registrazione come segue:
    
      - Definire uno **Scenario**, oppure utilizzarne uno predefinito. Uno *scenario* nel servizio di registrazione centralizzato è costituito da un ambito (globale o sito), un nome dello scenario per identificare lo scopo dello scenario e uno o più provider. È possibile eseguire due scenari contemporaneamente su un computer.
    
      - Utilizzare un *provider* esistente, o crearne uno nuovo. Un *provider* definisce cosa viene raccolto da una sessione di registrazione, nonché il livello di dettagli, i componenti da tracciare e i contrassegni applicati.
        
        <div>
        

        > [!TIP]  
        > Se si ha familiarità con OCSLogger, il termine <EM>provider</EM> fa riferimento alla raccolta di <STRONG>componenti</STRONG> (ad esempio, S4, SIPStack), un <STRONG>tipo di registrazione</STRONG> (ad esempio, WPP, EventLog o IIS logfile), un <STRONG>livello di traccia</STRONG> (ad esempio, All, verbose, debug) e <STRONG>contrassegni</STRONG> (ad esempio, TF_COMPONENT, TF_DIAG). Questi elementi sono definiti nel provider (variabile di Windows PowerShell) e vengono passati al comando del servizio di registrazione centralizzato.

        
        </div>
    
      - Configurare i computer e i pool dai quali si desidera raccogliere registri.
    
      - Definire l'ambito della sessione di registrazione dalle opzioni **Sito** (per eseguire raccolte di registri su computer che si trovano su quel sito soltanto), o **Globale** (per eseguire raccolte di registri su tutti i computer della distribuzione).

Il servizio di registrazione centralizzato è estremamente potente e può soddisfare quasi tutte le esigenze per la risoluzione dei problemi, ovvero grandi o piccole dimensioni. Dall'analisi delle cause radice ai problemi di prestazioni, il servizio di registrazione centralizzato può essere uno strumento importante per tutti gli amministratori. Tutti gli esempi vengono visualizzati utilizzando Lync Server Management Shell. È presente un componente della riga di comando per il servizio di registrazione centralizzato denominato **CLSController. exe**. Allo strumento da riga di comando viene offerto supporto dallo strumento stesso. Tuttavia, le funzioni eseguibili dalla riga di comando sono limitate. Utilizzando Lync Server Management Shell, è possibile accedere a un insieme di caratteristiche molto più grande e configurabile. Quando si utilizza il servizio di registrazione centralizzato, è consigliabile considerare sempre Lync Server Management Shell come primo e principale metodo.

Negli argomenti di questa sezione viene illustrato come utilizzare il servizio di registrazione centralizzato ed esempi di utilizzo delle numerose funzionalità.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [Gestione delle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [Utilizzo di Start per il servizio di registrazione centralizzato per l'acquisizione dei log in Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [Utilizzo di stop per il servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [Utilizzo della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [Lettura dei registri di acquisizione dal servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

