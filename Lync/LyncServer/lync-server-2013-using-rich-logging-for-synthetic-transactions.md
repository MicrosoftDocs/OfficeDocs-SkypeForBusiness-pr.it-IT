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
ms.openlocfilehash: dc43a38a1c6060827755c958ac071fa63608556f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="47a28-102">Utilizzo della registrazione avanzata per le transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a28-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47a28-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="47a28-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="47a28-104">Le transazioni sintetiche (introdotte in Microsoft Lync Server 2010) consentono agli amministratori di verificare che gli utenti siano in grado di completare correttamente attività comuni, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova sulla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="47a28-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="47a28-105">Questi test, che sono inclusi in un set di cmdlet di Windows PowerShell per Lync Server, possono essere eseguiti manualmente da un amministratore oppure possono essere gestiti automaticamente da un'applicazione, ad esempio System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="47a28-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="47a28-106">In Lync Server 2010, le transazioni sintetiche si sono rivelate estremamente utili per aiutare gli amministratori a identificare i problemi del sistema.</span><span class="sxs-lookup"><span data-stu-id="47a28-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="47a28-107">Ad esempio, il cmdlet **Test-CsRegistration** può avvisare gli amministratori del fatto che alcuni utenti hanno riscontrato problemi di registrazione con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47a28-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="47a28-108">Tuttavia, le transazioni sintetiche sono state un po' meno utili per aiutare gli amministratori a determinare il motivo per cui gli utenti hanno difficoltà a registrarsi con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47a28-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="47a28-109">Ciò è dovuto al fatto che le transazioni sintetiche non forniscono informazioni dettagliate sulla registrazione che potrebbero aiutare gli amministratori a risolvere i problemi relativi a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47a28-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="47a28-110">Nella maggior parte dei casi, l'output dettagliato di una transazione sintetica ha fornito informazioni dettagliate che potrebbero consentire a un amministratore di fare un'ipotesi dettagliata sul luogo in cui si è verificato un problema probabile.</span><span class="sxs-lookup"><span data-stu-id="47a28-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="47a28-111">In Microsoft Lync Server 2013, le transazioni sintetiche sono state rielaborate in modo da garantire una registrazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="47a28-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="47a28-112">"Rich logging" significa che, per ogni attività intraprese da una transazione sintetica, verranno registrate informazioni come questa:</span><span class="sxs-lookup"><span data-stu-id="47a28-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="47a28-113">L'ora di inizio dell'attività</span><span class="sxs-lookup"><span data-stu-id="47a28-113">The time that the activity started</span></span>

  - <span data-ttu-id="47a28-114">L'ora di fine dell'attività</span><span class="sxs-lookup"><span data-stu-id="47a28-114">The time that the activity finished</span></span>

  - <span data-ttu-id="47a28-115">Azione eseguita, ad esempio la creazione, l'aggiunta o l'uscita di una conferenza, l'accesso a Lync Server, l'invio di un messaggio istantaneo e così via</span><span class="sxs-lookup"><span data-stu-id="47a28-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="47a28-116">Messaggi informativi, dettagliati, di avviso o di errore generati durante l'esecuzione dell'attività</span><span class="sxs-lookup"><span data-stu-id="47a28-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="47a28-117">Messaggi di registrazione SIP</span><span class="sxs-lookup"><span data-stu-id="47a28-117">SIP registration messages</span></span>

  - <span data-ttu-id="47a28-118">Record delle eccezioni o codici diagnostici generati durante l'esecuzione dell'attività</span><span class="sxs-lookup"><span data-stu-id="47a28-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="47a28-119">Il risultato dell'esecuzione dell'attività</span><span class="sxs-lookup"><span data-stu-id="47a28-119">The net result of running the activity</span></span>

<span data-ttu-id="47a28-120">Queste informazioni vengono generate automaticamente ogni volta che viene eseguita una transazione sintetica.</span><span class="sxs-lookup"><span data-stu-id="47a28-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="47a28-121">Tuttavia, le informazioni non vengono visualizzate o salvate automaticamente in un file di registro.</span><span class="sxs-lookup"><span data-stu-id="47a28-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="47a28-122">Al contrario, gli amministratori che eseguono manualmente una transazione sintetica possono utilizzare il parametro OutLoggerVariable per specificare una variabile di Windows PowerShell in cui verranno archiviate le informazioni.</span><span class="sxs-lookup"><span data-stu-id="47a28-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="47a28-123">Gli amministratori possono quindi utilizzare una coppia di metodi che consentono loro di salvare e/o visualizzare il log RTF in formato XML o HTML.</span><span class="sxs-lookup"><span data-stu-id="47a28-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="47a28-124">Ad esempio, gli amministratori di Lync Server 2010 possono eseguire il cmdlet **Test-CsRegistration** utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="47a28-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="47a28-125">Possono inoltre scegliere se includere il parametro OutLoggerVariable seguito dal nome di variabile desiderato:</span><span class="sxs-lookup"><span data-stu-id="47a28-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="47a28-p105">Non anteporre il carattere $ al nome di variabile. Un nome valido può essere ad esempio RegistrationTest, mentre non lo è il nome $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="47a28-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="47a28-128">Il comando precedente restituisce un contenuto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="47a28-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="47a28-p106">Per questo errore, sono tuttavia disponibili informazioni ancora più dettagliate che non si limitano al messaggio di errore riportato sopra. Per accedere a tali informazioni in formato HTML, specificare un comando simile al seguente in modo da salvare in un file HTML le informazioni archiviate nella variabile RegistrationTest:</span><span class="sxs-lookup"><span data-stu-id="47a28-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="47a28-131">In alternativa, è possibile usare il metodo ToXML() per salvare i dati in un file XML:</span><span class="sxs-lookup"><span data-stu-id="47a28-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="47a28-132">Questi file possono quindi essere visualizzati tramite Internet Explorer, Visual Studio o qualsiasi altra applicazione in grado di aprire file HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="47a28-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="47a28-133">Le transazioni sintetiche eseguite dall'interno di System Center Operations Manager genereranno automaticamente questi file di registro per gli errori.</span><span class="sxs-lookup"><span data-stu-id="47a28-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="47a28-134">Tuttavia, questi registri non verranno generati se l'esecuzione ha esito negativo prima che Windows PowerShell sia in grado di caricare ed eseguire la transazione sintetica.</span><span class="sxs-lookup"><span data-stu-id="47a28-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="47a28-135">Per impostazione predefinita, Lync Server 2013 Salva i file di registro in una cartella non condivisa.</span><span class="sxs-lookup"><span data-stu-id="47a28-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="47a28-136">Per rendere tali registri facilmente accessibili, è necessario condividere questa cartella, ad esempio \\ \\ATL-watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="47a28-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

