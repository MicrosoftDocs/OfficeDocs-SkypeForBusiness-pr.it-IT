---
title: "Lync Server 2013: rapporto di registrazione dell'utente"
description: 'Lync Server 2013: rapporto di registrazione degli utenti.'
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
ms.openlocfilehash: 7adb8ef7e94a24f0fd088f12e009fc9d63f3be9d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569752"
---
# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="9fcbb-103">Rapporto di registrazione degli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fcbb-103">User Registration Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fcbb-104">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="9fcbb-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="9fcbb-105">Il rapporto registrazione utenti fornisce una panoramica delle attività di accesso degli utenti, in particolare informazioni sul numero di utenti che hanno effettuato l'accesso a Microsoft Lync Server 2013 nel corso di un periodo di tempo specificato (ogni ora, giornaliero, settimanale e mensile).</span><span class="sxs-lookup"><span data-stu-id="9fcbb-105">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="9fcbb-106">Tenere presente che il report indica solo il numero di utenti connessi.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-106">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="9fcbb-107">Non indica *quali* utenti hanno effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-107">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="9fcbb-108">I rapporti di monitoraggio non forniscono informazioni sugli utenti specifici che utilizzano Lync Server 2013 (e quali no).</span><span class="sxs-lookup"><span data-stu-id="9fcbb-108">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="9fcbb-109">Tuttavia, è possibile ottenere una stima approssimativa delle informazioni degli utenti utilizzando il rapporto attività utente.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-109">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="9fcbb-110">Quando si forniscono informazioni sugli accessi degli utenti, il rapporto di registrazione degli utenti disegna due distinzioni importanti.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-110">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="9fcbb-111">In primo luogo, interrompe gli accessi in due categorie principali: gli accessi interni e gli accessi esterni.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-111">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="9fcbb-112">Gli accessi interni rappresentano gli utenti che hanno effettuato l'accesso dall'interno del firewall dell'organizzazione, ovvero durante la connessione alla rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-112">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="9fcbb-113">Gli accessi esterni rappresentano gli utenti che si sono connessi dall'esterno del firewall tramite un server perimetrale (ad esempio, un utente che ha effettuato l'accesso da un Internet Café conta come un account esterno).</span><span class="sxs-lookup"><span data-stu-id="9fcbb-113">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="9fcbb-114">Se è necessario sapere quanti utenti accedono dall'esterno del firewall, il rapporto registrazione utenti può fornire queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-114">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="9fcbb-115">Inoltre, il rapporto registrazione utenti annota il numero di utenti *attivi* presenti nel corso di un determinato periodo.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-115">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="9fcbb-116">Un utente attivo è un utente che ha preso parte a una sessione di messaggistica istantanea, ha partecipato a una riunione di Lync, ha effettuato o ha ricevuto una chiamata telefonica oppure ha utilizzato Lync Server in altro modo durante tale periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-116">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="9fcbb-117">Differisce da un utente che ha effettuato l'accesso, ma non si è mai avvalso effettivamente del sistema.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-117">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="9fcbb-118">Accesso al rapporto registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="9fcbb-118">Accessing the User Registration Report</span></span>

