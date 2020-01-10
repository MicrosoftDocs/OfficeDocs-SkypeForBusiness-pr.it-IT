---
title: Configurare SharePoint Server per cercare i dati archiviati di Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Riepilogo: configurare SharePoint Server per la ricerca di dati archiviati da Exchange Server e Skype for Business Server.'
ms.openlocfilehash: d896d6acecd808e5b153e931b8c4b3a8ba62ed9a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003576"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurare SharePoint Server per cercare i dati archiviati di Skype for Business
 
**Riepilogo:** Configurare SharePoint Server per la ricerca di dati archiviati da Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.
  
Uno dei vantaggi principali per archiviare le trascrizioni di messaggistica istantanea e conferenze Web in Exchange Server invece di Skype for Business Server è che l'archiviazione dei dati nella stessa posizione consente agli amministratori di usare un singolo strumento per cercare i dati di Exchange archiviati e/o i dati archiviati di Skype for Business Server. Poiché tutti i dati sono archiviati nella stessa posizione (Exchange), qualsiasi strumento che può cercare dati di Exchange archiviati può cercare anche dati archiviati in Skype for Business Server.
  
Uno strumento che facilita la ricerca di dati archiviati è Microsoft SharePoint Server 2013. Se si vuole usare SharePoint per cercare i dati di Skype for Business Server, è prima di tutto necessario completare tutti i passaggi necessari per la configurazione dell'archiviazione di Exchange in Skype for Business Server. Dopo che Exchange Server e Skype for Business Server sono stati integrati correttamente, è necessario installare l' [API gestita di Exchange Web Services](https://go.microsoft.com/fwlink/p/?LinkId=258305) in SharePoint Server. Il file scaricato (EWSManagedAPI. msi) può essere salvato in qualsiasi cartella di SharePoint Server.
  
Dopo aver scaricato il file, completare la procedura seguente in SharePoint Server:
  
1. Aprire una finestra di comando facendo clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il **pulsante destro del mouse e**quindi scegliere **Esegui come amministratore**.
    
2. Nella finestra di comando usare il comando CD per cambiare la directory corrente nella cartella in cui è stato salvato il file EWSManagedAPI. msi. Ad esempio, se il file è stato salvato in C:\Downloads, digitare il comando seguente nella finestra di comando e quindi premere INVIO:
    
   ```console
   cd C:\Downloads
   ```

3. Per installare l'API, digitare il comando seguente e premere INVIO:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Dopo aver installato l'API, reimpostare IIS digitando il comando seguente e premendo INVIO:
    
   ```console
   iisreset
   ```

Dopo aver installato i servizi Web di Exchange, è necessario configurare l'autenticazione da server a server tra SharePoint Server ed Exchange Server. A tale scopo, aprire prima di tutto SharePoint Management Shell ed eseguire il set di comandi seguente:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Assicurati e usa l'URI per il servizio di individuazione automatica. Non usare l'URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1di esempio. 
  
Dopo aver creato l'emittente del token e configurato il servizio token, eseguire questi comandi, assicurandosi di sostituire l'URL del sito di SharePoint per l'URL di esempiohttp://atl-sharepoint-001:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Per configurare l'autenticazione da server a server per Exchange Server, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che usi il percorso della cartella predefinito):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) in tutti i server di cassette postali e accesso client di Exchange. È possibile riavviare IIS usando un comando simile a questo, che riavvia il servizio nel computer ATL-Exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando.
  
Esegui quindi un comando simile al seguente, che assegna all'utente specificato (in questo esempio kenmyer) il diritto di eseguire l'individuazione in Exchange:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Dopo aver stabilito l'autenticazione da server a server tra Exchange e SharePoint, il passaggio successivo consiste nel creare un sito di eDiscovery in SharePoint. Questa operazione può essere eseguita eseguendo comandi simili a quelli di SharePoint Management Shell:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" è l'abbreviazione di "Electronic Discovery" e in genere si riferisce al processo di ricerca di archivi elettronici per gli elementi che possono essere "ragionevolmente calcolati per portare ad una prova ammissibile" in tribunale. 
  
Quando il nuovo sito è pronto, il passaggio successivo consiste nel configurare Exchange Server per fungere da origine dei risultati per SharePoint. Per eseguire questa operazione, è possibile completare la procedura seguente dalla pagina Amministrazione centrale di SharePoint:
  
1. Nella pagina Amministrazione centrale fare clic su **Gestisci applicazioni di servizio** e quindi su **applicazione del servizio di ricerca**.
    
2. Nell'applicazione servizio di ricerca: pagina Amministrazione ricerca fare clic su **origini risultati** , quindi fare clic su **nuova origine dei risultati**.
    
3. Nel riquadro dell' **origine del nuovo risultato** immettere un nome per la nuova origine dei risultati, ad esempio **Microsoft Exchange**, nella casella **nome** . Selezionare **Exchange** come **protocollo**di origine dei risultati e quindi immettere l'URL di origine dei servizi Web per il server Exchange nella casella **URL di origine di Exchange** . L'URL di origine dovrebbe avere un aspetto simile al seguente:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Verificare che l'opzione **Usa individuazione automatica** non sia selezionata e quindi fare clic su **OK**.
    
Infine, creare un nuovo caso di eDiscovery e un nuovo set di eDiscovery completando la procedura seguente dal sito di individuazione di SharePoint, ad esempiohttps://atl-sharepoint-001/sites/discovery):
  
1. Nella pagina contenuto del sito fare clic su **Crea un nuovo caso**.
    
2. Nella pagina contenuto del sito: nuovo sito di SharePoint immettere l'alias di posta elettronica dell'utente, ad esempio **kenmyer**, nella casella **titolo** e quindi aggiungere lo stesso URL alla casella **Indirizzo sito Web** . Ciò comporterà un URL simile al seguente:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Fare clic su **Crea**.
    
4. Quando viene visualizzata la pagina set di eDiscovery, fare clic su **nuovo elemento** in **identità e Mantieni: set di individuazione**.
    
5. Nella pagina New: Discovery set immettere l'alias di posta elettronica dell'utente nella casella **nome set di individuazione** . Immettere **eDiscovery Lync\\*** nella casella **filtro** e quindi fare clic **su &amp; Aggiungi Gestisci origini**.
    
6. Nella pagina Add &amp; Manage Sources immettere l'alias di posta elettronica dell'utente nella prima casella di testo in **cassette postali**. Fare clic sull'icona di controllo della cassetta postale situata accanto al manuale per verificare che SharePoint possa connettersi alla cassetta postale specificata.
    
7. Fare clic su **OK**.
    
8. Nella pagina set eDiscovery fare clic su **Salva** per salvare il nuovo set di eDiscovery.
    
A questo punto è possibile eseguire una ricerca nella cassetta postale specificata (kenmyer) e/o abilitare il blocco sul posto nello stesso modo per qualsiasi altro contenuto o origine dei risultati di SharePoint.
  

