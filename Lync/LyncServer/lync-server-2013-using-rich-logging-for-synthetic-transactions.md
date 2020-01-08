---
title: 'Lync Server 2013: usare la registrazione avanzata per le transazioni sintetiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455d7bcdc14dd4d701d749407759cead0834906f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Uso della registrazione avanzata per le transazioni sintetiche in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Le transazioni sintetiche (introdotte in Microsoft Lync Server 2010) consentono agli amministratori di verificare che gli utenti siano in grado di completare correttamente le attività comuni, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nella rete PSTN (Public Switched Telephone Network). Questi test (confezionati come set di cmdlet di Windows PowerShell per Lync Server) possono essere condotti manualmente da un amministratore oppure possono essere eseguiti automaticamente da un'applicazione, ad esempio System Center Operations Manager.

In Lync Server 2010 le transazioni sintetiche si sono rivelate estremamente utili per aiutare gli amministratori a identificare i problemi del sistema. Il cmdlet **Test-CsRegistration** , ad esempio, potrebbe avvisare gli amministratori del fatto che alcuni utenti avevano difficoltà a registrarsi con Lync Server. Tuttavia, le transazioni sintetiche sono state alquanto meno utili per aiutare gli amministratori a determinare il motivo per cui questi utenti avevano difficoltà a registrarsi con Lync Server. Ciò è dovuto al fatto che le transazioni sintetiche non offrono informazioni dettagliate sulla registrazione che potrebbero aiutare gli amministratori a risolvere i problemi relativi a Lync Server. Nella migliore delle ipotesi, l'output dettagliato di una transazione sintetica ha fornito informazioni dettagliate che potrebbero consentire a un amministratore di indovinare il punto in cui si è verificato un problema.

In Microsoft Lync Server 2013 le transazioni sintetiche sono state riprogettato per consentire una registrazione avanzata. "Rich logging" indica che, per ogni attività eseguita da una transazione sintetica, verranno registrate informazioni come questa:

  - Ora di inizio dell'attività

  - Il tempo di completamento dell'attività

  - Azione eseguita (ad esempio, creazione, partecipazione o uscita di una conferenza; accesso a Lync Server; invio di un messaggio istantaneo e così via)

  - Messaggi informativi, dettagliati, di avviso o di errore generati durante l'esecuzione dell'attività

  - Messaggi di registrazione SIP

  - Record di eccezioni o codici di diagnostica generati quando l'attività è stata eseguita

  - Il risultato netto della gestione dell'attività

Queste informazioni vengono generate automaticamente ogni volta che viene eseguita una transazione sintetica. Le informazioni non vengono tuttavia visualizzate o salvate automaticamente in un file di log. Gli amministratori che hanno invece eseguito manualmente una transazione sintetica possono usare il parametro OutLoggerVariable per specificare una variabile di Windows PowerShell in cui verranno archiviate le informazioni. Da lì gli amministratori possono quindi usare una coppia di metodi che consentono loro di salvare e/o visualizzare il log RTF in formato XML o HTML.

Ad esempio, gli amministratori di Lync Server 2010 possono eseguire il cmdlet **Test-CsRegistration** usando un comando simile al seguente:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Gli amministratori hanno la possibilità di includere il parametro OutLoggerVariable seguito da un nome di variabile scelto:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> Non precedere il nome della variabile con il carattere $. Usare un nome di variabile come RegistrationTest e non $RegistrationTest.

Il comando precedente restituisce il contenuto simile al seguente:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Tuttavia, informazioni molto più dettagliate sono disponibili per questo errore che non solo il messaggio di errore visualizzato sopra. Per accedere a queste informazioni in formato HTML, usare un comando simile al seguente per salvare le informazioni archiviate nella variabile RegistrationTest in un file HTML:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

In alternativa, puoi usare il metodo ToXML () per salvare i dati in un file XML:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Questi file possono quindi essere visualizzati usando Internet Explorer, Visual Studio o qualsiasi altra applicazione in grado di aprire file HTML/XML.

Le transazioni sintetiche eseguite dall'interno di System Center Operations Manager generano automaticamente questi file di log per gli errori. Questi registri non verranno tuttavia generati se l'esecuzione non riesce prima che Windows PowerShell sia in grado di caricare ed eseguire la transazione sintetica.

> [!IMPORTANT]  
> Per impostazione predefinita, Lync Server 2013 Salva i file di log in una cartella non condivisa. Per rendere questi registri facilmente accessibili, è consigliabile condividere questa cartella, ad esempio \\ \\ATL-watcher-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