<span data-ttu-id="9fcbb-p104">Il rapporto registrazione utenti è accessibile solo dalla home page Relazioni monitoraggio e non è collegato ad altri rapporti.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="9fcbb-121">Utilizzo ottimale del rapporto registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="9fcbb-121">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="9fcbb-122">Dopo aver distribuito Lync Server una domanda comune è la seguente: come è possibile sapere se gli utenti utilizzano effettivamente questa nuova tecnologia?</span><span class="sxs-lookup"><span data-stu-id="9fcbb-122">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="9fcbb-123">Sebbene presenti qualche limitazione, il rapporto registrazione utenti può contribuire a fornire una risposta al riguardo.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-123">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="9fcbb-124">Per determinare se gli utenti utilizzano o meno Lync Server, è necessario eseguire due operazioni.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-124">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="9fcbb-125">Innanzitutto, occorre acquisire il valore metrico degli utenti con accesso univoco dal rapporto registrazione utenti.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-125">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="9fcbb-126">Questo valore indica il numero di utenti distinti connessi a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-126">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="9fcbb-127">In base al confronto, la metrica totale degli accessi indica il numero totale di volte in cui tutti gli utenti hanno effettuato l'accesso a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-127">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="9fcbb-128">Si supponga, ad esempio, che Ken si sia connesso a Lync Server cinque volte diverse in un solo giorno.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-128">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="9fcbb-129">In tal caso, Ken remario conta come cinque sessioni di accesso separate per la metrica totale degli accessi, ma un solo utente di accesso per la metrica degli utenti di accesso univoco.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-129">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="9fcbb-130">Analogamente, non è raro che un utente acceda da più dispositivi o più posizioni.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-130">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="9fcbb-131">Ad esempio, un utente può accedere utilizzando il suo computer desktop, il suo computer portatile e può disporre di un telefono IP che accede automaticamente a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-131">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="9fcbb-132">In questo esempio, è presente un utente univoco con tre accessi.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-132">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="9fcbb-133">Per spiegare ulteriormente la differenza tra accessi totali e accessi univoci, osservare gli accessi relativi a uno specifico periodo nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-133">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fcbb-134">Utente</span><span class="sxs-lookup"><span data-stu-id="9fcbb-134">User</span></span></th>
<th><span data-ttu-id="9fcbb-135">Ora accesso</span><span class="sxs-lookup"><span data-stu-id="9fcbb-135">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fcbb-136">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="9fcbb-136">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-137">07/07/2012 08.45</span><span class="sxs-lookup"><span data-stu-id="9fcbb-137">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fcbb-138">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="9fcbb-138">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-139">07/07/2012 08.46</span><span class="sxs-lookup"><span data-stu-id="9fcbb-139">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fcbb-140">Luisa Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="9fcbb-140">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-141">07/07/2012 09.17</span><span class="sxs-lookup"><span data-stu-id="9fcbb-141">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fcbb-142">Davide Garghentini</span><span class="sxs-lookup"><span data-stu-id="9fcbb-142">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-143">07/07/2012 09.22</span><span class="sxs-lookup"><span data-stu-id="9fcbb-143">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fcbb-144">Luisa Cazzaniga</span><span class="sxs-lookup"><span data-stu-id="9fcbb-144">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-145">07/07/2012 09.31</span><span class="sxs-lookup"><span data-stu-id="9fcbb-145">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9fcbb-p107">Sebbene complessivamente vengano indicati cinque accessi, vi sono in realtà solo due utenti con accesso univoco: Davide Garghentini, che si è connesso tre volte, e Luisa Cazzaniga, che ha effettuato l'accesso due volte. Questa è la differenza tra accessi e utenti con accesso univoco.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="9fcbb-148">Oltre a conoscere il numero di accessi univoci, è necessario conoscere il numero totale di utenti che sono stati abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-148">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="9fcbb-149">Tale valore può essere recuperato aprendo Lync Server 2013 Management Shell ed eseguendo il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="9fcbb-149">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="9fcbb-150">Se il comando precedente restituisce un valore pari a 1.236 e la metrica degli utenti di accesso univoco restituisce un valore medio di 667, che indica che un po' più della metà degli utenti abilitati per Lync si sta effettivamente accedendo al sistema ogni giorno, ovvero 667 diviso per 1.236, che è approssimativamente 54%.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-150">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9fcbb-151">Tenere presente che le metriche di accesso registrano gli utenti effettivamente connessi durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-151">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="9fcbb-152">Non tengono conto degli utenti già connessi al sistema.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-152">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="9fcbb-153">Ad esempio, se la metrica degli utenti di accesso univoco Visualizza 667 accessi e sono presenti 1.236 utenti, questo suggerisce che circa la metà degli utenti accedono al sistema.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-153">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="9fcbb-154">Tuttavia, si supponga che 300 utenti siano già connessi al sistema al momento in cui si è iniziato a controllare i dati di accesso.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-154">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="9fcbb-155">Questo significa che si è effettivamente avuto quasi 1.000 utenti connessi a Lync Server, il che significherebbe che più vicino al 80% degli utenti sono stati connessi.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-155">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="9fcbb-156">È inoltre opportuno confrontare i valori delle metriche Utenti con accesso univoco e Utenti attivi univoci.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-156">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="9fcbb-157">La metrica Unique Active users indica il numero di utenti univoci che hanno effettivamente utilizzato Lync Server: hanno effettuato una chiamata telefonica, hanno partecipato a una riunione di Lync o sono stati presenti in una sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-157">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="9fcbb-158">Si tratta di informazioni utili, perché Microsoft Lync 2013 può essere configurato per l'avvio automatico ogni volta che un utente avvia Windows.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-158">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="9fcbb-159">Per questo motivo, potrebbe essere presente un numero elevato di utenti che accedono automaticamente a Lync quando eseguono l'accesso a Windows ogni giorno, ma non utilizzano mai Lync Server in quel periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-159">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="9fcbb-160">La metrica degli utenti attivi univoci fornisce anche dati più significativi in un'organizzazione in cui gli utenti in genere non disattivano le finestre alla fine della giornata.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-160">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="9fcbb-161">Al contrario, bloccano semplicemente i propri computer e lasciano l'esecuzione di Windows e Lync.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-161">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="9fcbb-162">In una situazione simile, si potrebbe finire con pochissimi accessi al giorno perché gli utenti hanno effettuato l'accesso alcuni giorni fa e non sono mai disconnessi.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-162">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="9fcbb-163">Tuttavia, gli utenti attivi univoci indicano se gli utenti utilizzano attivamente Lync o un altro client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-163">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9fcbb-164">Filtri</span><span class="sxs-lookup"><span data-stu-id="9fcbb-164">Filters</span></span>

