---
title: 'Lync Server 2013: report inventario IP Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb9bb9a3ae48c8bf2fc9a5122e1b8004e0f6019
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="df5be-102">Report sull'inventario del telefono IP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df5be-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df5be-103">_**Argomento Ultima modifica:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="df5be-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="df5be-104">Il report inventario IP Phone riporta le informazioni sui telefoni IP attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="df5be-104">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization.</span></span> <span data-ttu-id="df5be-105">Il report inventario IP include un elenco dettagliato dei telefoni IP effettivamente usati durante il periodo di riferimento specificato.</span><span class="sxs-lookup"><span data-stu-id="df5be-105">The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period.</span></span> <span data-ttu-id="df5be-106">Tra le altre cose, questo report consente agli amministratori di sapere se sono ancora in uso vecchi telefoni obsoleti che devono essere sostituiti. può anche avvisare gli amministratori del fatto che nell'organizzazione sono presenti telefoni costosi che raramente vengono usati.</span><span class="sxs-lookup"><span data-stu-id="df5be-106">Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used.</span></span> <span data-ttu-id="df5be-107">Questo tipo di informazioni può essere prezioso quando arriva il momento di acquistare nuovi telefoni o di ridistribuire i telefoni esistenti.</span><span class="sxs-lookup"><span data-stu-id="df5be-107">That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones.</span></span> <span data-ttu-id="df5be-108">Ad esempio, un utente che usa raramente il suo telefono costoso può essere invitato a scambiare telefoni con un utente che usa il suo telefono molto più spesso.</span><span class="sxs-lookup"><span data-stu-id="df5be-108">(For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="df5be-109">Si noti che il report presenta alcune limitazioni quando viene usato come report di inventario vero.</span><span class="sxs-lookup"><span data-stu-id="df5be-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="df5be-110">Per prima cosa, il report IP Phone elenca semplicemente tutti i telefoni che hanno effettuato l'accesso a Lync Server durante il periodo di tempo specificato, ordinati in base all'ora dell'ultimo accesso.</span><span class="sxs-lookup"><span data-stu-id="df5be-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="df5be-111">Se un telefono non ha eseguito l'accesso durante il periodo di tempo specificato, non verrà elencato nel report inventario.</span><span class="sxs-lookup"><span data-stu-id="df5be-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="df5be-112">Che include i telefoni che hanno effettuato l'accesso prima del periodo di tempo iniziato e che sono stati ancora connessi durante l'intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="df5be-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="df5be-113">Supponiamo, ad esempio, di voler esaminare tutte le scorte telefoniche di luglio 2012.</span><span class="sxs-lookup"><span data-stu-id="df5be-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="df5be-114">Supponiamo anche che diversi telefoni abbiano effettuato l'accesso a Lync Server il 30 giugno 2012 ed abbiano ancora effettuato l'accesso a partire dal 1 ° luglio.</span><span class="sxs-lookup"><span data-stu-id="df5be-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="df5be-115">I telefoni non verranno visualizzati nel report scorte per il 1 ° luglio.</span><span class="sxs-lookup"><span data-stu-id="df5be-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="df5be-116">È anche importante notare che il report inventario può includere i telefoni che l'organizzazione non usa più.</span><span class="sxs-lookup"><span data-stu-id="df5be-116">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="df5be-117">Supponiamo ad esempio che un numero di telefoni Fabrikam sia connesso al sistema il 1 ° luglio 2012; 5 giorni dopo l'organizzazione si è sbarazzata di tutti i telefoni Fabrikam e li ha sostituiti con un modello contoso più recente.</span><span class="sxs-lookup"><span data-stu-id="df5be-117">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="df5be-118">I telefoni Fabrikam verranno comunque visualizzati nel report "inventario" semplicemente perché hanno effettuato l'accesso al sistema durante il mese di luglio.</span><span class="sxs-lookup"><span data-stu-id="df5be-118">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="df5be-119">Inoltre, il report inventario IP Phone non riporta i totali di riepilogo per i diversi tipi di telefono.</span><span class="sxs-lookup"><span data-stu-id="df5be-119">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones.</span></span> <span data-ttu-id="df5be-120">Supponiamo, ad esempio, di avere 105 telefoni CX600 Polycom.</span><span class="sxs-lookup"><span data-stu-id="df5be-120">For example, suppose you have 105 Polycom CX600 phones.</span></span> <span data-ttu-id="df5be-121">Il report non ti dirà che hai 105 di questi telefoni; verranno invece visualizzate semplicemente voci separate di 105 per la Cx600 Polycom.</span><span class="sxs-lookup"><span data-stu-id="df5be-121">The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600.</span></span> <span data-ttu-id="df5be-122">L'unico modo per sapere che ci sono 105 voci per il Polycom Cx600 consiste nel contare ognuna di queste voci manualmente.</span><span class="sxs-lookup"><span data-stu-id="df5be-122">The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="df5be-123">In alternativa, esportare i dati e usare Microsoft Excel o Windows PowerShell per eseguire il conteggio per l'utente.</span><span class="sxs-lookup"><span data-stu-id="df5be-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="df5be-124">Accesso al report inventario IP Phone</span><span class="sxs-lookup"><span data-stu-id="df5be-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="df5be-125">Il report inventario IP Phone si accede dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="df5be-125">The IP Phone Inventory Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="df5be-126">Se si fa clic sulla metrica URI utente, è possibile accedere al report attività utente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="df5be-126">If you click the User URI metric you can access the User Activity Report for that user.</span></span> <span data-ttu-id="df5be-127">Facendo clic sulla metrica Ultima attività per una chiamata peer-to-peer si accede al report Dettagli sessione peer-to-peer. Se si fa clic sulla stessa metrica per una conferenza, sarà possibile eseguire il report Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="df5be-127">Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="df5be-128">Sfruttare al meglio il report inventario IP Phone</span><span class="sxs-lookup"><span data-stu-id="df5be-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="df5be-129">Se si è interessati solo alle informazioni sull'uso di un determinato tipo di telefono (ad esempio, "con quale frequenza Gli utenti usano un telefono CX600 Polycom?"), è possibile ottenere queste informazioni direttamente dal report inventario del telefono IP filtrando per quel particolare tipo di telefono.</span><span class="sxs-lookup"><span data-stu-id="df5be-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="df5be-130">Tuttavia, se vuoi informazioni di riepilogo per tutti i telefoni (quante persone usano un Polycom CX600, quanti usano un IP8540 LG-Nortel e così via), dovrai esportare i dati e usare un'altra applicazione (ad esempio Windows PowerShell) per eseguire questo tipo di analisi.</span><span class="sxs-lookup"><span data-stu-id="df5be-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="df5be-131">Si supponga ad esempio di esportare i dati in un file con valori delimitati da virgole\\(\\C\_:\_data\_IP Phone Inventory Report. csv).</span><span class="sxs-lookup"><span data-stu-id="df5be-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="df5be-132">In questo caso, puoi usare questi due comandi per specificare i dati di riepilogo per tutti i telefoni:</span><span class="sxs-lookup"><span data-stu-id="df5be-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="df5be-133">Che restituirà dati simili a questi:</span><span class="sxs-lookup"><span data-stu-id="df5be-133">That will return data similar to this:</span></span>

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

<span data-ttu-id="df5be-134">Allo stesso modo, questi due comandi indicano i telefoni connessi al sistema, ma che non sono mai stati effettivamente usati per effettuare una chiamata (il valore della metrica Ultima attività è vuoto, che indica che non è stata eseguita alcuna Ultima attività):</span><span class="sxs-lookup"><span data-stu-id="df5be-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="df5be-135">Che restituisce dati simili a quelli per ogni telefono che non è stato usato:</span><span class="sxs-lookup"><span data-stu-id="df5be-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="df5be-136">Un altro modo interessante per usare il report di inventario dei telefoni IP è il seguente: se si ha l'indirizzo MAC di un telefono IP, è possibile trovare l'ultimo utente che ha usato il telefono semplicemente inserendo l'indirizzo nella casella di testo indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="df5be-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="df5be-137">Il report inventario IP Phone riferirà (tra le altre cose) l'indirizzo SIP dell'utente che ha effettuato l'accesso con il telefono.</span><span class="sxs-lookup"><span data-stu-id="df5be-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="df5be-138">In alternativa, è possibile immettere un indirizzo SIP utente (nella casella prefisso URI utente) per scoprire tutti i telefoni usati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="df5be-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="df5be-139">Filtri</span><span class="sxs-lookup"><span data-stu-id="df5be-139">Filters</span></span>

<span data-ttu-id="df5be-140">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="df5be-140">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="df5be-141">Ad esempio, l'inventario del telefono IP consente di visualizzare solo i telefoni prodotti da una società specifica o anche una versione specifica di questi telefoni.</span><span class="sxs-lookup"><span data-stu-id="df5be-141">For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones.</span></span> <span data-ttu-id="df5be-142">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="df5be-142">You can also choose how data should be grouped.</span></span> <span data-ttu-id="df5be-143">In questo caso, le registrazioni vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="df5be-143">In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="df5be-144">Nella tabella seguente sono elencati i filtri che è possibile usare con il report inventario IP Phone.</span><span class="sxs-lookup"><span data-stu-id="df5be-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="df5be-145">Filtri di report inventario IP Phone</span><span class="sxs-lookup"><span data-stu-id="df5be-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df5be-146">Nome</span><span class="sxs-lookup"><span data-stu-id="df5be-146">Name</span></span></th>
<th><span data-ttu-id="df5be-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df5be-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df5be-148"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-149">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="df5be-149">Start date/time for the time range.</span></span> <span data-ttu-id="df5be-150">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="df5be-150">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="df5be-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="df5be-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="df5be-152">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="df5be-152">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="df5be-153">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="df5be-153">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="df5be-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="df5be-154">7/7/2012</span></span></p>
<p><span data-ttu-id="df5be-155">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="df5be-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="df5be-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="df5be-156">7/3/2012</span></span></p>
<p><span data-ttu-id="df5be-157">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="df5be-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df5be-158"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-159">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="df5be-159">End date/time for the time range.</span></span> <span data-ttu-id="df5be-160">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="df5be-160">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="df5be-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="df5be-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="df5be-162">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="df5be-162">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="df5be-163">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="df5be-163">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="df5be-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="df5be-164">7/7/2012</span></span></p>
<p><span data-ttu-id="df5be-165">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="df5be-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="df5be-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="df5be-166">7/3/2012</span></span></p>
<p><span data-ttu-id="df5be-167">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="df5be-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df5be-168"><strong>Produttore</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-169">Nome della società che ha prodotto il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-169">Name of the company that manufactured the IP phone.</span></span> <span data-ttu-id="df5be-170">I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="df5be-170">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df5be-171"><strong>Versione hardware</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-172">Numero di versione del telefono IP; usando il produttore e i filtri della versione hardware puoi identificare in modo univoco un determinato tipo di telefono.</span><span class="sxs-lookup"><span data-stu-id="df5be-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="df5be-173">I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="df5be-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df5be-174"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-175">Identificatore per il software usato dal telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-175">Identifier for the software used by the IP phone.</span></span> <span data-ttu-id="df5be-176">I valori per questo filtro vengono popolati automaticamente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="df5be-176">The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df5be-177"><strong>Indirizzo MAC</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-178">Identificatore univoco per l'interfaccia di rete sul telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-178">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="df5be-179">L'indirizzo MAC (Media Access Control) viene in genere assegnato nel momento in cui il telefono viene fabbricato e collegato all'hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="df5be-179">The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="df5be-180">Per cercare i record relativi a un indirizzo MAC specifico, è sufficiente immettere l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="df5be-180">To search for records pertaining to a specific MAC address simply enter that address.</span></span> <span data-ttu-id="df5be-181">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="df5be-181">For example:</span></span></p>
<p><span data-ttu-id="df5be-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="df5be-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="df5be-183">È necessario immettere l'indirizzo completo.</span><span class="sxs-lookup"><span data-stu-id="df5be-183">You must enter the complete address.</span></span> <span data-ttu-id="df5be-184">Un indirizzo parziale (ad esempio 00-08-5D) non restituisce dati.</span><span class="sxs-lookup"><span data-stu-id="df5be-184">A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df5be-185"><strong>Ultima attività prima del giorno</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-186">Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="df5be-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="df5be-187">Tutti</span><span class="sxs-lookup"><span data-stu-id="df5be-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="df5be-188">10</span><span class="sxs-lookup"><span data-stu-id="df5be-188">10</span></span></p></li>
<li><p><span data-ttu-id="df5be-189">20</span><span class="sxs-lookup"><span data-stu-id="df5be-189">20</span></span></p></li>
<li><p><span data-ttu-id="df5be-190">30</span><span class="sxs-lookup"><span data-stu-id="df5be-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df5be-191"><strong>Ultima ora di disconnessione prima del giorno</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-192">Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="df5be-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="df5be-193">Tutti</span><span class="sxs-lookup"><span data-stu-id="df5be-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="df5be-194">10</span><span class="sxs-lookup"><span data-stu-id="df5be-194">10</span></span></p></li>
<li><p><span data-ttu-id="df5be-195">20</span><span class="sxs-lookup"><span data-stu-id="df5be-195">20</span></span></p></li>
<li><p><span data-ttu-id="df5be-196">30</span><span class="sxs-lookup"><span data-stu-id="df5be-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df5be-197"><strong>Prefisso URI utente</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-198">Indirizzo SIP dell'utente che ha usato il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="df5be-199">Metriche</span><span class="sxs-lookup"><span data-stu-id="df5be-199">Metrics</span></span>

<span data-ttu-id="df5be-200">Nella tabella seguente sono elencate le informazioni fornite nel report sull'inventario dei telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="df5be-201">Metriche del report inventario IP Phone</span><span class="sxs-lookup"><span data-stu-id="df5be-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df5be-202">Nome</span><span class="sxs-lookup"><span data-stu-id="df5be-202">Name</span></span></th>
<th><span data-ttu-id="df5be-203">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="df5be-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="df5be-204">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df5be-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df5be-205"><strong>Produttore</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-206">Sì</span><span class="sxs-lookup"><span data-stu-id="df5be-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="df5be-207">Nome della società che ha prodotto il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df5be-208"><strong>Versione hardware</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-209">Sì</span><span class="sxs-lookup"><span data-stu-id="df5be-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="df5be-210">Numero di versione del telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df5be-211"><strong>Indirizzo MAC</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-212">Sì</span><span class="sxs-lookup"><span data-stu-id="df5be-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="df5be-213">Identificatore univoco per l'interfaccia di rete sul telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-213">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="df5be-214">L'indirizzo MAC viene in genere assegnato nel momento in cui il telefono viene fabbricato e viene collegato all'hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="df5be-214">The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df5be-215"><strong>URI utente</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-216">Sì</span><span class="sxs-lookup"><span data-stu-id="df5be-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="df5be-217">Indirizzo SIP dell'utente che ha usato il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df5be-218"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-219">Sì</span><span class="sxs-lookup"><span data-stu-id="df5be-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="df5be-220">Identificatore per il software usato dal telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df5be-221"><strong>Ora ultimo accesso</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-222">Sì</span><span class="sxs-lookup"><span data-stu-id="df5be-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="df5be-223">Data e ora dell'ultima volta che il telefono IP ha eseguito l'accesso a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df5be-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df5be-224"><strong>Ultima ora di disconnessione</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-225">Sì</span><span class="sxs-lookup"><span data-stu-id="df5be-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="df5be-226">Data e ora in cui il telefono IP ha eseguito l'ultimo disconnessione da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df5be-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df5be-227"><strong>Ultima attività</strong></span><span class="sxs-lookup"><span data-stu-id="df5be-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="df5be-228">Sì</span><span class="sxs-lookup"><span data-stu-id="df5be-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="df5be-229">Data e ora dell'ultima volta che è stato usato il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="df5be-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

