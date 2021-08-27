---
title: Configurare SharePoint Server per la ricerca di dati Skype for Business archiviati
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Riepilogo: configurare SharePoint Server per cercare i dati archiviati da Exchange Server e Skype for Business Server.'
ms.openlocfilehash: 8a27bb170f0e089d702417a32d93eee96c7c6299
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604205"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurare SharePoint Server per la ricerca di dati Skype for Business archiviati
 
**Riepilogo:** Configurare SharePoint Server per cercare i dati archiviati da Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.
  
Uno dei principali vantaggi dell'archiviazione delle trascrizioni di messaggistica istantanea e conferenze Web in Exchange Server anziché Skype for Business Server è che l'archiviazione dei dati nella stessa posizione consente agli amministratori di utilizzare un singolo strumento per cercare i dati Exchange archiviati e/o i dati Skype for Business Server archiviati. Poiché tutti i dati vengono archiviati nella stessa posizione (Exchange) qualsiasi strumento in grado di cercare i dati Exchange archiviati può anche cercare i dati Skype for Business Server archiviati.
  
Uno strumento che semplifica la ricerca di dati archiviati è Microsoft SharePoint Server 2013. Se si desidera utilizzare SharePoint per cercare dati Skype for Business Server, è necessario innanzitutto completare tutti i passaggi necessari per configurare l'archiviazione Exchange in Skype for Business Server. Dopo Exchange Server e Skype for Business Server, è necessario installare l'API gestita di Exchange [Web Services](https://go.microsoft.com/fwlink/p/?LinkId=258305) nel SharePoint Server. Il file scaricato (EWSManagedAPI.msi) può essere salvato in qualsiasi cartella del SharePoint server.
  
Al termine del download del file, eseguire la procedura seguente in SharePoint Server:
  
1. Aprire una finestra dei comandi facendo clic su **Start**, scegliere **Tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi fare clic su **Esegui come amministratore**.
    
2. Nella finestra dei comandi passare dalla directory corrente alla cartella in cui è stato salvato il file EWSManagedAPI.msi utilizzando il comando cd. Ad esempio, se il file è stato salvato in C:\Downloads, digitare il comando seguente nella finestra di comando e quindi premere INVIO:
    
   ```console
   cd C:\Downloads
   ```

3. Per installare l'API, digitare il comando seguente e premere INVIO:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Dopo l'installazione dell'API, reimpostare IIS digitando il comando seguente e premendo INVIO:
    
   ```console
   iisreset
   ```

Dopo Exchange servizi Web è necessario configurare l'autenticazione da server a server tra SharePoint Server e Exchange Server. A tale scopo, aprire innanzitutto SharePoint Management Shell ed eseguire il set di comandi seguente:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Verificare e utilizzare l'URI del servizio di individuazione automatica. Non usare l'URI di esempio https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 . 
  
Dopo aver creato l'autorità emittente di token e aver configurato il servizio token, esegui questi comandi, assicurandoti di sostituire l'URL del sito di SharePoint con l'URL di esempiohttp://atl-sharepoint-001:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Per configurare l'autenticazione da server a server per Exchange Server, aprire Exchange Management Shell ed eseguire un comando simile al seguente (presupponendo che Exchange sia stato installato nell'unità C: e che utilizzi il percorso di cartella predefinito):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) in tutti i server cassette postali Exchange e accesso client. Per riavviare IIS è possibile utilizzare un comando simile al seguente, che riavvia il servizio sul computer atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Questo comando può essere eseguito da Exchange Management Shell o da qualsiasi altra finestra di comando.
  
Eseguire quindi un comando simile al seguente, che concede all'utente specificato (in questo esempio kenmyer) il diritto di eseguire l'individuazione in Exchange:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Dopo aver stabilito l'autenticazione da server a server tra Exchange e SharePoint, il passaggio successivo consiste nel creare un sito eDiscovery in SharePoint. Questa operazione può essere eseguita eseguendo comandi simili ai seguenti da SharePoint Management Shell:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" è l'abbreviazione di "individuazione elettronica" e in genere si riferisce al processo di ricerca in archivi elettronici di elementi che possano essere "considerati ragionevolmente ammissibili come prova" in un tribunale. 
  
Quando il nuovo sito è pronto, il passaggio successivo consiste nel configurare Exchange Server come origine dei risultati per SharePoint. È possibile eseguire questa operazione completando la procedura seguente dalla SharePoint Amministrazione centrale:
  
1. Nella pagina Amministrazione centrale fare clic su **Gestisci applicazioni di servizio**, quindi su **Applicazione servizio di ricerca**.
    
2. In Applicazione servizio di ricerca: nella pagina Amministrazione ricerca fare clic su **Origini di risultati** e quindi su **Nuova origine dei risultati**.
    
3. Nel riquadro **Nuova origine dei risultati** specificare un nome per la nuova origine dei risultati, ad esempio **Microsoft Exchange**, nella casella **Nome**. Selezionare **Exchange** come protocollo di origine dei risultati **e** quindi immettere l'URL di origine dei servizi Web per il server Exchange nella casella **URL** origine Exchange risultati. L'URL di origine avrà un aspetto simile al seguente:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Verificare che l'opzione **Usa individuazione automatica** non sia selezionata, quindi fare clic su **OK**.
    
Infine, creare un nuovo caso di eDiscovery e un nuovo set di eDiscovery completando la procedura seguente dal sito di individuazione SharePoint (ad esempio,https://atl-sharepoint-001/sites/discovery):
  
1. Nella pagina Contenuto del sito fare clic su **Crea un nuovo caso**.
    
2. In Contenuto del sito: nella pagina Nuovo sito di SharePoint inserire l'alias di posta elettronica dell'utente, ad esempio **kenmyer**, nella casella **Titolo**, quindi aggiungere lo stesso URL nella casella **Indirizzo sito Web**. Verrà creato un URL simile a questo:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Fare clic su **Crea**.
    
4. Quando viene visualizzata la pagina Set eDiscovery, fare clic su **nuovo elemento** in **Identity and Preserve: Discovery Sets**.
    
5. Nella pagina New: Discovery Set inserire l'alias di posta elettronica dell'utente nella casella **Discovery Set Name**. Immettere **eDiscovery \\ Lync** _ nella casella _ *Filtro** e quindi fare clic su Aggiungi **Gestisci &amp; origini.**
    
6. Nella pagina Aggiungi origini, immettere l'alias di posta elettronica &amp; dell'utente nella prima casella di testo in Cassette **postali**. Fare clic sull'icona Controlla cassetta postale accanto alla casella di testo per verificare che SharePoint sia in grado di connettersi alla cassetta postale specificata.
    
7. Fare clic su **OK**.
    
8. Nella pagina Set eDiscovery fare clic su **Salva** per salvare il nuovo set eDiscovery.
    
A questo punto è possibile cercare nella cassetta postale specificata (kenmyer) e/o abilitare In-Place conserva allo stesso modo qualsiasi altro contenuto o origine dei risultati SharePoint.
  

