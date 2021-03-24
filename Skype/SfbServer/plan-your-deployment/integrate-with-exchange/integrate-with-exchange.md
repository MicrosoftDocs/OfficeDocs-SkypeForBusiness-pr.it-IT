---
title: Pianificare l'integrazione di Skype for Business ed Exchange
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Riepilogo: esaminare questo argomento per informazioni su come integrare Skype for Business Server con Exchange Server 2016 o Exchange Server 2013.'
ms.openlocfilehash: 6b2fdab1a25db7d56c99e965877cb684d102da36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098672"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Pianificare l'integrazione di Skype for Business ed Exchange
 
**Riepilogo:** Leggere questo argomento per informazioni su come integrare Skype for Business Server con Exchange Server 2016 o Exchange Server 2013.
  
Prima di poter integrare Skype for Business Server e Exchange Server, è necessario verificare che sia Exchange Server che Skype for Business Server siano completamente installati e funzionanti. 
  
Per informazioni dettagliate sull'Exchange Server, vedere la documentazione relativa Exchange Server pianificazione e distribuzione per la versione di Exchange in esecuzione. 
   
Dopo l'esecuzione dei server, è necessario assegnare certificati di autenticazione da server a server sia a Skype for Business Server che Exchange Server; questi certificati consentono a Skype for Business Server e Exchange Server di scambiare informazioni e comunicare tra loro. Quando si installa Exchange Server, viene creato automaticamente un certificato autofirmato con Microsoft Exchange Server certificato di autenticazione. Questo certificato, disponibile nell'archivio certificati del computer locale, deve essere utilizzato per l'autenticazione da server a server in Exchange Server. Per informazioni dettagliate sull'assegnazione di certificati in Exchange Server, vedere [Configure Mail Flow and Client Access](/exchange/configure-mail-flow-and-client-access-exchange-2013-help).
  
Per Skype for Business Server è possibile utilizzare un certificato di Skype for Business Server esistente come certificato di autenticazione da server a server. ad esempio, il certificato predefinito può essere usato anche come certificato OAuthTokenIssuer. Skype for Business Server consente di utilizzare qualsiasi certificato del server Web come certificato per l'autenticazione da server a server purché:
  
- Il certificato includa il nome del dominio SIP nel campo Oggetto.
    
- Lo stesso certificato sia configurato come certificato OAuthTokenIssuer in tutti i Front End Server.
    
- Il certificato abbia una lunghezza di almeno 2048 bit.
    
Per informazioni dettagliate sui certificati di autenticazione da server a server per Skype for Business Server, vedere Assegnare un certificato di autenticazione [da server a server a Skype for Business Server.](../../manage/authentication/assign-a-server-to-server-certificate.md)
  
Dopo aver assegnato i certificati, è necessario configurare il servizio di individuazione automatica in Exchange Server. In Exchange Server, il servizio di individuazione automatica configura i profili utente e fornisce l'accesso ai servizi di Exchange quando gli utenti accedono al sistema. Gli utenti presentano il servizio di individuazione automatica con l'indirizzo di posta elettronica e la password; a sua volta, i servizi forniscono all'utente informazioni quali:
  
- Informazioni di connessione per la connettività interna ed esterna a Exchange Server.
    
- Posizione del server Cassette postali dell'utente.
    
- URL per caratteristiche Outlook quali le informazioni di libero/occupato, la messaggistica unificata e la rubrica offline.
    
- Impostazioni del server Outlook via Internet.
    
Il servizio di individuazione automatica deve essere configurato prima di poter integrare Skype for Business Server e Exchange Server. È possibile verificare se il servizio di individuazione automatica è stato configurato eseguendo il comando seguente da Exchange Server Management Shell e controllando il valore della proprietà AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Se il valore è vuoto, è necessario assegnare un URI al servizio di individuazione automatica. In genere questo URI sarà simile al seguente: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Per assegnare l'URI di individuazione automatica, è possibile eseguire un comando simile a questo:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Per informazioni dettagliate sul servizio di individuazione automatica, vedere [Autodiscover Service](/Exchange/architecture/client-access/autodiscover).
  
