---
title: Configurare SharePoint Server per cercare i dati archiviati di Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Riepilogo: configurare SharePoint Server per la ricerca di dati archiviati da Exchange Server e Skype for Business Server.'
ms.openlocfilehash: 2fb4b601e594ca48105afcf2e0c75107b2c6bceb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188123"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="df773-103">Configurare SharePoint Server per cercare i dati archiviati di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="df773-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="df773-104">**Riepilogo:** Configurare SharePoint Server per la ricerca di dati archiviati da Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="df773-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="df773-105">Uno dei vantaggi principali per archiviare la messaggistica istantanea e le trascrizioni di Web Conferencing in Exchange Server anziché in Skype for Business Server è che l'archiviazione dei dati nella stessa posizione consente agli amministratori di usare un singolo strumento per cercare i dati di Exchange archiviati e/o dati archiviati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="df773-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="df773-106">Poiché tutti i dati sono archiviati nella stessa posizione (Exchange), qualsiasi strumento che può cercare dati di Exchange archiviati può cercare anche dati archiviati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="df773-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="df773-107">Uno strumento che facilita la ricerca di dati archiviati è Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df773-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="df773-108">Se si vuole usare SharePoint per cercare i dati di Skype for Business Server, è prima di tutto necessario completare tutti i passaggi necessari per la configurazione dell'archiviazione di Exchange in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="df773-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="df773-109">Dopo che Exchange Server e Skype for Business Server sono stati integrati correttamente, è necessario installare l' [API gestita di Exchange Web Services](https://go.microsoft.com/fwlink/p/?LinkId=258305) in SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="df773-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="df773-110">Il file scaricato (EWSManagedAPI. msi) può essere salvato in qualsiasi cartella di SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="df773-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="df773-111">Dopo aver scaricato il file, completare la procedura seguente in SharePoint Server:</span><span class="sxs-lookup"><span data-stu-id="df773-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="df773-112">Aprire una finestra di comando facendo clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, \*\*\*\* fare clic con il pulsante destro del mouse e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="df773-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="df773-113">Nella finestra di comando usare il comando CD per cambiare la directory corrente nella cartella in cui è stato salvato il file EWSManagedAPI. msi.</span><span class="sxs-lookup"><span data-stu-id="df773-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="df773-114">Ad esempio, se il file è stato salvato in C:\Downloads, digitare il comando seguente nella finestra di comando e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="df773-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="df773-115">Per installare l'API, digitare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="df773-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="df773-116">Dopo aver installato l'API, reimpostare IIS digitando il comando seguente e premendo INVIO:</span><span class="sxs-lookup"><span data-stu-id="df773-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="df773-117">Dopo aver installato i servizi Web di Exchange, è necessario configurare l'autenticazione da server a server tra SharePoint Server ed Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="df773-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="df773-118">A tale scopo, aprire prima di tutto SharePoint Management Shell ed eseguire il set di comandi seguente:</span><span class="sxs-lookup"><span data-stu-id="df773-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="df773-119">Assicurati e usa l'URI per il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="df773-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="df773-120">Non usare l'URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1di esempio.</span><span class="sxs-lookup"><span data-stu-id="df773-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="df773-121">Dopo aver creato l'emittente del token e configurato il servizio token, eseguire questi comandi, assicurandosi di sostituire l'URL del sito di SharePoint per l'URL di esempiohttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="df773-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="df773-122">Per configurare l'autenticazione da server a server per Exchange Server, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che usi il percorso della cartella predefinito):</span><span class="sxs-lookup"><span data-stu-id="df773-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="df773-123">Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) in tutti i server di cassette postali e accesso client di Exchange.</span><span class="sxs-lookup"><span data-stu-id="df773-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="df773-124">È possibile riavviare IIS usando un comando simile a questo, che riavvia il servizio nel computer ATL-Exchange-001:</span><span class="sxs-lookup"><span data-stu-id="df773-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="df773-125">Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="df773-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="df773-126">Esegui quindi un comando simile al seguente, che assegna all'utente specificato (in questo esempio kenmyer) il diritto di eseguire l'individuazione in Exchange:</span><span class="sxs-lookup"><span data-stu-id="df773-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="df773-127">Dopo aver stabilito l'autenticazione da server a server tra Exchange e SharePoint, il passaggio successivo consiste nel creare un sito di eDiscovery in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="df773-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="df773-128">Questa operazione può essere eseguita eseguendo comandi simili a quelli di SharePoint Management Shell:</span><span class="sxs-lookup"><span data-stu-id="df773-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="df773-129">"eDiscovery" è l'abbreviazione di "Electronic Discovery" e in genere si riferisce al processo di ricerca di archivi elettronici per gli elementi che possono essere "ragionevolmente calcolati per portare ad una prova ammissibile" in tribunale.</span><span class="sxs-lookup"><span data-stu-id="df773-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="df773-130">Quando il nuovo sito è pronto, il passaggio successivo consiste nel configurare Exchange Server per fungere da origine dei risultati per SharePoint.</span><span class="sxs-lookup"><span data-stu-id="df773-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="df773-131">Per eseguire questa operazione, è possibile completare la procedura seguente dalla pagina Amministrazione centrale di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="df773-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="df773-132">Nella pagina Amministrazione centrale fare clic su **Gestisci applicazioni di servizio** e quindi su applicazione del servizio di **ricerca**.</span><span class="sxs-lookup"><span data-stu-id="df773-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="df773-133">Nell'applicazione servizio di ricerca: pagina Amministrazione ricerca fare clic su **origini risultati** , quindi fare clic su **nuova origine dei risultati**.</span><span class="sxs-lookup"><span data-stu-id="df773-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="df773-134">Nel riquadro dell' **origine del nuovo risultato** immettere un nome per la nuova origine dei risultati, ad esempio **Microsoft Exchange**, nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="df773-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="df773-135">Selezionare **Exchange** come **protocollo**di origine dei risultati e quindi immettere l'URL di origine dei servizi Web per il server Exchange nella casella **URL di origine di Exchange** .</span><span class="sxs-lookup"><span data-stu-id="df773-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="df773-136">L'URL di origine dovrebbe avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="df773-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="df773-137">Verificare che l'opzione **Usa individuazione automatica** non sia selezionata e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="df773-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="df773-138">Infine, creare un nuovo caso di eDiscovery e un nuovo set di eDiscovery completando la procedura seguente dal sito di individuazione di SharePoint, ad esempiohttps://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="df773-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="df773-139">Nella pagina contenuto del sito fare clic su **Crea un nuovo caso**.</span><span class="sxs-lookup"><span data-stu-id="df773-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="df773-140">Nella pagina contenuto del sito: nuovo sito di SharePoint immettere l'alias di posta elettronica dell'utente, ad esempio **kenmyer**, nella casella **titolo** e quindi aggiungere lo stesso URL alla casella **Indirizzo sito Web** .</span><span class="sxs-lookup"><span data-stu-id="df773-140">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box.</span></span> <span data-ttu-id="df773-141">Ciò comporterà un URL simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="df773-141">That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="df773-142">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="df773-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="df773-143">Quando viene visualizzata la pagina set di eDiscovery, fare clic su **nuovo elemento** in **identità e Mantieni: set di individuazione**.</span><span class="sxs-lookup"><span data-stu-id="df773-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="df773-144">Nella pagina New: Discovery set immettere l'alias di posta elettronica dell'utente nella casella **nome set di individuazione** .</span><span class="sxs-lookup"><span data-stu-id="df773-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="df773-145">Immettere **eDiscovery Lync\\**\* nella casella **filtro** e quindi fare clic **su &amp; Aggiungi Gestisci origini**.</span><span class="sxs-lookup"><span data-stu-id="df773-145">Enter **eDiscovery Lync\\**\* in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="df773-146">Nella pagina Add &amp; Manage Sources immettere l'alias di posta elettronica dell'utente nella prima casella di testo in **cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="df773-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="df773-147">Fare clic sull'icona di controllo della cassetta postale situata accanto al manuale per verificare che SharePoint possa connettersi alla cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="df773-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="df773-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="df773-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="df773-149">Nella pagina set eDiscovery fare clic su **Salva** per salvare il nuovo set di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="df773-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="df773-150">A questo punto è possibile eseguire una ricerca nella cassetta postale specificata (kenmyer) e/o abilitare il blocco sul posto nello stesso modo per qualsiasi altro contenuto o origine dei risultati di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="df773-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

