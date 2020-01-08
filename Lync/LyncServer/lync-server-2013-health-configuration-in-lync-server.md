---
title: "Lync Server 2013: configurazione dell'integrità in Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="92f2f-102">Configurazione dell'integrità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92f2f-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92f2f-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="92f2f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="92f2f-104">Tra i vari siti Web, gli articoli della Microsoft Knowledge base e gli strumenti di Lync Server Resource Kit, gli amministratori che incontrano problemi durante l'uso di Lync Server non sono mai lontani da un modo per risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="92f2f-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="92f2f-105">Ovviamente non è possibile garantire che non si verifichino problemi con Lync Server 2013 perché Lync Server può essere influenzato da molti aspetti, ad esempio gli arresti anomali della rete e gli errori hardware, che il prodotto stesso non può controllare.</span><span class="sxs-lookup"><span data-stu-id="92f2f-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="92f2f-106">Implementando il monitoraggio dell'integrità, gli amministratori possono identificare potenziali problemi prima che vengano trasformati in problemi reali.</span><span class="sxs-lookup"><span data-stu-id="92f2f-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="92f2f-107">Ad esempio, gli amministratori possono usare il monitoraggio di Lync Server per identificare tendenze e tendenze.</span><span class="sxs-lookup"><span data-stu-id="92f2f-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="92f2f-108">Ad esempio, un aumento costante del numero di conferenze audio/video potrebbe suggerire la necessità di aggiungere capacità prima che il sistema diventi sovraccaricato.</span><span class="sxs-lookup"><span data-stu-id="92f2f-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="92f2f-109">In modo analogo, gli amministratori possono usare System Center Operations Manager per eseguire operazioni come l'emissione di avvisi in tempo reale quando si verificano eventi specificati e per l'esecuzione di transazioni sintetiche che verificano in modo proattivo il sistema.</span><span class="sxs-lookup"><span data-stu-id="92f2f-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="92f2f-110">Le transazioni sintetiche vengono usate in Lync Server per verificare che gli utenti siano in grado di completare correttamente le attività comuni, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nella rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="92f2f-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="92f2f-111">Ad esempio, l'uso periodico di questi test può avvisare i potenziali problemi con gli utenti che accedono a Lync Server e consente di risolvere il problema prima che il team di supporto venga allagato con chiamate provenienti da utenti non in grado di creare una connessione.</span><span class="sxs-lookup"><span data-stu-id="92f2f-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="92f2f-112">Usando System Center Operations Manager per eseguire queste transazioni sintetiche, gli amministratori possono monitorare abitualmente la distribuzione di Lync Server continuamente per 24 ore ogni giorno, senza dover rispondere a qualsiasi avviso che potrebbe essere emesse.</span><span class="sxs-lookup"><span data-stu-id="92f2f-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92f2f-113">Per Lync Server 2013, il Management Pack di System Center Operations Manager è anche in grado di rilevare i problemi "esterni" che possono influire negativamente su Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92f2f-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="92f2f-114">Ad esempio, gli amministratori possono ricevere una notifica se Internet Information Services (IIS) non è in linea, le risorse di sistema in un computer Lync Server scendono al di sotto di un importo specificato o un computer Lync Server sperimenta un errore hardware.</span><span class="sxs-lookup"><span data-stu-id="92f2f-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="92f2f-115">La configurazione dell'integrità in Lync Server 2013 è basata su System Center Operations Manager e sull'uso di Lync Server Management Pack.</span><span class="sxs-lookup"><span data-stu-id="92f2f-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="92f2f-116">Questi Management Pack includono una serie di nuove funzionalità e miglioramenti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="92f2f-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="92f2f-117">**Disponibilità dello scenario da qualsiasi posizione.**</span><span class="sxs-lookup"><span data-stu-id="92f2f-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="92f2f-118">Il Management Pack di Lync Server 2010 ha introdotto il concetto di monitoraggio della disponibilità degli scenari per gli utenti finali con le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="92f2f-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="92f2f-119">In Lync Server 2013 questi agenti hanno più transazioni sintetiche e possono essere eseguiti da un'ampia gamma di posizioni all'interno dell'organizzazione, da postazioni geografiche remote all'esterno dell'organizzazione, dagli strumenti di filiale e da Lync Server 2010 distribuzioni per aggiungere una copertura alle distribuzioni di Edge legacy.</span><span class="sxs-lookup"><span data-stu-id="92f2f-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="92f2f-120">**Registri delle transazioni sintetici.**</span><span class="sxs-lookup"><span data-stu-id="92f2f-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="92f2f-121">Quando una transazione sintetica non riesce, gli amministratori hanno accesso ai log HTML per determinare il risultato non riuscito.</span><span class="sxs-lookup"><span data-stu-id="92f2f-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="92f2f-122">Ciò include la comprensione dell'azione non riuscita, la latenza di ogni azione, la riga di comando usata per eseguire il test e l'errore che si è verificato.</span><span class="sxs-lookup"><span data-stu-id="92f2f-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="92f2f-123">**Maggiore copertura dell'affidabilità delle chiamate.**</span><span class="sxs-lookup"><span data-stu-id="92f2f-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="92f2f-124">Il Management Pack di Lync Server 2010 ha introdotto l'avviso di affidabilità delle chiamate per rilevare gravi problemi di connettività che influiscono sulle chiamate audio degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="92f2f-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="92f2f-125">I Management Pack di Lync Server 2013 aggiungono una copertura per la messaggistica istantanea peer-to-peer e altre funzionalità di conferenza di base per massimizzare la copertura riducendo il rumore.</span><span class="sxs-lookup"><span data-stu-id="92f2f-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="92f2f-126">**Monitoraggio delle dipendenze.**</span><span class="sxs-lookup"><span data-stu-id="92f2f-126">**Dependency monitoring.**</span></span> <span data-ttu-id="92f2f-127">Gli scenari di Lync Server possono avere esito negativo a causa di diversi fattori esterni, ad esempio IIS offline, limitate risorse di CPU e memoria e problemi relativi al disco.</span><span class="sxs-lookup"><span data-stu-id="92f2f-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="92f2f-128">I nuovi Management Pack controllano diverse dipendenze critiche per assicurarsi che gli amministratori siano a conoscenza del loro impatto.</span><span class="sxs-lookup"><span data-stu-id="92f2f-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="92f2f-129">**Report avanzato.**</span><span class="sxs-lookup"><span data-stu-id="92f2f-129">**Enhanced reporting.**</span></span> <span data-ttu-id="92f2f-130">Un set di report per aiutare gli amministratori a valutare la disponibilità dello scenario, pianificare la capacità e vedere quali componenti stanno vivendo la maggior parte dei problemi.</span><span class="sxs-lookup"><span data-stu-id="92f2f-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="92f2f-131">I Management Pack includono anche varie funzionalità che consentono di rilevare e diagnosticare una visibilità in tempo reale nell'integrità della distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92f2f-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="92f2f-132">Queste caratteristiche sono elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="92f2f-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="92f2f-133">Caratteristiche del Management Pack</span><span class="sxs-lookup"><span data-stu-id="92f2f-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92f2f-134">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="92f2f-134">Feature</span></span></th>
<th><span data-ttu-id="92f2f-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92f2f-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92f2f-136">Transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="92f2f-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="92f2f-137">Cmdlet di Windows PowerShell che possono essere eseguiti da varie posizioni per garantire che gli scenari degli utenti finali, ad esempio accesso, presenza, messaggistica istantanea e conferenza siano prontamente disponibili per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="92f2f-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f2f-138">Avvisi di affidabilità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="92f2f-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="92f2f-139">Query di database per i record dei dettagli delle chiamate (CDR).</span><span class="sxs-lookup"><span data-stu-id="92f2f-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="92f2f-140">Questi record vengono scritti dai server front-end per indicare se gli utenti finali sono stati in grado di connettersi a una chiamata o perché una chiamata è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="92f2f-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="92f2f-141">Queste query generano avvisi che indicano quando una vasta gamma di utenti finali sta vivendo problemi di connettività per le chiamate peer-to-peer o per le funzionalità di conferenza di base.</span><span class="sxs-lookup"><span data-stu-id="92f2f-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92f2f-142">Avvisi di qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="92f2f-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="92f2f-143">Query di database che esaminano i report di qualità dell'esperienza (QoE) pubblicati dai client alla fine di ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="92f2f-143">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="92f2f-144">Queste query generano avvisi che individuano scenari in cui gli utenti possono provare una qualità media scadente durante le chiamate e le conferenze.</span><span class="sxs-lookup"><span data-stu-id="92f2f-144">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="92f2f-145">I dati sono basati su metriche chiave, ad esempio la latenza e la perdita di pacchetti, le metriche note per contribuire direttamente alla qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="92f2f-145">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f2f-146">Integrità dei componenti</span><span class="sxs-lookup"><span data-stu-id="92f2f-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="92f2f-147">I singoli componenti del server generano avvisi usando i registri eventi e i contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="92f2f-147">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="92f2f-148">Questi avvisi indicano le condizioni di errore che possono influire gravemente su uno o più scenari degli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="92f2f-148">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="92f2f-149">Questi avvisi possono anche indicare una varietà di altre condizioni di errore, inclusi i servizi non in uso, le alte frequenze di errore, la latenza elevata dei messaggi o i problemi di connettività.</span><span class="sxs-lookup"><span data-stu-id="92f2f-149">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92f2f-150">Integrità delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="92f2f-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="92f2f-151">È possibile che si verifichino errori per diversi motivi esterni.</span><span class="sxs-lookup"><span data-stu-id="92f2f-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="92f2f-152">I Management Pack ora controllano e raccolgono dati per alcune delle dipendenze esterne critiche che potrebbero indicare problemi gravi, tra cui disponibilità di IIS, utilizzo della CPU e della memoria di server e processi e metriche del disco.</span><span class="sxs-lookup"><span data-stu-id="92f2f-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="92f2f-153">Gli avvisi emessi dal sistema sono stati classificati in tre categorie generali:</span><span class="sxs-lookup"><span data-stu-id="92f2f-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="92f2f-154">**Avvisi ad alta priorità.**</span><span class="sxs-lookup"><span data-stu-id="92f2f-154">**High-priority Alerts.**</span></span> <span data-ttu-id="92f2f-155">Questi avvisi indicano le condizioni che causano interruzioni dei servizi per gruppi di utenti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="92f2f-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="92f2f-156">Ad esempio, un errore del componente in un singolo computer non è un avviso ad alta priorità, perché Lync Server 2013 include caratteristiche di disponibilità elevata predefinite.</span><span class="sxs-lookup"><span data-stu-id="92f2f-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="92f2f-157">Al contrario, gli avvisi ad alta priorità rappresentano problemi abbastanza seri "per riattivare gli amministratori durante la notte".</span><span class="sxs-lookup"><span data-stu-id="92f2f-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="92f2f-158">Le interruzioni rilevate dalle transazioni sintetiche e dai servizi offline, ad esempio le conferenze audio/video, si qualificano come avvisi ad alta priorità.</span><span class="sxs-lookup"><span data-stu-id="92f2f-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="92f2f-159">**Avvisi con priorità media.**.</span><span class="sxs-lookup"><span data-stu-id="92f2f-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="92f2f-160">Questi avvisi indicano le condizioni che influiscono su un sottoinsieme di utenti o indicano la degradazione della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="92f2f-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="92f2f-161">Che include problemi come gli errori dei componenti, la latenza nello stabilimento di chiamata o la qualità audio degradata nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="92f2f-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="92f2f-162">Gli avvisi in questa categoria sono con stato e indicano lo stato corrente del problema.</span><span class="sxs-lookup"><span data-stu-id="92f2f-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="92f2f-163">Supponiamo ad esempio che i tempi di creazione delle chiamate superino la soglia di avviso.</span><span class="sxs-lookup"><span data-stu-id="92f2f-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="92f2f-164">Se le chiamate allo stabilimento per il ritorno alla normalità, questi avvisi verranno risolti automaticamente in System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="92f2f-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="92f2f-165">L'aspettativa per questi avvisi è che un amministratore li guarderà nello stesso giorno lavorativo.</span><span class="sxs-lookup"><span data-stu-id="92f2f-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="92f2f-166">**Altri avvisi.**</span><span class="sxs-lookup"><span data-stu-id="92f2f-166">**Other alerts.**</span></span> <span data-ttu-id="92f2f-167">Si tratta di avvisi provenienti da componenti che possono influire su un utente o un sottoinsieme specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="92f2f-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="92f2f-168">Ad esempio, forse il servizio Rubrica non può analizzare l'immissione di Active Directory di un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="92f2f-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="92f2f-169">L'aspettativa per questi avvisi consiste nel fatto che gli amministratori possano accedervi quando hanno tempo disponibile.</span><span class="sxs-lookup"><span data-stu-id="92f2f-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92f2f-170">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="92f2f-170">In This Section</span></span>

  - [<span data-ttu-id="92f2f-171">Configurazione di Lync Server 2013 per l'utilizzo con System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="92f2f-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="92f2f-172">Uso della registrazione avanzata per le transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92f2f-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="92f2f-173">Uso di Microsoft SQL Server 2008 R2 come database di Operations Manager di System Center per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92f2f-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