Dopo aver configurato il servizio di individuazione automatica, è necessario modificare le impostazioni di configurazione OAuth di Skype for Business Server. ciò garantisce che Skype for Business Server sappia dove trovare il servizio di individuazione automatica. Per modificare le impostazioni di configurazione OAuth in Skype for Business Server, eseguire il comando seguente da Skype for Business Server Management Shell. Quando si esegue questo comando, assicurarsi di specificare l'URI per il servizio di individuazione automatica in esecuzione sul Exchange Server e di utilizzare **autodiscover.svc** per puntare al percorso del servizio anziché **aautodiscover.xml** (che punta al file XML utilizzato dal servizio):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Il parametro Identity nel comando precedente è facoltativo. questo perché Skype for Business Server consente solo di avere una singola raccolta globale di impostazioni di configurazione OAuth. Tra le altre cose, questo significa che è possibile configurare l'URL di individuazione automatica utilizzando questo comando leggermente più semplice: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " " 
> 
> [!NOTE]
> Per chi non avesse familiarità con la tecnologia, OAuth è un protocollo di autorizzazione standard utilizzato da numerosi siti Web di rilievo. Con OAuth, le credenziali e le password degli utenti non vengono passate da un computer all'altro. L'autenticazione e l'autorizzazione sono invece basate sullo scambio di token di sicurezza. Tali token consentono l'accesso a uno specifico set di risorse per un tempo specifico. 
  
Oltre a configurare il servizio di individuazione automatica, è necessario creare anche un record DNS per il servizio che punta alla propria Exchange Server. Ad esempio, se il servizio di individuazione automatica si trova in autodiscover.litwareinc.com sarà necessario creare un record DNS per autodiscover.litwareinc.com che si risolve nel nome di dominio completo del Exchange Server (ad esempio, atl-exchange-001.litwareinc.com).
  
Se si sta integrando Skype for Business Server con Exchange Online, i passaggi successivi sono in Configurare l'integrazione tra Skype for Business Server locale e [Outlook Web App,](../../deploy/integrate-with-exchange-server/outlook-web-app.md)altrimenti vedere [Integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Supporto delle funzionalità
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021 dopo che le integrazioni di Exchange elencate di seguito che includono il servizio non saranno più supportate.

Nella tabella seguente vengono fornite informazioni dettagliate sulle funzionalità supportate in varie combinazioni di exchange e Skype for Business online o locali.
  
||**Exchange 2016/2013/2010 (locale) + Skype for Business Server (locale)**|**Exchange Online + Skype for Business Server (locale)**|**Exchange 2010 (locale) + Skype for Business online**|**Exchange 2016/2013 (locale) + Skype for Business online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presenza in Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Rispondere tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o videochiamata da un messaggio di posta elettronica di Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Presenza in Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Rispondere tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o videochiamata da OWA posta elettronica  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Pianificare e partecipare a riunioni online tramite Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Messaggistica istantanea/Presenza nei client mobili  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Partecipare a riunioni online nei client mobili  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Elenco contatti (tramite l'archivio contatti unificato)  <br/> |Y (necessario Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Foto di contatto ad alta risoluzione (richiede almeno i client Lync 2013 o Skype for Business. Non supportato per LWA, app per dispositivi mobili, Lync 2010, Lync per Mac e altri client meno recenti.  <br/> |Y (necessario Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|Delega riunione  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> |Y (necessario Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Ricerca contenuto archiviato  <br/> |Y (necessario Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Casella vocale di messaggistica unificata di Exchange  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Cronologia conversazioni sul lato server  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> È disponibile un servizio di segreteria telefonica cloud supportato per Skype for Business online, Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013.
> 

## <a name="see-also"></a>Vedere anche
<a name="feature_support"> </a>

[Configurare l'integrazione tra Skype for Business Server locale e Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurare OAuth tra Skype for Business online ed Exchange locale](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Come integrare Exchange Server 2013 con Lync Server 2013, Skype for Business online o una distribuzione ibrida di Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Configurare le applicazioni partner in Skype for Business Server e Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)