---
title: 'Lync Server 2013: configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Lync Server 2013 archiviati'
description: 'Lync Server 2013: configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Lync Server 2013 archiviati.'
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
ms.openlocfilehash: aeabe49bb4f4e71bac7017497f3aadd9799bf515
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542762"
---
# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Configurazione di Microsoft SharePoint Server 2013 per la ricerca di dati di Microsoft Lync Server 2013 archiviati

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-04_

Uno dei principali vantaggi per l'archiviazione delle trascrizioni di messaggistica istantanea e Web Conferencing in Microsoft Exchange Server 2013 anziché Microsoft Lync Server 2013 è il fatto che l'archiviazione dei dati nello stesso percorso consente agli amministratori di utilizzare un singolo strumento per cercare i dati di Exchange archiviati e/o i dati di Lync Server archiviati. Poiché tutti i dati vengono archiviati nello stesso luogo (Exchange), qualsiasi strumento in grado di eseguire la ricerca di dati di Exchange archiviati può anche cercare i dati archiviati di Lync Server.

Uno strumento che facilita la ricerca dei dati archiviati è Microsoft SharePoint Server 2013. Se si desidera utilizzare SharePoint per cercare i dati di Lync Server, è necessario prima completare tutti i passaggi necessari per la configurazione dell'archiviazione di Exchange in Lync Server. Dopo aver completato l'integrazione di Exchange 2013 e Lync Server 2013, è necessario installare l'API gestita di servizi Web Exchange versione 2,0 sul server di SharePoint. il programma di installazione per l'API può essere scaricato dall'area download Microsoft ( [https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305) ). Il file scaricato (EWSManagedAPI.msi) può essere salvato in una cartella qualsiasi del server di SharePoint.

Al termine del download del file, eseguire la procedura seguente in SharePoint Server:

1.  Aprire una finestra dei comandi facendo clic su **Start**, scegliere **Tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi fare clic su **Esegui come amministratore**.

2.  Nella finestra dei comandi passare dalla directory corrente alla cartella in cui è stato salvato il file EWSManagedAPI.msi utilizzando il comando **cd**. Ad esempio, se il file è stato salvato in C: \\ Downloads, digitare il comando seguente nella finestra di comando e quindi premere INVIO:
    
        cd C:\Downloads

3.  Per installare l'API, digitare il comando seguente e premere INVIO:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  Al termine dell'installazione dell'API, riavviare IIS digitando questo comando seguito da INVIO:
    
        iisreset

Dopo l'installazione dei servizi Web di Exchange, è necessario configurare l'autenticazione da server a server tra SharePoint Server 2013 ed Exchange 2013. A tale scopo, aprire innanzitutto SharePoint 2013 Management Shell ed eseguire il seguente set di comandi:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> Verificare e utilizzare l'URI del servizio di individuazione automatica. Non utilizzare l'URI di esempio https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 .



</div>

Dopo aver creato l'autorità emittente di token e aver configurato il servizio token, eseguire questi comandi, assicurandosi di sostituire l'URL del sito di SharePoint per l'URL di esempio. http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Per configurare l'autenticazione da server a server per Exchange 2013, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che utilizzi il percorso della cartella predefinito):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) su tutti i server cassette postali e accesso client di Exchange. Per riavviare IIS è possibile utilizzare un comando simile al seguente, che riavvia il servizio sul computer atl-exchange-001:

    iisreset atl-exchange-001

Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando.

Successivamente, eseguire un comando simile al seguente, che fornisce all'utente specificato (in questo esempio, kenmyer) il diritto all'individuazione su Exchange:

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Dopo che è stata stabilita l'autenticazione da server a server tra Exchange e SharePoint, il passaggio successivo consiste nel creare un sito di eDiscovery in SharePoint. Questa operazione può essere eseguita eseguendo comandi simili a quelli di SharePoint Management Shell:

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "eDiscovery" è l'abbreviazione di "individuazione elettronica" e in genere si riferisce al processo di ricerca in archivi elettronici di elementi che possano essere "considerati ragionevolmente ammissibili come prova" in un tribunale.



</div>

Quando il nuovo sito è pronto, il passaggio successivo consiste nel configurare Exchange 2013 affinché funga da origine dei risultati per SharePoint. È possibile eseguire questa operazione eseguendo la procedura seguente dalla pagina Amministrazione centrale SharePoint 2013:

1.  Nella pagina Amministrazione centrale fare clic su **Gestisci applicazioni di servizio**, quindi su **Applicazione servizio di ricerca**.

2.  In Applicazione servizio di ricerca: nella pagina Amministrazione ricerca fare clic su **Origini di risultati** e quindi su **Nuova origine dei risultati**.

3.  Nel riquadro **Nuova origine dei risultati** specificare un nome per la nuova origine dei risultati, ad esempio **Microsoft Exchange**, nella casella **Nome**. Selezionare **Exchange** come **protocollo**dell'origine dei risultati e quindi immettere l'URL di origine dei servizi Web per il server Exchange nella casella **URL di origine di Exchange** . L'URL di origine avrà un aspetto simile al seguente:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Verificare che l'opzione **Usa individuazione automatica** non sia selezionata, quindi fare clic su **OK**.

Infine, creare un nuovo caso di eDiscovery e un nuovo set di eDiscovery completando la procedura seguente dal sito di individuazione di SharePoint, ad esempio https://atl-sharepoint-001/sites/discovery):

1.  Nella pagina Contenuto del sito fare clic su **Crea un nuovo caso**.

2.  In Contenuto del sito: nella pagina Nuovo sito di SharePoint inserire l'alias di posta elettronica dell'utente, ad esempio **kenmyer**, nella casella **Titolo**, quindi aggiungere lo stesso URL nella casella **Indirizzo sito Web**. Verrà creato un URL simile a questo:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Fare clic su **Crea**.

4.  Quando viene visualizzata la pagina Set eDiscovery, fare clic su **nuovo elemento** in **Identity and Preserve: Discovery Sets**.

5.  Nella pagina New: Discovery Set inserire l'alias di posta elettronica dell'utente nella casella **Discovery Set Name**. Immettere **eDiscovery Lync \* ** nella casella **filtro** e quindi fare clic su **Aggiungi & Gestisci origini**.

6.  Nella pagina Aggiungi e gestisci origini inserire l'alias di posta elettronica dell'utente nella prima casella di testo sotto **Cassette postali**. Fare clic sull'icona Controlla cassetta postale accanto alla casella di testo per verificare che SharePoint sia in grado di connettersi alla cassetta postale specificata.

7.  Fare clic su **OK**.

8.  Nella pagina Set eDiscovery fare clic su **Salva** per salvare il nuovo set eDiscovery.

A questo punto è possibile effettuare una ricerca nella cassetta postale specificata (kenmyer) e/o abilitare In-Place in modo analogo a qualsiasi altro contenuto o origine dei risultati di SharePoint.

</div>

<span> </span>

</div>

</div>

</div>

