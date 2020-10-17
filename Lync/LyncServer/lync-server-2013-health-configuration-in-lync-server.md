---
title: "Lync Server 2013: configurazione dell'integrità in Lync Server"
description: "Lync Server 2013: configurazione dell'integrità in Lync Server."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 999a6d5401cb34382a4120f9255c91c846f72422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552852"
---
# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="11285-103">Configurazione dell'integrità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11285-103">Health configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11285-104">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="11285-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="11285-105">Tra i diversi siti Web, gli articoli della Microsoft Knowledge base e gli strumenti di Lync Server Resource Kit, gli amministratori che riscontrano problemi durante l'esecuzione di Lync Server non sono mai lontani da un modo per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="11285-105">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="11285-106">Non è ovviamente possibile garantire che non vengano mai riscontrati problemi con Lync Server 2013 perché Lync Server può essere influenzato da molte operazioni, ad esempio arresti anomali della rete e hardware, che il prodotto stesso non è in grado di controllare.</span><span class="sxs-lookup"><span data-stu-id="11285-106">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="11285-107">Implementando il monitoraggio dello stato, gli amministratori possono identificare potenziali problemi prima che diventino problemi a tutti gli effetti.</span><span class="sxs-lookup"><span data-stu-id="11285-107">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="11285-108">Ad esempio, gli amministratori possono utilizzare il monitoraggio di Lync Server per identificare tendenze e tendenze.</span><span class="sxs-lookup"><span data-stu-id="11285-108">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="11285-109">Un aumento costante del numero di conferenze audio/video ad esempio può suggerire la necessità di aggiungere capacità prima che si verifichi un sovraccarico del sistema.</span><span class="sxs-lookup"><span data-stu-id="11285-109">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="11285-110">Analogamente, gli amministratori possono utilizzare System Center Operations Manager per eseguire operazioni quali gli avvisi in tempo reale quando si verificano gli eventi specificati e l'esecuzione di transazioni sintetiche che verificano il sistema in modo proattivo.</span><span class="sxs-lookup"><span data-stu-id="11285-110">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="11285-111">Le transazioni sintetiche vengono utilizzate in Lync Server per verificare che gli utenti siano in grado di completare correttamente attività comuni, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nella rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="11285-111">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="11285-112">Ad esempio, l'esecuzione periodica di questi test può avvisare l'utente di eventuali problemi con gli utenti che accedono a Lync Server e fornire la possibilità di risolvere il problema prima che il team di supporto sia inondato da chiamate provenienti da utenti che non sono in grado di effettuare una connessione.</span><span class="sxs-lookup"><span data-stu-id="11285-112">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="11285-113">Tramite System Center Operations Manager per eseguire queste transazioni sintetiche, gli amministratori possono monitorare periodicamente la distribuzione di Lync Server continuamente per 24 ore al giorno, senza dover rispondere a qualsiasi avviso che potrebbe essere emesso.</span><span class="sxs-lookup"><span data-stu-id="11285-113">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11285-114">Per Lync Server 2013, il Management Pack per System Center Operations Manager è anche in grado di rilevare problemi "esterni" che possono influire negativamente su Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11285-114">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="11285-115">Ad esempio, gli amministratori possono ricevere una notifica se Internet Information Services (IIS) non è in linea, le risorse di sistema in un computer Lync Server scendono al di sotto di un determinato importo oppure un computer con Lync Server subisce un errore hardware.</span><span class="sxs-lookup"><span data-stu-id="11285-115">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="11285-116">La configurazione dell'integrità in Lync Server 2013 è basata su System Center Operations Manager e sull'utilizzo dei Management Pack di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11285-116">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="11285-117">Tali Management Pack includono diverse nuove funzionalità e miglioramenti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="11285-117">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="11285-118">**Disponibilità degli scenari da qualsiasi posizione.**</span><span class="sxs-lookup"><span data-stu-id="11285-118">**Scenario availability from any location.**</span></span> <span data-ttu-id="11285-119">Il Management Pack di Lync Server 2010 introduce il concetto di monitoraggio della disponibilità degli scenari degli utenti finali con transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="11285-119">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="11285-120">In Lync Server 2013, questi agenti dispongono di transazioni più sintetiche e possono essere eseguiti da diverse posizioni all'interno dell'organizzazione, dalle posizioni geografiche remote esterne all'organizzazione, dagli strumenti di succursale e dalle distribuzioni di Lync Server 2010 per aggiungere una copertura alle distribuzioni di Edge legacy.</span><span class="sxs-lookup"><span data-stu-id="11285-120">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="11285-121">**Log delle transazioni sintetiche.**</span><span class="sxs-lookup"><span data-stu-id="11285-121">**Synthetic transaction logs.**</span></span> <span data-ttu-id="11285-122">Quando una transazione sintetica ha esito negativo, gli amministratori hanno accesso a log HTML utili per determinare cosa sia accaduto.</span><span class="sxs-lookup"><span data-stu-id="11285-122">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="11285-123">Tra le informazioni fornite vi sono l'azione non riuscita, la latenza di ogni azione, la riga di comando utilizzata per eseguire il test e l'errore verificatosi.</span><span class="sxs-lookup"><span data-stu-id="11285-123">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="11285-124">**Maggiore copertura per segnalare l'affidabilità delle chiamate.**</span><span class="sxs-lookup"><span data-stu-id="11285-124">**Increased call reliability coverage.**</span></span> <span data-ttu-id="11285-125">Lync Server 2010 Management Pack ha introdotto l'avviso di affidabilità delle chiamate per rilevare gravi problemi di connettività che influiscono sulle chiamate audio degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="11285-125">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="11285-126">I Management Pack di Lync Server 2013 aggiungono una copertura per la messaggistica istantanea peer-to-peer e altre funzionalità di base per le conferenze per massimizzare la copertura durante la riduzione del rumore.</span><span class="sxs-lookup"><span data-stu-id="11285-126">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="11285-127">**Monitoraggio delle dipendenze.**</span><span class="sxs-lookup"><span data-stu-id="11285-127">**Dependency monitoring.**</span></span> <span data-ttu-id="11285-128">Gli scenari di Lync Server possono avere esito negativo a causa di una serie di fattori esterni, ad esempio IIS non in linea, limitate risorse di memoria e CPU e problemi relativi al disco.</span><span class="sxs-lookup"><span data-stu-id="11285-128">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="11285-129">I nuovi Management Pack verificano diverse dipendenze critiche in modo che gli amministratori siano consapevoli del relativo impatto.</span><span class="sxs-lookup"><span data-stu-id="11285-129">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="11285-130">**Miglioramento dei report.**</span><span class="sxs-lookup"><span data-stu-id="11285-130">**Enhanced reporting.**</span></span> <span data-ttu-id="11285-131">È disponibile una serie di report che consentono agli amministratori di stimare la disponibilità degli scenari, pianificare la capacità e controllare i componenti su cui si verifica la maggior parte dei problemi.</span><span class="sxs-lookup"><span data-stu-id="11285-131">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="11285-132">I Management Pack includono anche una serie di funzionalità che consentono di rilevare e diagnosticare una visibilità in tempo reale nell'integrità della distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11285-132">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="11285-133">Queste funzionalità sono elencate nella tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="11285-133">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="11285-134">Funzionalità dei Management Pack</span><span class="sxs-lookup"><span data-stu-id="11285-134">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11285-135">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="11285-135">Feature</span></span></th>
<th><span data-ttu-id="11285-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11285-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11285-137">Transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="11285-137">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="11285-138">Cmdlet di Windows PowerShell che possono essere eseguiti da diverse posizioni per garantire che gli scenari degli utenti finali, ad esempio l'accesso, la presenza, la messaggistica istantanea e le conferenze, siano prontamente disponibili per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="11285-138">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11285-139">Avvisi di affidabilità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="11285-139">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="11285-140">Query di database per le registrazioni dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="11285-140">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="11285-141">Questi record vengono scritti dai Front End Server per riflettere se gli utenti finali sono stati in grado di connettersi a una chiamata o perché una chiamata è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="11285-141">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="11285-142">Queste query generano avvisi che segnalano quando un numero elevato di utenti finali ha problemi di connettività per chiamate peer-to-peer o funzionalità di conferenza di base.</span><span class="sxs-lookup"><span data-stu-id="11285-142">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11285-143">Avvisi sulla qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="11285-143">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="11285-p112">Query di database che esaminano i report sulla qualità percepita dagli utenti (QoE) pubblicati dai client alla fine di ogni chiamata. Queste query generano avvisi che segnalano gli scenari in cui è probabile che gli utenti percepiscano una scarsa qualità multimediale durante le chiamate e le conferenze. I dati si basano su metriche chiave, come la latenza e la perdita di pacchetti, che notoriamente contribuiscono in modo diretto alla qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="11285-p112">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call. These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences. The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11285-147">Stato dei componenti</span><span class="sxs-lookup"><span data-stu-id="11285-147">Component Health</span></span></p></td>
<td><p><span data-ttu-id="11285-p113">I singoli componenti server generano avvisi mediante log eventi e contatori delle prestazioni. Questi avvisi indicano le condizioni di errore che possono influire in modo significativo su uno o più scenari degli utenti finali. Questi avvisi inoltre indicano diverse altre condizioni di errore, tra cui i servizi non in esecuzione, alte percentuali di problemi, un'elevata latenza dei messaggi o i problemi di connettività.</span><span class="sxs-lookup"><span data-stu-id="11285-p113">Individual server components raise alerts by using event logs and performance counters. These alerts indicate failure conditions that can severely impact one or more end user scenarios. These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11285-151">Stato delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="11285-151">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="11285-152">I problemi possono essere causati da una vasta gamma di motivi esterni.</span><span class="sxs-lookup"><span data-stu-id="11285-152">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="11285-153">I Management Pack ora eseguono il monitoraggio e raccolgono dati per alcune delle dipendenze esterne più importanti che possono indicare seri problemi, inclusi la disponibilità di IIS, l'utilizzo di CPU e memoria dei server e dei processi e le metriche del disco.</span><span class="sxs-lookup"><span data-stu-id="11285-153">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11285-154">Gli avvisi generati dal sistema sono stati classificati in tre categorie generali:</span><span class="sxs-lookup"><span data-stu-id="11285-154">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="11285-155">**Avvisi di alta priorità.**</span><span class="sxs-lookup"><span data-stu-id="11285-155">**High-priority Alerts.**</span></span> <span data-ttu-id="11285-156">Questi avvisi indicano le condizioni che causeranno interruzioni dei servizi per gruppi estesi di utenti.</span><span class="sxs-lookup"><span data-stu-id="11285-156">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="11285-157">Ad esempio, un errore del componente su un singolo computer non è un avviso di priorità alta perché Lync Server 2013 dispone di funzionalità di disponibilità elevata incorporate.</span><span class="sxs-lookup"><span data-stu-id="11285-157">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="11285-158">Gli avvisi di alta priorità rappresentano invece problemi sufficientemente gravi da richiedere l'attenzione degli amministratori anche in piena notte.</span><span class="sxs-lookup"><span data-stu-id="11285-158">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="11285-159">I problemi rilevati dalle transazioni sintetiche e i servizi offline, ad esempio per conferenze audio/video, sono considerati avvisi di alta priorità.</span><span class="sxs-lookup"><span data-stu-id="11285-159">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="11285-160">**Avvisi di media priorità.**</span><span class="sxs-lookup"><span data-stu-id="11285-160">**Medium-priority alerts.**.</span></span> <span data-ttu-id="11285-161">Questi avvisi indicano le condizioni che incidono su un sottoinsieme di utenti o segnalano un degrado della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="11285-161">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="11285-162">Sono inclusi problemi quali guasti dei componenti, latenza per stabilire una chiamata o un peggioramento della qualità audio durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="11285-162">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="11285-163">Gli avvisi di questa categoria sono con stato e indicano lo stato corrente del problema.</span><span class="sxs-lookup"><span data-stu-id="11285-163">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="11285-164">Si supponga ad esempio che i tempi per stabilire una chiamata superino la soglia di avviso.</span><span class="sxs-lookup"><span data-stu-id="11285-164">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="11285-165">Se l'establishment di chiamata torna alla normalità, questi avvisi verranno risolti automaticamente in System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="11285-165">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="11285-166">È prevedibile che un amministratore esamini tali avvisi nello stesso giorno lavorativo.</span><span class="sxs-lookup"><span data-stu-id="11285-166">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="11285-167">**Altri avvisi.**</span><span class="sxs-lookup"><span data-stu-id="11285-167">**Other alerts.**</span></span> <span data-ttu-id="11285-168">Sono avvisi di componenti che possono incidere su un utente o un sottoinsieme specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="11285-168">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="11285-169">Ad esempio, il servizio Rubrica non riesce ad analizzare la voce di Active Directory di un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="11285-169">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="11285-170">È prevedibile che gli amministratori si occupino di tali avvisi quando hanno tempo a disposizione.</span><span class="sxs-lookup"><span data-stu-id="11285-170">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="11285-171">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="11285-171">In This Section</span></span>

  - [<span data-ttu-id="11285-172">Configurazione di Lync Server 2013 per l'utilizzo con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="11285-172">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="11285-173">Utilizzo della registrazione avanzata per le transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11285-173">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="11285-174">Utilizzo di Microsoft SQL Server 2008 R2 come database di System Center Operations Manager per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11285-174">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

