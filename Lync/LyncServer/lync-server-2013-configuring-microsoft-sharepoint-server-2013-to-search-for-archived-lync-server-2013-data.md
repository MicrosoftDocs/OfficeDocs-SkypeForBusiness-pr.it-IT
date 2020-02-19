---
title: 'Lync Server 2013: configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Lync Server 2013 archiviati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04e9599e0790c3d3468273ba27ea26f28ed3d766
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="ce113-102">Configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Microsoft Lync Server 2013 archiviati</span><span class="sxs-lookup"><span data-stu-id="ce113-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce113-103">_**Ultimo argomento modificato:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="ce113-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="ce113-104">Uno dei principali vantaggi per l'archiviazione delle trascrizioni di messaggistica istantanea e Web Conferencing in Microsoft Exchange Server 2013 anziché Microsoft Lync Server 2013 è il fatto che l'archiviazione dei dati nello stesso percorso consente agli amministratori di utilizzare un singolo strumento per cercare i dati di Exchange archiviati e/o i dati di Lync Server archiviati.</span><span class="sxs-lookup"><span data-stu-id="ce113-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="ce113-105">Poiché tutti i dati vengono archiviati nello stesso luogo (Exchange), qualsiasi strumento in grado di eseguire la ricerca di dati di Exchange archiviati può anche cercare i dati archiviati di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce113-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="ce113-106">Uno strumento che facilita la ricerca dei dati archiviati è Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce113-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="ce113-107">Se si desidera utilizzare SharePoint per cercare i dati di Lync Server, è necessario prima completare tutti i passaggi necessari per la configurazione dell'archiviazione di Exchange in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce113-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="ce113-108">Dopo aver completato l'integrazione di Exchange 2013 e Lync Server 2013, è necessario installare l'API gestita di servizi Web Exchange versione 2,0 sul server di SharePoint. il programma di installazione per l'API può essere scaricato dall'area download Microsoft ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)).</span><span class="sxs-lookup"><span data-stu-id="ce113-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="ce113-109">Il file scaricato (EWSManagedAPI. msi) può essere salvato in una cartella qualsiasi del server di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ce113-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="ce113-110">Al termine del download del file, eseguire la procedura seguente in SharePoint Server:</span><span class="sxs-lookup"><span data-stu-id="ce113-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="ce113-111">Aprire una finestra dei comandi facendo clic su **Start**, scegliere **Tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi fare clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ce113-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="ce113-112">Nella finestra dei comandi passare dalla directory corrente alla cartella in cui è stato salvato il file EWSManagedAPI.msi utilizzando il comando **cd**.</span><span class="sxs-lookup"><span data-stu-id="ce113-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="ce113-113">Ad esempio, se il file è stato salvato in C:\\Downloads, digitare il comando seguente nella finestra di comando e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="ce113-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="ce113-114">Per installare l'API, digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="ce113-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="ce113-115">Al termine dell'installazione dell'API, riavviare IIS digitando questo comando seguito da INVIO:</span><span class="sxs-lookup"><span data-stu-id="ce113-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="ce113-116">Dopo l'installazione dei servizi Web di Exchange, è necessario configurare l'autenticazione da server a server tra SharePoint Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ce113-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="ce113-117">A tale scopo, aprire innanzitutto SharePoint 2013 Management Shell ed eseguire il seguente set di comandi:</span><span class="sxs-lookup"><span data-stu-id="ce113-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="ce113-118">Verificare e utilizzare l'URI del servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="ce113-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="ce113-119">Non utilizzare l'URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1di esempio.</span><span class="sxs-lookup"><span data-stu-id="ce113-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="ce113-120">Dopo aver creato l'autorità emittente di token e aver configurato il servizio token, eseguire questi comandi, assicurandosi di sostituire l'URL del sito di SharePoint per l'URL di esempio.http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="ce113-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="ce113-121">Per configurare l'autenticazione da server a server per Exchange 2013, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che utilizzi il percorso della cartella predefinito):</span><span class="sxs-lookup"><span data-stu-id="ce113-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="ce113-122">Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) su tutti i server cassette postali e accesso client di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce113-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="ce113-123">Per riavviare IIS è possibile utilizzare un comando simile al seguente, che riavvia il servizio sul computer atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="ce113-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="ce113-124">Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="ce113-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="ce113-125">Successivamente, eseguire un comando simile al seguente, che fornisce all'utente specificato (in questo esempio, kenmyer) il diritto all'individuazione su Exchange:</span><span class="sxs-lookup"><span data-stu-id="ce113-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="ce113-126">Dopo che è stata stabilita l'autenticazione da server a server tra Exchange e SharePoint, il passaggio successivo consiste nel creare un sito di eDiscovery in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ce113-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="ce113-127">Questa operazione può essere eseguita eseguendo comandi simili a quelli di SharePoint Management Shell:</span><span class="sxs-lookup"><span data-stu-id="ce113-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="ce113-128">"eDiscovery" è l'abbreviazione di "individuazione elettronica" e in genere si riferisce al processo di ricerca in archivi elettronici di elementi che possano essere "considerati ragionevolmente ammissibili come prova" in un tribunale.</span><span class="sxs-lookup"><span data-stu-id="ce113-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="ce113-129">Quando il nuovo sito è pronto, il passaggio successivo consiste nel configurare Exchange 2013 affinché funga da origine dei risultati per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ce113-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="ce113-130">È possibile eseguire questa operazione eseguendo la procedura seguente dalla pagina Amministrazione centrale SharePoint 2013:</span><span class="sxs-lookup"><span data-stu-id="ce113-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="ce113-131">Nella pagina Amministrazione centrale fare clic su **Gestisci applicazioni di servizio**, quindi su **Applicazione servizio di ricerca**.</span><span class="sxs-lookup"><span data-stu-id="ce113-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="ce113-132">In Applicazione servizio di ricerca: nella pagina Amministrazione ricerca fare clic su **Origini di risultati** e quindi su **Nuova origine dei risultati**.</span><span class="sxs-lookup"><span data-stu-id="ce113-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="ce113-133">Nel riquadro **Nuova origine dei risultati** specificare un nome per la nuova origine dei risultati, ad esempio **Microsoft Exchange**, nella casella **Nome**.</span><span class="sxs-lookup"><span data-stu-id="ce113-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="ce113-134">Selezionare **Exchange** come **protocollo**dell'origine dei risultati e quindi immettere l'URL di origine dei servizi Web per il server Exchange nella casella **URL di origine di Exchange** .</span><span class="sxs-lookup"><span data-stu-id="ce113-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="ce113-135">L'URL di origine avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ce113-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="ce113-136">Verificare che l'opzione **Usa individuazione automatica** non sia selezionata, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce113-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="ce113-137">Infine, creare un nuovo caso di eDiscovery e un nuovo set di eDiscovery completando la procedura seguente dal sito di individuazione di SharePoint, ad esempiohttps://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="ce113-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="ce113-138">Nella pagina Contenuto del sito fare clic su **Crea un nuovo caso**.</span><span class="sxs-lookup"><span data-stu-id="ce113-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="ce113-p110">In Contenuto del sito: nella pagina Nuovo sito di SharePoint inserire l'alias di posta elettronica dell'utente, ad esempio **kenmyer**, nella casella **Titolo**, quindi aggiungere lo stesso URL nella casella **Indirizzo sito Web**. Verrà creato un URL simile a questo:</span><span class="sxs-lookup"><span data-stu-id="ce113-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="ce113-141">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ce113-141">Click **Create**.</span></span>

