---
title: Pianificare l'integrazione di Skype for Business ed Exchange
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Riepilogo: esaminare questo argomento per informazioni su come integrare Skype for Business Server con Exchange Server 2016 o Exchange Server 2013.'
ms.openlocfilehash: 5edfdf44b50d2a58c097bed5ee83855f375ff895
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562838"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Pianificare l'integrazione di Skype for Business ed Exchange
 
**Riepilogo:** Leggere questo argomento per informazioni su come integrare Skype for Business Server con Exchange Server 2016 o Exchange Server 2013.
  
Prima di poter integrare Skype for Business Server e Exchange Server, è necessario verificare che sia Exchange Server che Skype for Business Server siano completamente installati e funzionanti. 
  
Per informazioni dettagliate sull'Exchange Server, vedere la documentazione relativa Exchange Server pianificazione e distribuzione per la versione di Exchange. 
   
Dopo aver eseguito i server, è necessario assegnare certificati di autenticazione da server a server a Skype for Business Server e Exchange Server; questi certificati consentono l'autenticazione Skype for Business Server e Exchange Server  per scambiare informazioni e comunicare tra loro. Quando si installa Exchange Server, viene creato automaticamente un certificato autofirmato con il nome Microsoft Exchange Server certificato di autenticazione. Questo certificato, disponibile nell'archivio certificati del computer locale, deve essere utilizzato per l'autenticazione da server a server Exchange Server. Per informazioni dettagliate sull'assegnazione di certificati in Exchange Server, vedere [Configure Mail Flow and Client Access](/exchange/configure-mail-flow-and-client-access-exchange-2013-help).
  
Ad Skype for Business Server è possibile utilizzare un certificato di Skype for Business Server esistente come certificato di autenticazione da server a server; ad esempio, il certificato predefinito può essere utilizzato anche come certificato OAuthTokenIssuer. Skype for Business Server consente di utilizzare qualsiasi certificato del server Web come certificato per l'autenticazione da server a server purché:
  
- Il certificato includa il nome del dominio SIP nel campo Oggetto.
    
- Lo stesso certificato sia configurato come certificato OAuthTokenIssuer in tutti i Front End Server.
    
- Il certificato abbia una lunghezza di almeno 2048 bit.
    
