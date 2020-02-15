---
title: 'Lync Server 2013: rapporto inventario telefoni IP'
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
ms.openlocfilehash: 0c99945626105282324202d1fd754cd5d966bc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="00fb3-102">Rapporto inventario telefoni IP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00fb3-102">IP Phone Inventory Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00fb3-103">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="00fb3-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="00fb3-104">Il rapporto inventario telefoni IP riporta informazioni sui telefoni IP attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="00fb3-104">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization.</span></span> <span data-ttu-id="00fb3-105">Il report inventario IP fornisce un elenco dettagliato dei telefoni IP che sono stati effettivamente utilizzati durante il periodo di riferimento specificato.</span><span class="sxs-lookup"><span data-stu-id="00fb3-105">The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period.</span></span> <span data-ttu-id="00fb3-106">Tra le altre cose, questo rapporto consente agli amministratori di sapere se sono presenti telefoni obsoleti o obsoleti ancora in uso che devono essere sostituiti; è inoltre possibile avvisare gli amministratori del fatto che sono presenti telefoni costosi nell'organizzazione raramente utilizzati.</span><span class="sxs-lookup"><span data-stu-id="00fb3-106">Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used.</span></span> <span data-ttu-id="00fb3-107">Questo tipo di informazioni può essere prezioso quando arriva il momento di acquistare nuovi telefoni o di ridistribuire i telefoni esistenti.</span><span class="sxs-lookup"><span data-stu-id="00fb3-107">That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones.</span></span> <span data-ttu-id="00fb3-108">Ad esempio, un utente che raramente utilizza il proprio telefono costoso potrebbe essere invitato a scambiare telefoni con un utente che usa il proprio telefono con molta più frequenza.</span><span class="sxs-lookup"><span data-stu-id="00fb3-108">(For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="00fb3-109">Si noti che questo rapporto ha alcune limitazioni quando si tratta di essere utilizzato come un rapporto di inventario vero.</span><span class="sxs-lookup"><span data-stu-id="00fb3-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="00fb3-110">Per prima cosa, il rapporto telefoni IP elenca semplicemente tutti i telefoni che hanno effettuato l'accesso a Lync Server durante il periodo di tempo specificato, ordinati in base alla data dell'ultimo accesso.</span><span class="sxs-lookup"><span data-stu-id="00fb3-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="00fb3-111">Se un telefono non ha eseguito l'accesso durante il periodo di tempo specificato, non verrà elencato nel rapporto inventario.</span><span class="sxs-lookup"><span data-stu-id="00fb3-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="00fb3-112">Che include i telefoni che hanno effettuato l'accesso prima del periodo di tempo in cui sono stati avviati e che sono ancora connessi durante l'intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="00fb3-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="00fb3-113">Ad esempio, si supponga di voler esaminare tutti gli inventari telefonici per il 2012 luglio.</span><span class="sxs-lookup"><span data-stu-id="00fb3-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="00fb3-114">Si supponga, anche, che alcuni telefoni connessi a Lync Server il 30 giugno 2012 e siano ancora connessi al primo luglio.</span><span class="sxs-lookup"><span data-stu-id="00fb3-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="00fb3-115">Tali telefoni non verranno visualizzati nel rapporto inventario del 1 ° luglio.</span><span class="sxs-lookup"><span data-stu-id="00fb3-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="00fb3-116">È inoltre importante tenere presente che il rapporto inventario potrebbe includere i telefoni che l'organizzazione non utilizza più.</span><span class="sxs-lookup"><span data-stu-id="00fb3-116">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="00fb3-117">Si supponga, ad esempio, che un numero di telefoni Fabrikam sia connesso al sistema il 1 ° luglio 2012; 5 giorni dopo l'organizzazione si è sbarazzata di tutti i telefoni Fabrikam e li ha sostituiti con un modello contoso più recente.</span><span class="sxs-lookup"><span data-stu-id="00fb3-117">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="00fb3-118">I telefoni Fabrikam continueranno a essere visualizzati sul rapporto "inventario" semplicemente perché si sono connessi al sistema nel corso del mese di luglio.</span><span class="sxs-lookup"><span data-stu-id="00fb3-118">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="00fb3-119">Inoltre, il rapporto inventario telefoni IP non riporta i totali di riepilogo per i diversi tipi di telefoni.</span><span class="sxs-lookup"><span data-stu-id="00fb3-119">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones.</span></span> <span data-ttu-id="00fb3-120">Ad esempio, si supponga di disporre di 105 telefoni CX600 Polycom.</span><span class="sxs-lookup"><span data-stu-id="00fb3-120">For example, suppose you have 105 Polycom CX600 phones.</span></span> <span data-ttu-id="00fb3-121">Il report non dirà di avere 105 di questi telefoni; al contrario, si vedranno semplicemente 105 voci separate per la Cx600 Polycom.</span><span class="sxs-lookup"><span data-stu-id="00fb3-121">The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600.</span></span> <span data-ttu-id="00fb3-122">L'unico modo per sapere che ci sono 105 voci per l'Polycom Cx600 sarebbe quello di contare ognuna di queste voci manualmente.</span><span class="sxs-lookup"><span data-stu-id="00fb3-122">The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="00fb3-123">In alternativa, esportare i dati e utilizzare Microsoft Excel o Windows PowerShell per eseguire il conteggio per l'utente.</span><span class="sxs-lookup"><span data-stu-id="00fb3-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="00fb3-124">Accesso al rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="00fb3-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="00fb3-125">È possibile accedere al rapporto inventario telefoni IP dalla Home page dei rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="00fb3-125">The IP Phone Inventory Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="00fb3-126">Se si fa clic sulla metrica URI dell'utente, è possibile accedere al rapporto attività utente per tale utente.</span><span class="sxs-lookup"><span data-stu-id="00fb3-126">If you click the User URI metric you can access the User Activity Report for that user.</span></span> <span data-ttu-id="00fb3-127">Se si fa clic sulla metrica Ultima attività per una chiamata peer-to-peer, verrà eseguito il rapporto Dettagli sessione peer-to-peer. Se si fa clic sulla stessa metrica di una conferenza, verrà utilizzato il rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="00fb3-127">Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="00fb3-128">Utilizzo ottimale del rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="00fb3-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="00fb3-129">Se si è interessati solo alle informazioni sull'utilizzo per un determinato tipo di telefono (ad esempio, "con quale frequenza Gli utenti utilizzano un telefono CX600 di Polycom?"), è possibile ottenere tali informazioni direttamente dal rapporto inventario telefoni IP tramite filtro per quel tipo di telefono specifico.</span><span class="sxs-lookup"><span data-stu-id="00fb3-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="00fb3-130">Tuttavia, se si desiderano informazioni di riepilogo per tutti i telefoni (numero di utenti che utilizzano un CX600 di Polycom, quanti utilizzano un IP8540 LG-Nortel e così via), è necessario esportare i dati e utilizzare un'altra applicazione, ad esempio Windows PowerShell, per eseguire questo tipo di analisi.</span><span class="sxs-lookup"><span data-stu-id="00fb3-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="00fb3-131">Si supponga, ad esempio, di esportare i dati in un file con valori delimitati da virgole\_(\_C\_:\\data\\IP Phone inventario report. csv).</span><span class="sxs-lookup"><span data-stu-id="00fb3-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="00fb3-132">In tal caso, è possibile utilizzare questi due comandi per fornire dati di riepilogo per tutti i telefoni:</span><span class="sxs-lookup"><span data-stu-id="00fb3-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="00fb3-133">Il comando restituisce dati analoghi a questi:</span><span class="sxs-lookup"><span data-stu-id="00fb3-133">That will return data similar to this:</span></span>

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

