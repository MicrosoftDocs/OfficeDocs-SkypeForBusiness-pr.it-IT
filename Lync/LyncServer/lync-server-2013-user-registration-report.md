---
title: "Lync Server 2013: report di registrazione dell'utente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f56ffd05e677d5106552a9ebcf8a0718efbc100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="66390-102">Report di registrazione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66390-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66390-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="66390-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="66390-104">Il report registrazione utenti offre una panoramica delle attività di accesso degli utenti, in particolare informazioni sul numero di utenti che hanno effettuato l'accesso a Microsoft Lync Server 2013 durante un determinato periodo di tempo (ogni ora, ogni giorno, ogni settimana, ogni mese).</span><span class="sxs-lookup"><span data-stu-id="66390-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="66390-105">Tieni presente che il report indica solo il numero di persone che hanno effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="66390-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="66390-106">Non indica le persone *che* hanno effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="66390-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="66390-107">I report di monitoraggio non contengono informazioni su quali utenti specifici usano Lync Server 2013 (e quali non lo sono).</span><span class="sxs-lookup"><span data-stu-id="66390-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="66390-108">Puoi tuttavia ottenere una stima approssimativa delle informazioni utente usando il report attività utente.</span><span class="sxs-lookup"><span data-stu-id="66390-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="66390-109">Quando si forniscono informazioni sugli accessi degli utenti, il report di registrazione utente estrae due distinzioni importanti.</span><span class="sxs-lookup"><span data-stu-id="66390-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="66390-110">In primo luogo, interrompe gli accessi in due categorie principali: gli accessi interni e gli accessi esterni.</span><span class="sxs-lookup"><span data-stu-id="66390-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="66390-111">Gli accessi interni rappresentano gli utenti che hanno effettuato l'accesso dall'interno del firewall dell'organizzazione, ovvero durante la connessione alla rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="66390-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="66390-112">Gli accessi esterni rappresentano gli utenti che hanno effettuato l'accesso dall'esterno del firewall tramite un server perimetrale (ad esempio, un utente che ha effettuato l'accesso da un Internet Café conta come Accounting esterno).</span><span class="sxs-lookup"><span data-stu-id="66390-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="66390-113">Se è necessario conoscere il numero di utenti che accedono dall'esterno del firewall, è possibile che il report di registrazione dell'utente disponga di queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="66390-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="66390-114">Inoltre, il report registrazione utenti rileva il numero di utenti *attivi* presenti durante un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="66390-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="66390-115">Un utente attivo è un utente che ha preso parte a una sessione di messaggistica istantanea, ha partecipato a una riunione Lync, ha eseguito o ricevuto una telefonata oppure ha usato Lync Server in un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="66390-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="66390-116">Questa operazione è diversa da quella di un utente che ha effettuato l'accesso, ma non ha mai effettivamente usato il sistema.</span><span class="sxs-lookup"><span data-stu-id="66390-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="66390-117">Accesso al report di registrazione utente</span><span class="sxs-lookup"><span data-stu-id="66390-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="66390-118">È possibile accedere al report di registrazione utenti solo dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="66390-118">You access the User Registration Report only from the Monitoring Reports home page.</span></span> <span data-ttu-id="66390-119">Il report di registrazione utente non viene collegato ad altri report.</span><span class="sxs-lookup"><span data-stu-id="66390-119">The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="66390-120">Sfruttare al meglio il report di registrazione utente</span><span class="sxs-lookup"><span data-stu-id="66390-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="66390-121">Dopo aver distribuito Lync Server una domanda comunemente chiesta è la seguente: come è possibile sapere se gli utenti usano effettivamente questa nuova tecnologia?</span><span class="sxs-lookup"><span data-stu-id="66390-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="66390-122">Anche se ha alcune limitazioni a questo proposito, il report di registrazione dell'utente può aiutarti a rispondere a questa domanda.</span><span class="sxs-lookup"><span data-stu-id="66390-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="66390-123">Per determinare se gli utenti usano o meno Lync Server, è necessario eseguire due operazioni.</span><span class="sxs-lookup"><span data-stu-id="66390-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="66390-124">Prima di tutto, ottenere il valore della metrica degli utenti di accesso univoco dal report di registrazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="66390-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="66390-125">Questo valore indica il numero di utenti distinti connessi a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66390-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="66390-126">In base al confronto, la metrica totale degli accessi indica il numero totale di volte in cui tutti gli utenti hanno eseguito l'accesso a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66390-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="66390-127">Supponiamo ad esempio che Ken si sia connesso a Lync Server cinque volte in un solo giorno.</span><span class="sxs-lookup"><span data-stu-id="66390-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="66390-128">In questo caso, Ken si conta come cinque sessioni di accesso separate per la metrica totale degli accessi, ma solo un utente di accesso per la metrica per gli utenti di accesso univoco.</span><span class="sxs-lookup"><span data-stu-id="66390-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="66390-129">Allo stesso modo, non è raro che un utente acceda da più dispositivi o più posizioni.</span><span class="sxs-lookup"><span data-stu-id="66390-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="66390-130">Ad esempio, un utente può accedere usando il suo computer desktop, il suo computer portatile e può avere un telefono IP che accede automaticamente a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66390-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="66390-131">In questo esempio esiste un utente univoco con tre accessi.</span><span class="sxs-lookup"><span data-stu-id="66390-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="66390-132">Per spiegare ulteriormente la differenza tra gli accessi totali e gli accessi univoci, prendere in considerazione gli accessi per un determinato periodo di tempo nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="66390-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66390-133">Utente</span><span class="sxs-lookup"><span data-stu-id="66390-133">User</span></span></th>
<th><span data-ttu-id="66390-134">Ora di accesso</span><span class="sxs-lookup"><span data-stu-id="66390-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66390-135">Ken</span><span class="sxs-lookup"><span data-stu-id="66390-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="66390-136">7/7/2012 8:45 AM</span><span class="sxs-lookup"><span data-stu-id="66390-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66390-137">Ken</span><span class="sxs-lookup"><span data-stu-id="66390-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="66390-138">7/7/2012 8:46 AM</span><span class="sxs-lookup"><span data-stu-id="66390-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66390-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="66390-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="66390-140">7/7/2012 9:17 AM</span><span class="sxs-lookup"><span data-stu-id="66390-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66390-141">Ken</span><span class="sxs-lookup"><span data-stu-id="66390-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="66390-142">7/7/2012 9:22 AM</span><span class="sxs-lookup"><span data-stu-id="66390-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66390-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="66390-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="66390-144">7/7/2012 9:31 AM</span><span class="sxs-lookup"><span data-stu-id="66390-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="66390-145">Si noti che esiste un totale di cinque accessi; Tuttavia, esistono solo due utenti di Access univoci: Ken remario (che ha effettuato l'accesso tre volte) e Pilar Ackerman (che ha effettuato l'accesso due volte).</span><span class="sxs-lookup"><span data-stu-id="66390-145">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice).</span></span> <span data-ttu-id="66390-146">Questa è la differenza tra gli accessi e gli utenti di accesso univoco.</span><span class="sxs-lookup"><span data-stu-id="66390-146">That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="66390-147">Oltre a conoscere il numero di accessi univoci, è necessario conoscere il numero totale di utenti abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66390-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="66390-148">Questo valore può essere recuperato aprendo Lync Server 2013 Management Shell ed eseguendo il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="66390-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="66390-149">Se il comando precedente restituisce un valore di 1.236 e gli utenti di Access univoci Metric restituiscono un valore medio di 667, che suggerisce che un po' più della metà degli utenti abilitati per Lync sia effettivamente l'accesso al sistema ogni giorno (ovvero 667 diviso per 1.236 , che corrisponde a circa 54%).</span><span class="sxs-lookup"><span data-stu-id="66390-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="66390-150">Tieni presente che le metriche di accesso registrano gli utenti che hanno effettivamente effettuato l'accesso durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="66390-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="66390-151">Non tengono traccia degli utenti che hanno già effettuato l'accesso al sistema.</span><span class="sxs-lookup"><span data-stu-id="66390-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="66390-152">Ad esempio, se la metrica degli utenti di accesso univoco Mostra gli accessi di 667 e si hanno utenti di 1.236, il che suggerisce che circa la metà degli utenti accedono al sistema.</span><span class="sxs-lookup"><span data-stu-id="66390-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="66390-153">Supponiamo tuttavia che gli utenti di 300 abbiano già effettuato l'accesso al sistema nel momento in cui hai iniziato a controllare i dati di accesso.</span><span class="sxs-lookup"><span data-stu-id="66390-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="66390-154">Ciò significherebbe che in realtà gli utenti di quasi 1.000 hanno effettuato l'accesso a Lync Server, il che significherebbe che più vicino al 80% degli utenti è stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="66390-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="66390-155">Devi anche confrontare il valore degli utenti di accesso univoco con il valore della metrica utenti attivi univoci.</span><span class="sxs-lookup"><span data-stu-id="66390-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="66390-156">La metrica utenti attivi univoci indica il numero di utenti univoci usati in realtà Lync Server: hanno effettuato una telefonata, hanno partecipato a una riunione Lync o sono stati partecipanti a una sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="66390-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="66390-157">Si tratta di informazioni utili, perché Microsoft Lync 2013 può essere configurato per l'avvio automatico ogni volta che un utente avvia Windows.</span><span class="sxs-lookup"><span data-stu-id="66390-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="66390-158">Per questo motivo, potresti avere un numero elevato di utenti che accedono automaticamente a Lync quando accedono a Windows ogni giorno, ma in realtà non usano mai Lync Server durante tale periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="66390-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="66390-159">La metrica utenti attivi univoci offre anche dati più significativi in un'organizzazione in cui gli utenti in genere non disconnettersi da Windows alla fine della giornata.</span><span class="sxs-lookup"><span data-stu-id="66390-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="66390-160">Al contrario, bloccano semplicemente i propri computer e lasciano in funzione Windows e Lync.</span><span class="sxs-lookup"><span data-stu-id="66390-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="66390-161">In una situazione simile, potresti finire con pochissimi accessi al giorno perché gli utenti hanno effettuato l'accesso diversi giorni fa e non sono mai stati disconnessi.</span><span class="sxs-lookup"><span data-stu-id="66390-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="66390-162">Tuttavia, gli utenti attivi univoci indicano se gli utenti usano attivamente Lync o un altro client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66390-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="66390-163">Filtri</span><span class="sxs-lookup"><span data-stu-id="66390-163">Filters</span></span>

