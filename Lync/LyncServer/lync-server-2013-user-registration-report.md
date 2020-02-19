---
title: "Lync Server 2013: rapporto di registrazione dell'utente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77edf04decc6aee7bb0cd292c1b5b0b38139a164
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="5f2b9-102">Rapporto di registrazione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f2b9-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f2b9-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="5f2b9-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5f2b9-104">Il rapporto registrazione utenti fornisce una panoramica delle attività di accesso degli utenti, in particolare informazioni sul numero di utenti che hanno effettuato l'accesso a Microsoft Lync Server 2013 nel corso di un periodo di tempo specificato (ogni ora, giornaliero, settimanale e mensile).</span><span class="sxs-lookup"><span data-stu-id="5f2b9-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="5f2b9-105">Tenere presente che il report indica solo il numero di utenti connessi.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="5f2b9-106">Non indica *quali* utenti hanno effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="5f2b9-107">I rapporti di monitoraggio non forniscono informazioni sugli utenti specifici che utilizzano Lync Server 2013 (e quali no).</span><span class="sxs-lookup"><span data-stu-id="5f2b9-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="5f2b9-108">Tuttavia, è possibile ottenere una stima approssimativa delle informazioni degli utenti utilizzando il rapporto attività utente.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="5f2b9-109">Quando si forniscono informazioni sugli accessi degli utenti, il rapporto di registrazione degli utenti disegna due distinzioni importanti.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="5f2b9-110">In primo luogo, interrompe gli accessi in due categorie principali: gli accessi interni e gli accessi esterni.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="5f2b9-111">Gli accessi interni rappresentano gli utenti che hanno effettuato l'accesso dall'interno del firewall dell'organizzazione, ovvero durante la connessione alla rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="5f2b9-112">Gli accessi esterni rappresentano gli utenti che si sono connessi dall'esterno del firewall tramite un server perimetrale (ad esempio, un utente che ha effettuato l'accesso da un Internet Café conta come un account esterno).</span><span class="sxs-lookup"><span data-stu-id="5f2b9-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="5f2b9-113">Se è necessario sapere quanti utenti accedono dall'esterno del firewall, il rapporto registrazione utenti può fornire queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="5f2b9-114">Inoltre, il rapporto registrazione utenti annota il numero di utenti *attivi* presenti nel corso di un determinato periodo.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="5f2b9-115">Un utente attivo è un utente che ha preso parte a una sessione di messaggistica istantanea, ha partecipato a una riunione di Lync, ha effettuato o ha ricevuto una chiamata telefonica oppure ha utilizzato Lync Server in altro modo durante tale periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="5f2b9-116">Differisce da un utente che ha effettuato l'accesso, ma non si è mai avvalso effettivamente del sistema.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="5f2b9-117">Accesso al rapporto registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="5f2b9-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="5f2b9-p104">Il rapporto registrazione utenti è accessibile solo dalla home page Relazioni monitoraggio e non è collegato ad altri rapporti.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="5f2b9-120">Utilizzo ottimale del rapporto registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="5f2b9-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="5f2b9-121">Dopo aver distribuito Lync Server una domanda comune è la seguente: come è possibile sapere se gli utenti utilizzano effettivamente questa nuova tecnologia?</span><span class="sxs-lookup"><span data-stu-id="5f2b9-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="5f2b9-122">Sebbene presenti qualche limitazione, il rapporto registrazione utenti può contribuire a fornire una risposta al riguardo.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="5f2b9-123">Per determinare se gli utenti utilizzano o meno Lync Server, è necessario eseguire due operazioni.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="5f2b9-124">Innanzitutto, occorre acquisire il valore metrico degli utenti con accesso univoco dal rapporto registrazione utenti.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="5f2b9-125">Questo valore indica il numero di utenti distinti connessi a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="5f2b9-126">In base al confronto, la metrica totale degli accessi indica il numero totale di volte in cui tutti gli utenti hanno effettuato l'accesso a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="5f2b9-127">Si supponga, ad esempio, che Ken si sia connesso a Lync Server cinque volte diverse in un solo giorno.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="5f2b9-128">In tal caso, Ken remario conta come cinque sessioni di accesso separate per la metrica totale degli accessi, ma un solo utente di accesso per la metrica degli utenti di accesso univoco.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="5f2b9-129">Analogamente, non è raro che un utente acceda da più dispositivi o più posizioni.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="5f2b9-130">Ad esempio, un utente può accedere utilizzando il suo computer desktop, il suo computer portatile e può disporre di un telefono IP che accede automaticamente a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="5f2b9-131">In questo esempio, è presente un utente univoco con tre accessi.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="5f2b9-132">Per spiegare ulteriormente la differenza tra accessi totali e accessi univoci, osservare gli accessi relativi a uno specifico periodo nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f2b9-133">Utente</span><span class="sxs-lookup"><span data-stu-id="5f2b9-133">User</span></span></th>
<th><span data-ttu-id="5f2b9-134">Ora accesso</span><span class="sxs-lookup"><span data-stu-id="5f2b9-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f2b9-135">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="5f2b9-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-136">07/07/2012 08.45</span><span class="sxs-lookup"><span data-stu-id="5f2b9-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2b9-137">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="5f2b9-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-138">07/07/2012 08.46</span><span class="sxs-lookup"><span data-stu-id="5f2b9-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f2b9-139">Daniela Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="5f2b9-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-140">07/07/2012 09.17</span><span class="sxs-lookup"><span data-stu-id="5f2b9-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2b9-141">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="5f2b9-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-142">07/07/2012 09.22</span><span class="sxs-lookup"><span data-stu-id="5f2b9-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f2b9-143">Luisa Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="5f2b9-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-144">07/07/2012 09.31</span><span class="sxs-lookup"><span data-stu-id="5f2b9-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5f2b9-p107">Sebbene complessivamente vengano indicati cinque accessi, vi sono in realtà solo due utenti con accesso univoco: Davide Garghentini, che si è connesso tre volte, e Luisa Cazzaniga, che ha effettuato l'accesso due volte. Questa è la differenza tra accessi e utenti con accesso univoco.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="5f2b9-147">Oltre a conoscere il numero di accessi univoci, è necessario conoscere il numero totale di utenti che sono stati abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="5f2b9-148">Tale valore può essere recuperato aprendo Lync Server 2013 Management Shell ed eseguendo il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="5f2b9-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="5f2b9-149">Se il comando precedente restituisce un valore pari a 1.236 e la metrica degli utenti di accesso univoco restituisce un valore medio di 667, che indica che un po' più della metà degli utenti abilitati per Lync si sta effettivamente accedendo al sistema ogni giorno (ovvero 667 diviso per 1.236 , che corrisponde a circa 54%.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5f2b9-150">Tenere presente che le metriche di accesso registrano gli utenti effettivamente connessi durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="5f2b9-151">Non tengono conto degli utenti già connessi al sistema.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="5f2b9-152">Ad esempio, se la metrica degli utenti di accesso univoco Visualizza 667 accessi e sono presenti 1.236 utenti, questo suggerisce che circa la metà degli utenti accedono al sistema.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="5f2b9-153">Tuttavia, si supponga che 300 utenti siano già connessi al sistema al momento in cui si è iniziato a controllare i dati di accesso.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="5f2b9-154">Questo significa che si è effettivamente avuto quasi 1.000 utenti connessi a Lync Server, il che significherebbe che più vicino al 80% degli utenti sono stati connessi.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="5f2b9-155">È inoltre opportuno confrontare i valori delle metriche Utenti con accesso univoco e Utenti attivi univoci.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="5f2b9-156">La metrica Unique Active users indica il numero di utenti univoci che hanno effettivamente utilizzato Lync Server: hanno effettuato una chiamata telefonica, hanno partecipato a una riunione di Lync o sono stati presenti in una sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="5f2b9-157">Si tratta di informazioni utili, perché Microsoft Lync 2013 può essere configurato per l'avvio automatico ogni volta che un utente avvia Windows.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="5f2b9-158">Per questo motivo, potrebbe essere presente un numero elevato di utenti che accedono automaticamente a Lync quando eseguono l'accesso a Windows ogni giorno, ma non utilizzano mai Lync Server in quel periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="5f2b9-159">La metrica degli utenti attivi univoci fornisce anche dati più significativi in un'organizzazione in cui gli utenti in genere non disattivano le finestre alla fine della giornata.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="5f2b9-160">Al contrario, bloccano semplicemente i propri computer e lasciano l'esecuzione di Windows e Lync.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="5f2b9-161">In una situazione simile, si potrebbe finire con pochissimi accessi al giorno perché gli utenti hanno effettuato l'accesso alcuni giorni fa e non sono mai disconnessi.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="5f2b9-162">Tuttavia, gli utenti attivi univoci indicano se gli utenti utilizzano attivamente Lync o un altro client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5f2b9-163">Filtri</span><span class="sxs-lookup"><span data-stu-id="5f2b9-163">Filters</span></span>

<span data-ttu-id="5f2b9-164">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="5f2b9-165">Ad esempio, il rapporto di registrazione degli utenti consente di visualizzare i dati per tutti i pool di registrazione e i server perimetrali o per visualizzare i dati per un singolo pool.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="5f2b9-166">È inoltre possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="5f2b9-167">In tal caso, le registrazioni vengono raggruppate in base all'ora, al giorno, alla settimana o al mese.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="5f2b9-168">Nella tabella seguente sono riportati i filtri che è possibile utilizzare con il rapporto registrazione utenti.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="5f2b9-169">Filtri per il rapporto registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="5f2b9-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f2b9-170">Name</span><span class="sxs-lookup"><span data-stu-id="5f2b9-170">Name</span></span></th>
<th><span data-ttu-id="5f2b9-171">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f2b9-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f2b9-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-p113">Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5f2b9-175">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="5f2b9-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5f2b9-p114">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5f2b9-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5f2b9-178">7/7/2012</span></span></p>
<p><span data-ttu-id="5f2b9-179">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="5f2b9-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5f2b9-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5f2b9-180">7/3/2012</span></span></p>
<p><span data-ttu-id="5f2b9-181">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2b9-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-p115">Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5f2b9-185">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="5f2b9-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5f2b9-p116">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5f2b9-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5f2b9-188">7/7/2012</span></span></p>
<p><span data-ttu-id="5f2b9-189">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="5f2b9-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5f2b9-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5f2b9-190">7/3/2012</span></span></p>
<p><span data-ttu-id="5f2b9-191">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f2b9-192"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-p117">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5f2b9-195">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="5f2b9-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5f2b9-196">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="5f2b9-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5f2b9-197">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="5f2b9-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5f2b9-198">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="5f2b9-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="5f2b9-p118">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con 07/07/2012 come data di inizio e 28/02/2012 come data di fine, verranno visualizzati i dati dalla mezzanotte del 7 agosto 2012 alla mezzanotte del 7 settembre 2012, ovvero i dati per un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2b9-201"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-202">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="5f2b9-203">È possibile selezionare un singolo pool oppure selezionare <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="5f2b9-204">Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5f2b9-205">Metriche</span><span class="sxs-lookup"><span data-stu-id="5f2b9-205">Metrics</span></span>

<span data-ttu-id="5f2b9-206">Nella tabella seguente vengono riportate le informazioni fornite nel rapporto registrazione utenti.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="5f2b9-207">Metrica del rapporto registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="5f2b9-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f2b9-208">Name</span><span class="sxs-lookup"><span data-stu-id="5f2b9-208">Name</span></span></th>
<th><span data-ttu-id="5f2b9-209">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="5f2b9-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5f2b9-210">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f2b9-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f2b9-211"><strong>Orario</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="5f2b9-212"><strong>Giornaliero</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="5f2b9-213"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="5f2b9-214"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-215">No</span><span class="sxs-lookup"><span data-stu-id="5f2b9-215">No</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-p120">Indica l'intervallo di tempo selezionato nella barra degli strumenti per i filtri. Quando applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate a esso relative. Ad esempio, se si utilizza l'intervallo Giornaliero e si fa clic su 07/07/2012, l'attività di registrazione degli utenti relativa a tale data verrà visualizzata suddivisa per ore.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2b9-219"><strong>Totale accessi</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-220">No</span><span class="sxs-lookup"><span data-stu-id="5f2b9-220">No</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-221">Numero totale di sessioni di accesso che hanno avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f2b9-222"><strong>Accessi interni</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-223">No</span><span class="sxs-lookup"><span data-stu-id="5f2b9-223">No</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-224">Numero totale di accessi nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2b9-225"><strong>Accessi esterni</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-226">No</span><span class="sxs-lookup"><span data-stu-id="5f2b9-226">No</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-227">Numero totale di accessi dal di fuori della rete interna, utilizzando il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f2b9-228"><strong>Utenti con accesso univoco</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-229">No</span><span class="sxs-lookup"><span data-stu-id="5f2b9-229">No</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-p121">Numero totale di utenti che hanno avuto almeno una sessione di accesso. Un utente che ha avuto più sessioni di accesso viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f2b9-232"><strong>Utenti attivi univoci</strong></span><span class="sxs-lookup"><span data-stu-id="5f2b9-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="5f2b9-233">No</span><span class="sxs-lookup"><span data-stu-id="5f2b9-233">No</span></span></p></td>
<td><p><span data-ttu-id="5f2b9-p122">Numero totale di utenti che sono stati coinvolti in una sessione peer-to-peer o di conferenza. Un utente che ha avuto più sessioni viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione.</span><span class="sxs-lookup"><span data-stu-id="5f2b9-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