<span data-ttu-id="9fcbb-165">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-165">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="9fcbb-166">Ad esempio, il rapporto di registrazione degli utenti consente di visualizzare i dati per tutti i pool di registrazione e i server perimetrali o per visualizzare i dati per un singolo pool.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-166">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="9fcbb-167">È inoltre possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-167">You can also choose how data should be grouped.</span></span> <span data-ttu-id="9fcbb-168">In tal caso, le registrazioni vengono raggruppate in base all'ora, al giorno, alla settimana o al mese.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-168">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="9fcbb-169">Nella tabella seguente sono riportati i filtri che è possibile utilizzare con il rapporto registrazione utenti.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-169">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="9fcbb-170">Filtri per il rapporto registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="9fcbb-170">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fcbb-171">Nome</span><span class="sxs-lookup"><span data-stu-id="9fcbb-171">Name</span></span></th>
<th><span data-ttu-id="9fcbb-172">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fcbb-172">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fcbb-173"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-173"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-p113">Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9fcbb-176">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="9fcbb-176">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9fcbb-p114">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9fcbb-179">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9fcbb-179">7/7/2012</span></span></p>
<p><span data-ttu-id="9fcbb-180">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="9fcbb-180">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9fcbb-181">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9fcbb-181">7/3/2012</span></span></p>
<p><span data-ttu-id="9fcbb-182">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-182">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fcbb-183"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-183"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-p115">Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, inserire sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9fcbb-186">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="9fcbb-186">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9fcbb-p116">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9fcbb-189">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9fcbb-189">7/7/2012</span></span></p>
<p><span data-ttu-id="9fcbb-190">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="9fcbb-190">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9fcbb-191">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9fcbb-191">7/3/2012</span></span></p>
<p><span data-ttu-id="9fcbb-192">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-192">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fcbb-193"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-193"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-p117">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9fcbb-196">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="9fcbb-196">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9fcbb-197">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="9fcbb-197">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9fcbb-198">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="9fcbb-198">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="9fcbb-199">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="9fcbb-199">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="9fcbb-p118">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con 07/07/2012 come data di inizio e 28/02/2012 come data di fine, verranno visualizzati i dati dalla mezzanotte del 7 agosto 2012 alla mezzanotte del 7 settembre 2012, ovvero i dati per un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fcbb-202"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-202"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-203">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-203">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="9fcbb-204">È possibile selezionare un singolo pool oppure selezionare <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-204">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="9fcbb-205">Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-205">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9fcbb-206">Metriche</span><span class="sxs-lookup"><span data-stu-id="9fcbb-206">Metrics</span></span>

<span data-ttu-id="9fcbb-207">Nella tabella seguente vengono riportate le informazioni fornite nel rapporto registrazione utenti.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-207">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="9fcbb-208">Metrica del rapporto registrazione utenti</span><span class="sxs-lookup"><span data-stu-id="9fcbb-208">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fcbb-209">Nome</span><span class="sxs-lookup"><span data-stu-id="9fcbb-209">Name</span></span></th>
<th><span data-ttu-id="9fcbb-210">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="9fcbb-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9fcbb-211">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9fcbb-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fcbb-212"><strong>Orario</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="9fcbb-213"><strong>Giornaliero</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="9fcbb-214"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="9fcbb-215"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-216">No</span><span class="sxs-lookup"><span data-stu-id="9fcbb-216">No</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-p120">Indica l'intervallo di tempo selezionato nella barra degli strumenti per i filtri. Quando applicabile, è possibile fare clic su un determinato intervallo di tempo per visualizzare informazioni dettagliate a esso relative. Ad esempio, se si utilizza l'intervallo Giornaliero e si fa clic su 07/07/2012, l'attività di registrazione degli utenti relativa a tale data verrà visualizzata suddivisa per ore.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fcbb-220"><strong>Totale accessi</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-220"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-221">No</span><span class="sxs-lookup"><span data-stu-id="9fcbb-221">No</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-222">Numero totale di sessioni di accesso che hanno avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-222">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fcbb-223"><strong>Accessi interni</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-223"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-224">No</span><span class="sxs-lookup"><span data-stu-id="9fcbb-224">No</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-225">Numero totale di accessi nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-225">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fcbb-226"><strong>Accessi esterni</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-226"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-227">No</span><span class="sxs-lookup"><span data-stu-id="9fcbb-227">No</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-228">Numero totale di accessi dal di fuori della rete interna, utilizzando il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-228">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fcbb-229"><strong>Utenti con accesso univoco</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-229"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-230">No</span><span class="sxs-lookup"><span data-stu-id="9fcbb-230">No</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-p121">Numero totale di utenti che hanno avuto almeno una sessione di accesso. Un utente che ha avuto più sessioni di accesso viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione di accesso.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fcbb-233"><strong>Utenti attivi univoci</strong></span><span class="sxs-lookup"><span data-stu-id="9fcbb-233"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="9fcbb-234">No</span><span class="sxs-lookup"><span data-stu-id="9fcbb-234">No</span></span></p></td>
<td><p><span data-ttu-id="9fcbb-p122">Numero totale di utenti che sono stati coinvolti in una sessione peer-to-peer o di conferenza. Un utente che ha avuto più sessioni viene considerato come un unico utente, al pari di una persona che ha avuto una sola sessione.</span><span class="sxs-lookup"><span data-stu-id="9fcbb-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