<span data-ttu-id="66390-164">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="66390-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="66390-165">Il report di registrazione utente, ad esempio, consente di visualizzare i dati per tutti i pool di registrazione e i server perimetrali o per visualizzare i dati per un singolo pool.</span><span class="sxs-lookup"><span data-stu-id="66390-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="66390-166">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="66390-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="66390-167">In questo caso, le registrazioni sono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="66390-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="66390-168">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di registrazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="66390-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="66390-169">Filtri report registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="66390-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66390-170">Nome</span><span class="sxs-lookup"><span data-stu-id="66390-170">Name</span></span></th>
<th><span data-ttu-id="66390-171">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66390-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66390-172"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="66390-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-173">Data e ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="66390-173">Start date and time for the time range.</span></span> <span data-ttu-id="66390-174">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="66390-174">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="66390-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="66390-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="66390-176">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="66390-176">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="66390-177">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="66390-177">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="66390-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="66390-178">7/7/2012</span></span></p>
<p><span data-ttu-id="66390-179">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="66390-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="66390-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="66390-180">7/3/2012</span></span></p>
<p><span data-ttu-id="66390-181">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="66390-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66390-182"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="66390-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-183">Data e ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="66390-183">End date and time for the time range.</span></span> <span data-ttu-id="66390-184">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="66390-184">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="66390-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="66390-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="66390-186">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="66390-186">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="66390-187">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="66390-187">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="66390-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="66390-188">7/7/2012</span></span></p>
<p><span data-ttu-id="66390-189">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="66390-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="66390-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="66390-190">7/3/2012</span></span></p>
<p><span data-ttu-id="66390-191">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="66390-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66390-192"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="66390-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-193">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="66390-193">Time interval.</span></span> <span data-ttu-id="66390-194">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66390-194">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="66390-195">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="66390-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="66390-196">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="66390-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="66390-197">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="66390-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="66390-198">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="66390-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="66390-199">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, vengono visualizzati solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="66390-199">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="66390-200">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="66390-200">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66390-201"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="66390-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-202">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="66390-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="66390-203">È possibile selezionare un singolo pool oppure scegliere <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="66390-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="66390-204">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="66390-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="66390-205">Metriche</span><span class="sxs-lookup"><span data-stu-id="66390-205">Metrics</span></span>

