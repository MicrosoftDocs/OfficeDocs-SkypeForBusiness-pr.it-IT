---
title: Piano di integrazione di Skype for Business Server 2015 con Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Riepilogo: rivedere questo argomento per informazioni su come integrare Skype for Business Server con Exchange Server 2016 o Exchange Server 2013.'
ms.openlocfilehash: 54a079a550b1c915d9ffc124b1608a3fd3f2a5ef
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991481"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Piano di integrazione di Skype for Business Server 2015 con Exchange
 
**Riepilogo:** Esaminare questo argomento per informazioni su come integrare Skype for Business Server con Exchange Server 2016 o Exchange Server 2013.
  
Prima di poter integrare Skype for Business Server ed Exchange Server, è necessario assicurarsi che Exchange Server e Skype for Business Server siano completamente installati e operativi. 
  
Per informazioni dettagliate sull'installazione di Exchange Server, vedere la documentazione relativa alla pianificazione e distribuzione di Exchange Server per la versione di Exchange in questione. 
   
Dopo che i server sono in funzione, è necessario assegnare certificati di autenticazione da server a server a Skype for Business Server ed Exchange Server; questi certificati consentono a Skype for Business Server ed Exchange Server di scambiare informazioni e comunicare tra loro. Quando si installa Exchange Server, viene creato un certificato autofirmato con il nome certificato di autenticazione di Microsoft Exchange Server. Questo certificato, disponibile nell'archivio certificati del computer locale, deve essere usato per l'autenticazione da server a server in Exchange Server. Per informazioni dettagliate sull'assegnazione di certificati in Exchange Server, vedere [configurare il flusso di posta e l'accesso client](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Per Skype for Business Server è possibile usare un certificato di Skype for Business Server esistente come certificato di autenticazione da server a server; ad esempio, il certificato predefinito può essere usato anche come certificato OAuthTokenIssuer. Skype for Business Server consente di usare qualsiasi certificato del server Web come certificato per l'autenticazione da server a server purché:
  
- Il certificato include il nome del dominio SIP nel campo oggetto.
    
- Lo stesso certificato è configurato come certificato OAuthTokenIssuer in tutti i server front-end.
    
- Il certificato ha una lunghezza di almeno 2048 bit.
    
Per informazioni dettagliate sui certificati di autenticazione da server a server per Skype for Business Server, vedere [assegnare un certificato di autenticazione da server a server a Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Dopo aver assegnato i certificati, è necessario configurare il servizio di individuazione automatica su Exchange Server. In Exchange Server il servizio di individuazione automatica configura i profili utente e consente l'accesso ai servizi di Exchange quando gli utenti accedono al sistema. Gli utenti presentano il servizio di individuazione automatica con l'indirizzo di posta elettronica e la password; a sua volta, i servizi conferiscono all'utente informazioni come:
  
- Informazioni sulla connessione per la connettività interna ed esterna a Exchange Server.
    
- Posizione del server delle cassette postali dell'utente.
    
- URL per le funzionalità di Outlook, ad esempio informazioni sulla disponibilità, messaggistica unificata e Rubrica fuori rete.
    
- Impostazioni del server Outlook Anywhere.
    
Il servizio di individuazione automatica deve essere configurato prima di poter integrare Skype for Business Server ed Exchange Server. Puoi verificare se il servizio di individuazione automatica è stato configurato eseguendo il comando seguente da Exchange Server Management Shell e controllando il valore della proprietà AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Se questo valore è vuoto, devi assegnare un URI al servizio di individuazione automatica. In genere questo URI avrà un aspetto simile al seguente:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Puoi assegnare l'URI di individuazione automatica eseguendo un comando simile al seguente:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Per informazioni dettagliate sul servizio di individuazione automatica, vedere [servizio di individuazione automatica](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Dopo aver configurato il servizio di individuazione automatica, è necessario modificare le impostazioni di configurazione OAuth di Skype for Business Server. Questo garantisce che Skype for Business Server sappia dove trovare il servizio di individuazione automatica. Per modificare le impostazioni di configurazione OAuth in Skype for Business Server, eseguire il comando seguente dall'interno di Skype for Business Server Management Shell. Quando esegui questo comando, assicurati di specificare l'URI per il servizio di individuazione automatica in uso nel server Exchange e usi **autodiscover. svc** per puntare alla posizione del servizio invece di **autodiscover. XML** (che punta al file XML usato dal servizio):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Il parametro Identity nel comando precedente è facoltativo. Questo perché Skype for Business Server consente solo di avere una singola raccolta globale di impostazioni di configurazione OAuth. Tra le altre cose, questo significa che puoi configurare l'URL di individuazione automatica usando questo comando leggermente più semplice: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> Se non si ha familiarità con la tecnologia, OAuth è un protocollo di autorizzazione standard usato da numerosi siti Web principali. Con OAuth, le credenziali utente e le password non vengono passate da un computer a un altro. L'autenticazione e l'autorizzazione si basano invece sullo scambio di token di sicurezza. questi token concedono l'accesso a un set di risorse specifico per un determinato periodo di tempo. 
  
Oltre a configurare il servizio di individuazione automatica, è necessario creare anche un record DNS per il servizio che punta al server Exchange. Ad esempio, se il servizio di individuazione automatica si trova in autodiscover.litwareinc.com, è necessario creare un record DNS per autodiscover.litwareinc.com che venga risolto nel nome di dominio completo del server di Exchange, ad esempio atl-exchange-001.litwareinc.com).
  
Se si integra Skype for Business Server con Exchange Online, i passaggi successivi si trovano in [configurare l'integrazione tra Skype for Business Server locale e Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), altrimenti vedere [integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Supporto delle funzionalità
<a name="feature_support"> </a>

La tabella seguente descrive in dettaglio le caratteristiche supportate in varie combinazioni di online o locali per Exchange e Skype for business.
  
||**Exchange 2016/2013/2010 (locale) + Skype for Business Server (locale)**|**Exchange Online + Skype for Business Server (locale)**|**Exchange 2010 (locale) + Skype for business online**|**Exchange 2016/2013 (locale) + Skype for business online**|**Exchange Online + Skype for business online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presenza in Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Rispondere tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o videochiamata da un messaggio di posta elettronica di Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Presenza in Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Rispondere tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o videochiamata da un messaggio di posta elettronica OWA  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Pianificare e partecipare a riunioni online tramite Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Messaggistica istantanea/presenza nei client mobili  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Partecipare a riunioni online nei client mobili  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Elenco contatti (tramite l'archivio contatti unificato)  <br/> |Y (serve Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Foto di contatto ad alta risoluzione (richiede almeno Lync 2013 o client Skype for business. Non supportato per LWA, app per dispositivi mobili, Lync 2010, Lync per Mac e altri client meno recenti.  <br/> |Y (serve Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|Delega riunione  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|La cronologia delle conversazioni perse e i registri delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Archiviazione del contenuto (messaggistica istantanea e riunione) in Exchange  <br/> |Y (serve Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Cercare contenuto archiviato  <br/> |Y (serve Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Segreteria telefonica messaggistica unificata di Exchange  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Cronologia delle conversazioni lato server  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> È disponibile un servizio cloud Voicemail supportato per Skype for business online, Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013.
> 

## <a name="see-also"></a>Vedere anche
<a name="feature_support"> </a>

[Configurare l'integrazione tra Skype for Business Server e Outlook Web App locale](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurare OAuth tra Skype for business online e Exchange in locale](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Come integrare Exchange Server 2013 con Lync Server 2013, Skype for business online o una distribuzione ibrida di Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurare le applicazioni partner in Skype for Business Server e Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