<span data-ttu-id="00fb3-134">Analogamente, questi due comandi indicano quali telefoni sono connessi al sistema ma non sono mai stati effettivamente utilizzati per effettuare una chiamata (il valore della metrica Ultima attività è vuoto, a indicare che non vi sono state attività nell'ultima operazione):</span><span class="sxs-lookup"><span data-stu-id="00fb3-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="00fb3-135">Che restituisce dati simili a questo per ogni telefono che non è stato utilizzato:</span><span class="sxs-lookup"><span data-stu-id="00fb3-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="00fb3-136">Un altro modo interessante per utilizzare il rapporto inventario telefoni IP è questo: se si ha l'indirizzo MAC di un telefono IP, è possibile trovare l'utente che ha utilizzato l'ultima volta quel telefono semplicemente inserendo quell'indirizzo nella casella di testo indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="00fb3-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="00fb3-137">Il rapporto inventario telefoni IP riporterà (tra le altre cose) l'indirizzo SIP dell'utente che ha effettuato l'ultimo accesso con il telefono.</span><span class="sxs-lookup"><span data-stu-id="00fb3-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="00fb3-138">In alternativa, è possibile immettere un indirizzo SIP utente (nella casella prefisso URI utente) per individuare tutti i telefoni che sono stati utilizzati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="00fb3-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="00fb3-139">Filtri</span><span class="sxs-lookup"><span data-stu-id="00fb3-139">Filters</span></span>

<span data-ttu-id="00fb3-140">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="00fb3-140">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="00fb3-141">Ad esempio, l'inventario del telefono IP consente di visualizzare solo i telefoni prodotti da una determinata società o persino una versione specifica di tali telefoni.</span><span class="sxs-lookup"><span data-stu-id="00fb3-141">For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones.</span></span> <span data-ttu-id="00fb3-142">È inoltre possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="00fb3-142">You can also choose how data should be grouped.</span></span> <span data-ttu-id="00fb3-143">In questo caso, le registrazioni sono raggruppate in base all'ora, al giorno, alla settimana o al mese.</span><span class="sxs-lookup"><span data-stu-id="00fb3-143">In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="00fb3-144">Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il rapporto inventario telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="00fb3-145">Filtri del rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="00fb3-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00fb3-146">Nome</span><span class="sxs-lookup"><span data-stu-id="00fb3-146">Name</span></span></th>
<th><span data-ttu-id="00fb3-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00fb3-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-p109">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="00fb3-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="00fb3-151">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="00fb3-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="00fb3-p110">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="00fb3-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="00fb3-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="00fb3-154">7/7/2012</span></span></p>
<p><span data-ttu-id="00fb3-155">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="00fb3-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="00fb3-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="00fb3-156">7/3/2012</span></span></p>
<p><span data-ttu-id="00fb3-157">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="00fb3-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fb3-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-p111">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="00fb3-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="00fb3-161">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="00fb3-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="00fb3-p112">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="00fb3-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="00fb3-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="00fb3-164">7/7/2012</span></span></p>
<p><span data-ttu-id="00fb3-165">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="00fb3-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="00fb3-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="00fb3-166">7/3/2012</span></span></p>
<p><span data-ttu-id="00fb3-167">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="00fb3-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-168"><strong>Produttore</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-169">Nome della società che ha prodotto il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-169">Name of the company that manufactured the IP phone.</span></span> <span data-ttu-id="00fb3-170">I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="00fb3-170">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fb3-171"><strong>Versione hardware</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-172">Numero di versione del telefono IP; Se si utilizza il produttore e i filtri versione hardware, è possibile identificare in modo univoco un determinato tipo di telefono.</span><span class="sxs-lookup"><span data-stu-id="00fb3-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="00fb3-173">I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="00fb3-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-174"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-175">Identificatore del software utilizzato dal telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-175">Identifier for the software used by the IP phone.</span></span> <span data-ttu-id="00fb3-176">I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="00fb3-176">The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fb3-177"><strong>Indirizzo MAC</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-178">Identificatore univoco per l'interfaccia di rete sul telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-178">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="00fb3-179">L'indirizzo MAC (Media Access Control) in genere viene assegnato al momento in cui il telefono è prodotto e viene collegato all'hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="00fb3-179">The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="00fb3-180">Per cercare i record relativi a uno specifico indirizzo MAC, è sufficiente immettere quell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="00fb3-180">To search for records pertaining to a specific MAC address simply enter that address.</span></span> <span data-ttu-id="00fb3-181">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00fb3-181">For example:</span></span></p>
<p><span data-ttu-id="00fb3-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="00fb3-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="00fb3-183">È necessario immettere l'indirizzo completo.</span><span class="sxs-lookup"><span data-stu-id="00fb3-183">You must enter the complete address.</span></span> <span data-ttu-id="00fb3-184">Un indirizzo parziale (ad esempio 00-08-5D) non restituisce dati.</span><span class="sxs-lookup"><span data-stu-id="00fb3-184">A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-185"><strong>Ultima attività prima di ogni giorno</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-186">Selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="00fb3-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="00fb3-187">Tutti</span><span class="sxs-lookup"><span data-stu-id="00fb3-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="00fb3-188">10 </span><span class="sxs-lookup"><span data-stu-id="00fb3-188">10</span></span></p></li>
<li><p><span data-ttu-id="00fb3-189">20</span><span class="sxs-lookup"><span data-stu-id="00fb3-189">20</span></span></p></li>
<li><p><span data-ttu-id="00fb3-190">30</span><span class="sxs-lookup"><span data-stu-id="00fb3-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fb3-191"><strong>Ora ultima disconnessione prima di giorni</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-192">Selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="00fb3-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="00fb3-193">Tutti</span><span class="sxs-lookup"><span data-stu-id="00fb3-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="00fb3-194">10 </span><span class="sxs-lookup"><span data-stu-id="00fb3-194">10</span></span></p></li>
<li><p><span data-ttu-id="00fb3-195">20</span><span class="sxs-lookup"><span data-stu-id="00fb3-195">20</span></span></p></li>
<li><p><span data-ttu-id="00fb3-196">30</span><span class="sxs-lookup"><span data-stu-id="00fb3-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-197"><strong>Prefisso URI utente</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-198">Indirizzo SIP dell'utente che ha utilizzato il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="00fb3-199">Metriche</span><span class="sxs-lookup"><span data-stu-id="00fb3-199">Metrics</span></span>

<span data-ttu-id="00fb3-200">Nella tabella seguente sono elencate le informazioni fornite nel rapporto inventario telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="00fb3-201">Metriche del rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="00fb3-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00fb3-202">Nome</span><span class="sxs-lookup"><span data-stu-id="00fb3-202">Name</span></span></th>
<th><span data-ttu-id="00fb3-203">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="00fb3-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="00fb3-204">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00fb3-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-205"><strong>Produttore</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-206">Sì</span><span class="sxs-lookup"><span data-stu-id="00fb3-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="00fb3-207">Nome della società che ha prodotto il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fb3-208"><strong>Versione hardware</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-209">Sì</span><span class="sxs-lookup"><span data-stu-id="00fb3-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="00fb3-210">Numero di versione del telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-211"><strong>Indirizzo MAC</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-212">Sì</span><span class="sxs-lookup"><span data-stu-id="00fb3-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="00fb3-213">Identificatore univoco per l'interfaccia di rete sul telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-213">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="00fb3-214">L'indirizzo MAC è in genere assegnato al momento in cui il telefono è prodotto e viene collegato all'hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="00fb3-214">The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fb3-215"><strong>URI dell'utente</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-216">Sì</span><span class="sxs-lookup"><span data-stu-id="00fb3-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="00fb3-217">Indirizzo SIP dell'utente che ha utilizzato il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-218"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-219">Sì</span><span class="sxs-lookup"><span data-stu-id="00fb3-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="00fb3-220">Identificatore del software utilizzato dal telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fb3-221"><strong>Ora ultimo accesso</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-222">Sì</span><span class="sxs-lookup"><span data-stu-id="00fb3-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="00fb3-223">Data e ora dell'ultimo accesso del telefono IP a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00fb3-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00fb3-224"><strong>Ora ultima disconnessione</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-225">Sì</span><span class="sxs-lookup"><span data-stu-id="00fb3-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="00fb3-226">Data e ora dell'ultima disconnessione del telefono IP da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00fb3-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00fb3-227"><strong>Ultima attività</strong></span><span class="sxs-lookup"><span data-stu-id="00fb3-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="00fb3-228">Sì</span><span class="sxs-lookup"><span data-stu-id="00fb3-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="00fb3-229">Data e ora dell'ultimo utilizzo del telefono IP.</span><span class="sxs-lookup"><span data-stu-id="00fb3-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