Per informazioni dettagliate sui certificati di autenticazione da server a server per Skype for Business Server, vedere [Assign a server-to-server authentication certificate to Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Dopo aver assegnato i certificati, è necessario configurare il servizio di individuazione automatica in Exchange Server. In Exchange Server, il servizio di individuazione automatica configura i profili utente e fornisce l'accesso Exchange servizi quando gli utenti accedono al sistema. Gli utenti presentano il servizio di individuazione automatica con l'indirizzo di posta elettronica e la password; a sua volta, i servizi forniscono all'utente informazioni quali:
  
- Informazioni di connessione sia per la connettività interna che per la connettività Exchange Server.
    
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
  
Dopo aver configurato il servizio di individuazione automatica, è necessario modificare le impostazioni di configurazione di Skype for Business Server OAuth, in modo che Skype for Business Server sappia dove trovare il servizio di individuazione automatica. Per modificare le impostazioni di configurazione di OAuth in Skype for Business Server, eseguire il comando seguente da Skype for Business Server Management Shell. Quando si esegue questo comando, assicurarsi di specificare l'URI per il servizio di individuazione automatica in esecuzione sul Exchange Server e di utilizzare **autodiscover.svc** per puntare al percorso del servizio **anziché aautodiscover.xml** (che punta al file XML utilizzato dal servizio):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Il parametro Identity nel comando precedente è facoltativo. questo perché Skype for Business Server solo di avere una singola raccolta globale di impostazioni di configurazione OAuth. Tra le altre cose, questo significa che è possibile configurare l'URL di individuazione automatica utilizzando questo comando leggermente più semplice: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " " 
> 
> [!NOTE]
> Per chi non avesse familiarità con la tecnologia, OAuth è un protocollo di autorizzazione standard utilizzato da numerosi siti Web di rilievo. Con OAuth, le credenziali e le password degli utenti non vengono passate da un computer all'altro. L'autenticazione e l'autorizzazione sono invece basate sullo scambio di token di sicurezza. Tali token consentono l'accesso a uno specifico set di risorse per un tempo specifico. 
  
Oltre a configurare il servizio di individuazione automatica, è inoltre necessario creare un record DNS per il servizio che punta alla propria Exchange Server. Ad esempio, se il servizio di individuazione automatica si trova in autodiscover.litwareinc.com sarà necessario creare un record DNS per autodiscover.litwareinc.com che si risolve nel nome di dominio completo del Exchange Server (ad esempio, atl-exchange-001.litwareinc.com).
  
Se si sta integrando Skype for Business Server con Exchange Online, i passaggi successivi sono in [Configure integration between on-premises Skype for Business Server and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), altrimenti vedere [Integrate Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Supporto delle funzionalità
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online è stato ritirato il 31 luglio 2021. Le Exchange elencate di seguito che includono il servizio non sono più supportate.

Nella tabella seguente vengono fornite informazioni dettagliate sulle funzionalità supportate in varie combinazioni di funzionalità online o locali per Exchange e Skype for Business.
  
|&nbsp;|Exchange 2016/2013/2010 (locale) + Skype for Business Server (locale)|Exchange Online + Skype for Business Server (locale)**|**Exchange 2010 (locale) + Skype for Business Online|Exchange 2016/2013(in locale) + Skype for Business Online**|**Exchange Online + Skype for Business Online|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presenza in Outlook   |Y   |Y   |Y   |Y   |Y   |
|Rispondere tramite messaggistica istantanea, chiamata PSTN, Skype chiamata o videochiamata da un Outlook posta elettronica   |Y   |Y   |Y   |Y   |Y   |
|Pianificare e partecipare a riunioni online tramite Outlook   |Y   |Y   |Y   |Y   |Y   |
|Presenza in Outlook Web App   |Y   |Y   |N   |N   |Y   |
|Rispondere tramite messaggistica istantanea, chiamata PSTN, Skype chiamata o videochiamata da un OWA posta elettronica   |Y   |Y   |N   |N   |Y   |
|Pianificare e partecipare a riunioni online tramite Outlook Web App   |Y   |Y   |N   |N   |Y   |
|Messaggistica istantanea/Presenza nei client mobili   |Y   |Y   |Y   |Y   |Y   |
|Partecipare a riunioni online nei client mobili   |Y   |Y   |Y   |Y   |Y   |
|Pubblicare lo stato in base Outlook informazioni sulla disponibilità del calendario   |Y   |Y   |Y   |Y   |Y   |
|Elenco contatti (tramite l'archivio contatti unificato)   |Y (necessario Exchange 2016/2013)   |Y   |N   |N   |Y   |
|Foto contatto ad alta risoluzione (richiede Almeno Lync 2013 o Skype for Business client. Non supportato per LWA, app per dispositivi mobili, Lync 2010, Lync per Mac e altri client meno recenti.   |Y (necessario Exchange 2016/2013)   |Y   |N   |Y   |Y   |
|Delega riunione   |Y   |Y   |Y   |Y   |Y   |
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente   |Y   |Y   |Y   |Y   |Y   |
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange   |Y (necessario Exchange 2016/2013)   |Y   |N   |N   |Y   |
|Ricerca contenuto archiviato   |Y (necessario Exchange 2016/2013)   |Y   |N   |N   |Y   |
|Exchange segreteria telefonica di messaggistica unificata   |Y   |Y   |N   |N   |N   |
|Cronologia conversazioni sul lato server   |Y   |Y   |N   |Y   |Y   |

> [!NOTE]
> È disponibile un servizio di Cloud Voicemail supportato per Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013.
> 

## <a name="see-also"></a>Vedere anche
<a name="feature_support"> </a>

[Configurare l'integrazione tra Skype for Business Server locali e Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurare OAuth tra Skype for Business Online e Exchange locale](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Come integrare Exchange Server 2013 con Lync Server 2013, Skype for Business Online o una distribuzione ibrida di Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Configurare le applicazioni partner in Skype for Business Server e Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)