<span data-ttu-id="66390-206">Nella tabella seguente sono elencate le informazioni fornite nel report di registrazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="66390-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="66390-207">Metriche del report di registrazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="66390-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66390-208">Nome</span><span class="sxs-lookup"><span data-stu-id="66390-208">Name</span></span></th>
<th><span data-ttu-id="66390-209">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="66390-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="66390-210">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66390-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66390-211"><strong>Oraria</strong></span><span class="sxs-lookup"><span data-stu-id="66390-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="66390-212"><strong>Quotidiana</strong></span><span class="sxs-lookup"><span data-stu-id="66390-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="66390-213"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="66390-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="66390-214"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="66390-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-215">No</span><span class="sxs-lookup"><span data-stu-id="66390-215">No</span></span></p></td>
<td><p><span data-ttu-id="66390-216">Indica l'intervallo di tempo selezionato sulla barra degli strumenti filtro.</span><span class="sxs-lookup"><span data-stu-id="66390-216">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="66390-217">Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="66390-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="66390-218">Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</span><span class="sxs-lookup"><span data-stu-id="66390-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66390-219"><strong>Totale accessi</strong></span><span class="sxs-lookup"><span data-stu-id="66390-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-220">No</span><span class="sxs-lookup"><span data-stu-id="66390-220">No</span></span></p></td>
<td><p><span data-ttu-id="66390-221">Numero totale di sessioni di accesso riuscite.</span><span class="sxs-lookup"><span data-stu-id="66390-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66390-222"><strong>Accessi interni</strong></span><span class="sxs-lookup"><span data-stu-id="66390-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-223">No</span><span class="sxs-lookup"><span data-stu-id="66390-223">No</span></span></p></td>
<td><p><span data-ttu-id="66390-224">Numero totale di accessi all'interno della rete interna.</span><span class="sxs-lookup"><span data-stu-id="66390-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66390-225"><strong>Accessi esterni</strong></span><span class="sxs-lookup"><span data-stu-id="66390-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-226">No</span><span class="sxs-lookup"><span data-stu-id="66390-226">No</span></span></p></td>
<td><p><span data-ttu-id="66390-227">Numero totale di accessi esterni alla rete interna tramite il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="66390-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66390-228"><strong>Utenti di Access univoci</strong></span><span class="sxs-lookup"><span data-stu-id="66390-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-229">No</span><span class="sxs-lookup"><span data-stu-id="66390-229">No</span></span></p></td>
<td><p><span data-ttu-id="66390-230">Numero totale di utenti che avevano almeno una sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="66390-230">Total number of users who had at least one logon session.</span></span> <span data-ttu-id="66390-231">Un utente che ha avuto più sessioni di accesso conta come un solo utente, uguale a quello che ha avuto solo una singola sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="66390-231">A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66390-232"><strong>Utenti attivi univoci</strong></span><span class="sxs-lookup"><span data-stu-id="66390-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="66390-233">No</span><span class="sxs-lookup"><span data-stu-id="66390-233">No</span></span></p></td>
<td><p><span data-ttu-id="66390-234">Numero totale di utenti che hanno partecipato a una sessione peer-to-peer o conferenza.</span><span class="sxs-lookup"><span data-stu-id="66390-234">Total number of users who were involved in a peer-to-peer or conferencing session.</span></span> <span data-ttu-id="66390-235">Un utente che ha avuto più sessioni conta come un utente, lo stesso che ha avuto una sola sessione.</span><span class="sxs-lookup"><span data-stu-id="66390-235">A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

