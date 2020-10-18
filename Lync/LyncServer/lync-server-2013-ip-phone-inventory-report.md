---
title: 'Lync Server 2013: rapporto inventario telefoni IP'
description: 'Lync Server 2013: rapporto inventario telefoni IP.'
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
ms.openlocfilehash: 3bc05017775ad64e0e18f876215aa2c6b3882bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575022"
---
# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="1ca14-103">Rapporto inventario telefoni IP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ca14-103">IP Phone Inventory Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ca14-104">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="1ca14-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="1ca14-105">Il rapporto inventario telefoni IP riporta informazioni sui telefoni IP attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1ca14-105">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization.</span></span> <span data-ttu-id="1ca14-106">Il report inventario IP fornisce un elenco dettagliato dei telefoni IP che sono stati effettivamente utilizzati durante il periodo di riferimento specificato.</span><span class="sxs-lookup"><span data-stu-id="1ca14-106">The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period.</span></span> <span data-ttu-id="1ca14-107">Tra le altre cose, questo rapporto consente agli amministratori di sapere se sono presenti telefoni obsoleti o obsoleti ancora in uso che devono essere sostituiti; è inoltre possibile avvisare gli amministratori del fatto che sono presenti telefoni costosi nell'organizzazione raramente utilizzati.</span><span class="sxs-lookup"><span data-stu-id="1ca14-107">Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used.</span></span> <span data-ttu-id="1ca14-108">Questo tipo di informazioni può essere prezioso quando arriva il momento di acquistare nuovi telefoni o di ridistribuire i telefoni esistenti.</span><span class="sxs-lookup"><span data-stu-id="1ca14-108">That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones.</span></span> <span data-ttu-id="1ca14-109">Ad esempio, un utente che raramente utilizza il proprio telefono costoso potrebbe essere invitato a scambiare telefoni con un utente che usa il proprio telefono con molta più frequenza.</span><span class="sxs-lookup"><span data-stu-id="1ca14-109">(For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="1ca14-110">Si noti che questo rapporto ha alcune limitazioni quando si tratta di essere utilizzato come un rapporto di inventario vero.</span><span class="sxs-lookup"><span data-stu-id="1ca14-110">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="1ca14-111">Per prima cosa, il rapporto telefoni IP elenca semplicemente tutti i telefoni che hanno effettuato l'accesso a Lync Server durante il periodo di tempo specificato, ordinati in base alla data dell'ultimo accesso.</span><span class="sxs-lookup"><span data-stu-id="1ca14-111">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="1ca14-112">Se un telefono non ha eseguito l'accesso durante il periodo di tempo specificato, non verrà elencato nel rapporto inventario.</span><span class="sxs-lookup"><span data-stu-id="1ca14-112">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="1ca14-113">Che include i telefoni che hanno effettuato l'accesso prima del periodo di tempo in cui sono stati avviati e che sono ancora connessi durante l'intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="1ca14-113">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="1ca14-114">Ad esempio, si supponga di voler esaminare tutti gli inventari telefonici per il 2012 luglio.</span><span class="sxs-lookup"><span data-stu-id="1ca14-114">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="1ca14-115">Si supponga, anche, che alcuni telefoni connessi a Lync Server il 30 giugno 2012 e siano ancora connessi al primo luglio.</span><span class="sxs-lookup"><span data-stu-id="1ca14-115">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="1ca14-116">Tali telefoni non verranno visualizzati nel rapporto inventario del 1 ° luglio.</span><span class="sxs-lookup"><span data-stu-id="1ca14-116">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="1ca14-117">È inoltre importante tenere presente che il rapporto inventario potrebbe includere i telefoni che l'organizzazione non utilizza più.</span><span class="sxs-lookup"><span data-stu-id="1ca14-117">It's also important to note that the inventory report could include phones that your organization no longer uses.</span></span> <span data-ttu-id="1ca14-118">Si supponga, ad esempio, che un numero di telefoni Fabrikam sia connesso al sistema il 1 ° luglio 2012; 5 giorni dopo l'organizzazione si è sbarazzata di tutti i telefoni Fabrikam e li ha sostituiti con un modello contoso più recente.</span><span class="sxs-lookup"><span data-stu-id="1ca14-118">For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model.</span></span> <span data-ttu-id="1ca14-119">I telefoni Fabrikam continueranno a essere visualizzati sul rapporto "inventario" semplicemente perché si sono connessi al sistema nel corso del mese di luglio.</span><span class="sxs-lookup"><span data-stu-id="1ca14-119">The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="1ca14-120">Inoltre, il rapporto inventario telefoni IP non riporta i totali di riepilogo per i diversi tipi di telefoni.</span><span class="sxs-lookup"><span data-stu-id="1ca14-120">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones.</span></span> <span data-ttu-id="1ca14-121">Ad esempio, si supponga di disporre di 105 telefoni CX600 Polycom.</span><span class="sxs-lookup"><span data-stu-id="1ca14-121">For example, suppose you have 105 Polycom CX600 phones.</span></span> <span data-ttu-id="1ca14-122">Il report non dirà di avere 105 di questi telefoni; al contrario, si vedranno semplicemente 105 voci separate per la Cx600 Polycom.</span><span class="sxs-lookup"><span data-stu-id="1ca14-122">The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600.</span></span> <span data-ttu-id="1ca14-123">L'unico modo per sapere che ci sono 105 voci per l'Polycom Cx600 sarebbe quello di contare ognuna di queste voci manualmente.</span><span class="sxs-lookup"><span data-stu-id="1ca14-123">The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1ca14-124">In alternativa, esportare i dati e utilizzare Microsoft Excel o Windows PowerShell per eseguire il conteggio per l'utente.</span><span class="sxs-lookup"><span data-stu-id="1ca14-124">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="1ca14-125">Accesso al rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="1ca14-125">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="1ca14-126">È possibile accedere al rapporto inventario telefoni IP dalla Home page dei rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="1ca14-126">The IP Phone Inventory Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="1ca14-127">Se si fa clic sulla metrica URI dell'utente, è possibile accedere al rapporto attività utente per tale utente.</span><span class="sxs-lookup"><span data-stu-id="1ca14-127">If you click the User URI metric you can access the User Activity Report for that user.</span></span> <span data-ttu-id="1ca14-128">Se si fa clic sulla metrica Ultima attività per una chiamata peer-to-peer, verrà eseguito il rapporto Dettagli sessione peer-to-peer. Se si fa clic sulla stessa metrica di una conferenza, verrà utilizzato il rapporto Dettagli conferenza.</span><span class="sxs-lookup"><span data-stu-id="1ca14-128">Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="1ca14-129">Utilizzo ottimale del rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="1ca14-129">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="1ca14-130">Se si è interessati solo alle informazioni sull'utilizzo per un determinato tipo di telefono (ad esempio, "con quale frequenza Gli utenti utilizzano un telefono CX600 di Polycom?"), è possibile ottenere tali informazioni direttamente dal rapporto inventario telefoni IP tramite filtro per quel tipo di telefono specifico.</span><span class="sxs-lookup"><span data-stu-id="1ca14-130">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="1ca14-131">Tuttavia, se si desiderano informazioni di riepilogo per tutti i telefoni (numero di utenti che utilizzano un CX600 di Polycom, quanti utilizzano un LG-Nortel IP8540 e così via), sarà necessario esportare i dati e utilizzare un'altra applicazione (ad esempio Windows PowerShell) per eseguire questo tipo di analisi.</span><span class="sxs-lookup"><span data-stu-id="1ca14-131">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="1ca14-132">Si supponga, ad esempio, di esportare i dati in un file con valori delimitati da virgole (C: \\ data \\ IP \_ Phone \_ Inventory \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="1ca14-132">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="1ca14-133">In tal caso, è possibile utilizzare questi due comandi per fornire dati di riepilogo per tutti i telefoni:</span><span class="sxs-lookup"><span data-stu-id="1ca14-133">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="1ca14-134">Il comando restituisce dati analoghi a questi:</span><span class="sxs-lookup"><span data-stu-id="1ca14-134">That will return data similar to this:</span></span>

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