4.  <span data-ttu-id="ce113-142">Quando viene visualizzata la pagina Set eDiscovery, fare clic su **nuovo elemento** in **Identity and Preserve: Discovery Sets**.</span><span class="sxs-lookup"><span data-stu-id="ce113-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="ce113-143">Nella pagina New: Discovery Set inserire l'alias di posta elettronica dell'utente nella casella **Discovery Set Name**.</span><span class="sxs-lookup"><span data-stu-id="ce113-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="ce113-144">Immettere \*\*eDiscovery Lync\* \*\* nella casella **filtro** e quindi fare clic su **Aggiungi & Gestisci origini**.</span><span class="sxs-lookup"><span data-stu-id="ce113-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="ce113-p112">Nella pagina Aggiungi e gestisci origini inserire l'alias di posta elettronica dell'utente nella prima casella di testo sotto **Cassette postali**. Fare clic sull'icona Controlla cassetta postale accanto alla casella di testo per verificare che SharePoint sia in grado di connettersi alla cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="ce113-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="ce113-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce113-147">Click **OK**.</span></span>

8.  <span data-ttu-id="ce113-148">Nella pagina Set eDiscovery fare clic su **Salva** per salvare il nuovo set eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ce113-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="ce113-149">A questo punto è possibile eseguire una ricerca nella cassetta postale specificata (kenmyer) e/o abilitare la conserva sul posto allo stesso modo per qualsiasi altro contenuto o origine dei risultati di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ce113-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

