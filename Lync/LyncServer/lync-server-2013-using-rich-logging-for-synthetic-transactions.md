---
title: 'Lync Server 2013: utilizzo della registrazione avanzata per le transazioni sintetiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d73bfe085d34e536c5d3b44f1cacca8819de442
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518793"
---
# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Utilizzo della registrazione avanzata per le transazioni sintetiche in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Le transazioni sintetiche (introdotte in Microsoft Lync Server 2010) consentono agli amministratori di verificare che gli utenti siano in grado di completare correttamente attività comuni, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nella rete PSTN (Public Switched Telephone Network). Questi test, che sono inclusi in un set di cmdlet di Windows PowerShell per Lync Server, possono essere eseguiti manualmente da un amministratore oppure possono essere gestiti automaticamente da un'applicazione, ad esempio System Center Operations Manager.

In Lync Server 2010, le transazioni sintetiche si sono rivelate estremamente utili per aiutare gli amministratori a identificare i problemi del sistema. Ad esempio, il cmdlet **Test-CsRegistration** può avvisare gli amministratori del fatto che alcuni utenti hanno riscontrato problemi di registrazione con Lync Server. Tuttavia, le transazioni sintetiche sono state un po' meno utili per aiutare gli amministratori a determinare il motivo per cui gli utenti hanno difficoltà a registrarsi con Lync Server. Ciò è dovuto al fatto che le transazioni sintetiche non forniscono informazioni dettagliate sulla registrazione che potrebbero aiutare gli amministratori a risolvere i problemi relativi a Lync Server. Nella maggior parte dei casi, l'output dettagliato di una transazione sintetica ha fornito informazioni dettagliate che potrebbero consentire a un amministratore di fare un'ipotesi dettagliata sul luogo in cui si è verificato un problema probabile.

In Microsoft Lync Server 2013, le transazioni sintetiche sono state rielaborate in modo da garantire una registrazione avanzata. "Rich logging" significa che, per ogni attività intraprese da una transazione sintetica, verranno registrate informazioni come questa:

  - L'ora di inizio dell'attività

  - L'ora di fine dell'attività

  - Azione eseguita, ad esempio la creazione, l'aggiunta o l'uscita di una conferenza, l'accesso a Lync Server, l'invio di un messaggio istantaneo e così via

  - Messaggi informativi, dettagliati, di avviso o di errore generati durante l'esecuzione dell'attività

  - Messaggi di registrazione SIP

  - Record delle eccezioni o codici diagnostici generati durante l'esecuzione dell'attività

  - Il risultato dell'esecuzione dell'attività

Queste informazioni vengono generate automaticamente ogni volta che viene eseguita una transazione sintetica. Tuttavia, le informazioni non vengono visualizzate o salvate automaticamente in un file di registro. Al contrario, gli amministratori che eseguono manualmente una transazione sintetica possono utilizzare il parametro OutLoggerVariable per specificare una variabile di Windows PowerShell in cui verranno archiviate le informazioni. Gli amministratori possono quindi utilizzare una coppia di metodi che consentono loro di salvare e/o visualizzare il log RTF in formato XML o HTML.

Ad esempio, gli amministratori di Lync Server 2010 possono eseguire il cmdlet **Test-CsRegistration** utilizzando un comando simile al seguente:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Possono inoltre scegliere se includere il parametro OutLoggerVariable seguito dal nome di variabile desiderato:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> Non anteporre il carattere $ al nome di variabile. Un nome valido può essere ad esempio RegistrationTest, mentre non lo è il nome $RegistrationTest.

Il comando precedente restituisce un contenuto simile al seguente:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Per questo errore, sono tuttavia disponibili informazioni ancora più dettagliate che non si limitano al messaggio di errore riportato sopra. Per accedere a tali informazioni in formato HTML, specificare un comando simile al seguente in modo da salvare in un file HTML le informazioni archiviate nella variabile RegistrationTest:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

In alternativa, è possibile usare il metodo ToXML() per salvare i dati in un file XML:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Questi file possono quindi essere visualizzati tramite Internet Explorer, Visual Studio o qualsiasi altra applicazione in grado di aprire file HTML/XML.

Le transazioni sintetiche eseguite dall'interno di System Center Operations Manager genereranno automaticamente questi file di registro per gli errori. Tuttavia, questi registri non verranno generati se l'esecuzione ha esito negativo prima che Windows PowerShell sia in grado di caricare ed eseguire la transazione sintetica.

> [!IMPORTANT]  
> Per impostazione predefinita, Lync Server 2013 Salva i file di registro in una cartella non condivisa. Per rendere tali registri facilmente accessibili, è necessario condividere questa cartella, ad esempio \\ \\ ATL-watcher-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