<span data-ttu-id="1ca14-135">Analogamente, questi due comandi indicano quali telefoni sono connessi al sistema ma non sono mai stati effettivamente utilizzati per effettuare una chiamata (il valore della metrica Ultima attività è vuoto, a indicare che non vi sono state attività nell'ultima operazione):</span><span class="sxs-lookup"><span data-stu-id="1ca14-135">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="1ca14-136">Che restituisce dati simili a questo per ogni telefono che non è stato utilizzato:</span><span class="sxs-lookup"><span data-stu-id="1ca14-136">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="1ca14-137">Un altro modo interessante per utilizzare il rapporto inventario telefoni IP è questo: se si ha l'indirizzo MAC di un telefono IP, è possibile trovare l'utente che ha utilizzato l'ultima volta quel telefono semplicemente inserendo quell'indirizzo nella casella di testo indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="1ca14-137">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="1ca14-138">Il rapporto inventario telefoni IP riporterà (tra le altre cose) l'indirizzo SIP dell'utente che ha effettuato l'ultimo accesso con il telefono.</span><span class="sxs-lookup"><span data-stu-id="1ca14-138">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="1ca14-139">In alternativa, è possibile immettere un indirizzo SIP utente (nella casella prefisso URI utente) per individuare tutti i telefoni che sono stati utilizzati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1ca14-139">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1ca14-140">Filtri</span><span class="sxs-lookup"><span data-stu-id="1ca14-140">Filters</span></span>

<span data-ttu-id="1ca14-141">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="1ca14-141">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="1ca14-142">Ad esempio, l'inventario del telefono IP consente di visualizzare solo i telefoni prodotti da una determinata società o persino una versione specifica di tali telefoni.</span><span class="sxs-lookup"><span data-stu-id="1ca14-142">For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones.</span></span> <span data-ttu-id="1ca14-143">È inoltre possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="1ca14-143">You can also choose how data should be grouped.</span></span> <span data-ttu-id="1ca14-144">In questo caso, le registrazioni sono raggruppate in base all'ora, al giorno, alla settimana o al mese.</span><span class="sxs-lookup"><span data-stu-id="1ca14-144">In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="1ca14-145">Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il rapporto inventario telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-145">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="1ca14-146">Filtri del rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="1ca14-146">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ca14-147">Nome</span><span class="sxs-lookup"><span data-stu-id="1ca14-147">Name</span></span></th>
<th><span data-ttu-id="1ca14-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ca14-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-p109">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="1ca14-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1ca14-152">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="1ca14-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1ca14-p110">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="1ca14-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1ca14-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1ca14-155">7/7/2012</span></span></p>
<p><span data-ttu-id="1ca14-156">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="1ca14-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1ca14-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1ca14-157">7/3/2012</span></span></p>
<p><span data-ttu-id="1ca14-158">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="1ca14-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca14-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-p111">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="1ca14-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1ca14-162">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="1ca14-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1ca14-p112">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="1ca14-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1ca14-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1ca14-165">7/7/2012</span></span></p>
<p><span data-ttu-id="1ca14-166">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="1ca14-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1ca14-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1ca14-167">7/3/2012</span></span></p>
<p><span data-ttu-id="1ca14-168">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="1ca14-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-169"><strong>Produttore</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-169"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-170">Nome della società che ha prodotto il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-170">Name of the company that manufactured the IP phone.</span></span> <span data-ttu-id="1ca14-171">I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="1ca14-171">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca14-172"><strong>Versione hardware</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-172"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-173">Numero di versione del telefono IP; Se si utilizza il produttore e i filtri versione hardware, è possibile identificare in modo univoco un determinato tipo di telefono.</span><span class="sxs-lookup"><span data-stu-id="1ca14-173">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="1ca14-174">I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="1ca14-174">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-175"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-175"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-176">Identificatore del software utilizzato dal telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-176">Identifier for the software used by the IP phone.</span></span> <span data-ttu-id="1ca14-177">I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="1ca14-177">The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca14-178"><strong>Indirizzo MAC</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-178"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-179">Identificatore univoco per l'interfaccia di rete sul telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-179">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="1ca14-180">L'indirizzo MAC (Media Access Control) in genere viene assegnato al momento in cui il telefono è prodotto e viene collegato all'hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ca14-180">The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="1ca14-181">Per cercare i record relativi a uno specifico indirizzo MAC, è sufficiente immettere quell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="1ca14-181">To search for records pertaining to a specific MAC address simply enter that address.</span></span> <span data-ttu-id="1ca14-182">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1ca14-182">For example:</span></span></p>
<p><span data-ttu-id="1ca14-183">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="1ca14-183">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="1ca14-184">È necessario immettere l'indirizzo completo.</span><span class="sxs-lookup"><span data-stu-id="1ca14-184">You must enter the complete address.</span></span> <span data-ttu-id="1ca14-185">Un indirizzo parziale (ad esempio 00-08-5D) non restituisce dati.</span><span class="sxs-lookup"><span data-stu-id="1ca14-185">A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-186"><strong>Ultima attività prima di ogni giorno</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-186"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-187">Selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="1ca14-187">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ca14-188">Tutti</span><span class="sxs-lookup"><span data-stu-id="1ca14-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="1ca14-189">10  </span><span class="sxs-lookup"><span data-stu-id="1ca14-189">10</span></span></p></li>
<li><p><span data-ttu-id="1ca14-190">20</span><span class="sxs-lookup"><span data-stu-id="1ca14-190">20</span></span></p></li>
<li><p><span data-ttu-id="1ca14-191">30</span><span class="sxs-lookup"><span data-stu-id="1ca14-191">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca14-192"><strong>Ora ultima disconnessione prima di giorni</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-192"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-193">Selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="1ca14-193">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="1ca14-194">Tutti</span><span class="sxs-lookup"><span data-stu-id="1ca14-194">[All]</span></span></p></li>
<li><p><span data-ttu-id="1ca14-195">10  </span><span class="sxs-lookup"><span data-stu-id="1ca14-195">10</span></span></p></li>
<li><p><span data-ttu-id="1ca14-196">20</span><span class="sxs-lookup"><span data-stu-id="1ca14-196">20</span></span></p></li>
<li><p><span data-ttu-id="1ca14-197">30</span><span class="sxs-lookup"><span data-stu-id="1ca14-197">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-198"><strong>Prefisso URI utente</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-199">Indirizzo SIP dell'utente che ha utilizzato il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-199">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1ca14-200">Metriche</span><span class="sxs-lookup"><span data-stu-id="1ca14-200">Metrics</span></span>

<span data-ttu-id="1ca14-201">Nella tabella seguente sono elencate le informazioni fornite nel rapporto inventario telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-201">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="1ca14-202">Metriche del rapporto inventario telefoni IP</span><span class="sxs-lookup"><span data-stu-id="1ca14-202">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ca14-203">Nome</span><span class="sxs-lookup"><span data-stu-id="1ca14-203">Name</span></span></th>
<th><span data-ttu-id="1ca14-204">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="1ca14-204">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1ca14-205">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ca14-205">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-206"><strong>Produttore</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-206"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-207">Sì</span><span class="sxs-lookup"><span data-stu-id="1ca14-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ca14-208">Nome della società che ha prodotto il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-208">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca14-209"><strong>Versione hardware</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-209"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-210">Sì</span><span class="sxs-lookup"><span data-stu-id="1ca14-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ca14-211">Numero di versione del telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-211">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-212"><strong>Indirizzo MAC</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-212"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-213">Sì</span><span class="sxs-lookup"><span data-stu-id="1ca14-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ca14-214">Identificatore univoco per l'interfaccia di rete sul telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-214">Unique identifier for the network interface on the IP phone.</span></span> <span data-ttu-id="1ca14-215">L'indirizzo MAC è in genere assegnato al momento in cui il telefono è prodotto e viene collegato all'hardware del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ca14-215">The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca14-216"><strong>URI dell'utente</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-216"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-217">Sì</span><span class="sxs-lookup"><span data-stu-id="1ca14-217">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ca14-218">Indirizzo SIP dell'utente che ha utilizzato il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-218">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-219"><strong>Agente utente</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-219"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-220">Sì</span><span class="sxs-lookup"><span data-stu-id="1ca14-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ca14-221">Identificatore del software utilizzato dal telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-221">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca14-222"><strong>Ora ultimo accesso</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-222"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-223">Sì</span><span class="sxs-lookup"><span data-stu-id="1ca14-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ca14-224">Data e ora dell'ultimo accesso del telefono IP a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ca14-224">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca14-225"><strong>Ora ultima disconnessione</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-225"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-226">Sì</span><span class="sxs-lookup"><span data-stu-id="1ca14-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ca14-227">Data e ora dell'ultima disconnessione del telefono IP da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ca14-227">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca14-228"><strong>Ultima attività</strong></span><span class="sxs-lookup"><span data-stu-id="1ca14-228"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="1ca14-229">Sì</span><span class="sxs-lookup"><span data-stu-id="1ca14-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="1ca14-230">Data e ora dell'ultimo utilizzo del telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ca14-230">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

