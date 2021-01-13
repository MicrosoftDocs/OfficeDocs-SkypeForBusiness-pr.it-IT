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
description: 'Riepilogo: leggere questo argomento per informazioni su come integrare Skype for Business Server con Exchange Server 2016 o Exchange Server 2013.'
ms.openlocfilehash: f2a9dfc718b7891a0cbe9b7b1455df24531a6ed0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810101"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Pianificare l'integrazione di Skype for Business ed Exchange
 
**Riepilogo:** Leggere questo argomento per informazioni su come integrare Skype for Business Server con Exchange Server 2016 o Exchange Server 2013.
  
Prima di poter integrare Skype for Business Server e Exchange Server, è necessario assicurarsi che sia Exchange Server che Skype for Business Server siano completamente installati e in esecuzione. 
  
Per informazioni dettagliate sull'installazione di Exchange Server, vedere la documentazione relativa alla pianificazione e alla distribuzione di Exchange Server per la versione di Exchange. 
   
Dopo l'esecuzione dei server, è necessario assegnare certificati di autenticazione da server a server sia a Skype for Business Server che a Exchange Server; questi certificati consentono a Skype for Business Server e Exchange Server di scambiare informazioni e comunicare tra loro. Quando si installa Exchange Server, viene creato un certificato autofirmato con il nome del certificato di autenticazione di Microsoft Exchange Server. Questo certificato, che può essere trovato nell'archivio certificati del computer locale, deve essere utilizzato per l'autenticazione da server a server in Exchange Server. Per informazioni dettagliate sull'assegnazione dei certificati in Exchange Server, vedere [Configure Mail Flow and Client Access](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Per Skype for Business Server, è possibile utilizzare un certificato di Skype for Business Server esistente come certificato di autenticazione da server a server; ad esempio, il certificato predefinito può essere utilizzato anche come certificato di OAuthTokenIssuer. Skype for Business Server consente di utilizzare qualsiasi certificato del server Web come certificato per l'autenticazione da server a server purché:
  
- Il certificato includa il nome del dominio SIP nel campo Oggetto.
    
- Lo stesso certificato sia configurato come certificato OAuthTokenIssuer in tutti i Front End Server.
    
- Il certificato abbia una lunghezza di almeno 2048 bit.
    
Per informazioni dettagliate sui certificati di autenticazione da server a server per Skype for Business Server, vedere [assegnare un certificato di autenticazione da server a server a Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Dopo aver assegnato i certificati, è necessario configurare il servizio di individuazione automatica su Exchange Server. In Exchange Server, il servizio di individuazione automatica configura i profili utente e fornisce l'accesso ai servizi di Exchange quando gli utenti accedono al sistema. Gli utenti presentano il servizio di individuazione automatica con l'indirizzo di posta elettronica e la password. a sua incirca, i servizi forniscono all'utente informazioni quali:
  
- Informazioni di connessione per la connettività sia interna che esterna a Exchange Server.
    
- Il percorso del server cassette postali dell'utente.
    
- URL per caratteristiche Outlook quali le informazioni di libero/occupato, la messaggistica unificata e la rubrica offline.
    
- Impostazioni del server Outlook via Internet.
    
È necessario configurare il servizio di individuazione automatica prima di poter integrare Skype for Business Server e Exchange Server. È possibile verificare se il servizio di individuazione automatica è stato configurato eseguendo il comando seguente da Exchange Server Management Shell e controllando il valore della proprietà AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Se il valore è vuoto, è necessario assegnare un URI al servizio di individuazione automatica. In genere, questo URI avrà un aspetto simile al seguente: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Per assegnare l'URI di individuazione automatica, è possibile eseguire un comando simile a questo:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Per informazioni dettagliate sul servizio di individuazione automatica, vedere [servizio di individuazione automatica](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Dopo che il servizio di individuazione automatica è stato configurato, è necessario modificare le impostazioni di configurazione OAuth di Skype for Business Server; Questo garantisce che Skype for Business Server sia in grado di individuare il servizio di individuazione automatica. Per modificare le impostazioni di configurazione OAuth in Skype for Business Server, eseguire il comando riportato di seguito dall'interno di Skype for Business Server Management Shell. Quando si esegue questo comando, accertarsi di specificare l'URI per il servizio di individuazione automatica in esecuzione nel server Exchange e di utilizzare **autodiscover. svc** in modo che punti alla posizione del servizio anziché **autodiscover.xml** (che punta al file XML utilizzato dal servizio):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> Il parametro Identity nel comando precedente è facoltativo. Questo perché Skype for Business Server consente solo di disporre di una singola raccolta globale di impostazioni di configurazione OAuth. Tra le altre cose, questo significa che è possibile configurare l'URL di individuazione automatica utilizzando questo comando leggermente più semplice: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Per chi non avesse familiarità con la tecnologia, OAuth è un protocollo di autorizzazione standard utilizzato da numerosi siti Web di rilievo. Con OAuth, le credenziali e le password degli utenti non vengono passate da un computer all'altro. L'autenticazione e l'autorizzazione sono invece basate sullo scambio di token di sicurezza. Tali token consentono l'accesso a uno specifico set di risorse per un tempo specifico. 
  
Oltre alla configurazione del servizio di individuazione automatica, è inoltre necessario creare un record DNS per il servizio che punta al server Exchange. Ad esempio, se il servizio di individuazione automatica si trova in autodiscover.litwareinc.com, sarà necessario creare un record DNS per autodiscover.litwareinc.com che risolva il nome di dominio completo del server Exchange (ad esempio, atl-exchange-001.litwareinc.com).
  
Se si sta integrando Skype for Business Server con Exchange Online, i passaggi successivi sono in [Configure Integration between Skype for Business Server locale e Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), altrimenti vedere [integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Supporto delle funzionalità
<a name="feature_support"> </a>

>[!Important]
> Skype for business online si ritirerà il 31 luglio 2021 dopo che le integrazioni di Exchange elencate di seguito che includono il servizio non saranno più supportate.

Nella tabella seguente vengono illustrate le caratteristiche supportate in diverse combinazioni di online o locali per Exchange e Skype for business.
  
||**Exchange 2016/2013/2010 (in locale) + Skype for Business Server (in locale)**|**Exchange Online + Skype for Business Server (in locale)**|**Exchange 2010 (in locale) + Skype for business online**|**Exchange 2016/2013 (locale) + Skype for business online**|**Exchange Online + Skype for business online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presenza in Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Rispondere tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o chiamata video da un messaggio di posta elettronica di Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Pianificare e partecipare a riunioni online tramite Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Presenza in Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Rispondi tramite messaggistica istantanea, chiamata PSTN, chiamata Skype o chiamata video da un messaggio di posta elettronica OWA  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Pianificare e partecipare a riunioni online tramite Outlook Web App  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Messaggistica istantanea/presenza nei client mobili  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Partecipare a riunioni online nei client mobili  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Pubblicare lo stato in base alle informazioni sulla disponibilità del calendario di Outlook  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Elenco contatti (tramite archivio contatti unificato)  <br/> |Y (necessità di Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Foto dei contatti ad alta risoluzione (richiede almeno Lync 2013 o client Skype for business). Non supportato per LWA, le app per dispositivi mobili, Lync 2010, Lync per Mac e altri client meno recenti.  <br/> |Y (necessità di Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|Delega riunione  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|La cronologia delle conversazioni perse e i log delle chiamate vengono scritti nella cassetta postale di Exchange dell'utente  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Contenuto di archiviazione (messaggistica istantanea e riunione) in Exchange  <br/> |Y (necessità di Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Ricerca contenuto archiviato  <br/> |Y (necessità di Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Segreteria telefonica di messaggistica unificata di Exchange  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Cronologia delle conversazioni sul fianco del server  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> È presente un servizio di segreteria telefonica cloud supportato per Skype for business online, Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013.
> 

## <a name="see-also"></a>Vedere anche
<a name="feature_support"> </a>

[Configurare l'integrazione tra Skype for Business Server locale e Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurare OAuth tra Skype for business online ed Exchange in locale](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrazione di Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Informazioni su come integrare Exchange Server 2013 con Lync Server 2013, Skype for business online o una distribuzione ibrida di Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurare le applicazioni partner in Skype for Business Server e Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
