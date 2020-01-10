---
title: Configurare le applicazioni partner in Skype for Business Server 2015 ed Exchange Server
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
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: "Riepilogo: configurare l'autenticazione da server a server per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server."
ms.openlocfilehash: 004b9c1926f00cd869658ae0b90679897d20516b
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001256"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurare le applicazioni partner in Skype for Business Server ed Exchange Server
 
**Riepilogo:** Configurare l'autenticazione da server a server per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.
  
L'autenticazione da server a server richiede in genere due server che devono comunicare tra loro e un server token di sicurezza di terze parti. Se il server A e il server B devono comunicare, questi vengono in genere avviati contattando un server token e ottenendo un token di sicurezza mutuamente attendibile. Il server A presenta quindi il token di sicurezza al server B (e viceversa) per garantirne l'autenticità e l'attendibilità.
  
Tuttavia, questa è una regola generale. Skype for Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013 non hanno bisogno di usare un server token di terze parti quando comunicano tra loro; Questo perché questi prodotti server possono creare token di sicurezza che possono essere accettati uno dall'altro senza la necessità di un server token separato. Questa funzionalità è disponibile solo in Skype for Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013. Se è necessario configurare l'autenticazione da server a server con altri server, inclusi altri prodotti server Microsoft, sarà necessario farlo usando un server token di terze parti.
  
Per configurare l'autenticazione da server a server tra Skype for Business Server ed Exchange Server, è necessario eseguire due operazioni: 1) è necessario assegnare i certificati appropriati a ogni server; e 2) è necessario configurare ogni server come applicazione partner dell'altro server: ciò significa che è necessario configurare Skype for Business Server come applicazione partner per Exchange Server e configurare Exchange Server in modo che sia un'applicazione partner per Skype for Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurazione di Skype for Business Server per diventare un'applicazione partner per Exchange Server

Il modo più semplice per configurare Skype for Business Server come applicazione partner con Exchange Server 2016 o Exchange Server 2013 consiste nell'eseguire lo script Configure-EnterprisePartnerApplication. ps1, uno script di Windows PowerShell fornito con Exchange Server. Per eseguire questo script, devi specificare l'URL per il documento di metadati dell'autenticazione di Skype for Business Server. in genere sarà il nome di dominio completo del pool di Skype for Business Server seguito dal suffisso/Metadata/JSON/1. Ad esempio:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Per configurare Skype for Business Server come applicazione partner, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che usi il percorso della cartella predefinito):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) nella cassetta postale di Exchange e nei server Accesso client. È possibile riavviare IIS usando un comando simile a questo, che riavvia il servizio nel computer ATL-Exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando eseguita in privilegi di amministratore.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configurazione di Exchange Server per diventare un'applicazione partner per Skype for Business Server

Dopo aver configurato Skype for Business Server come applicazione partner per Exchange Server 2016 o Exchange Server 2013, è necessario configurare Exchange Server come applicazione partner per Skype for Business Server. Questa operazione può essere eseguita usando Skype for Business Server Management Shell e specificando il documento di metadati di autenticazione per Exchange. si tratta in genere dell'URI del servizio di individuazione automatica di Exchange seguito dal suffisso/Metadata/JSON/1. Ad esempio:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

In Skype for Business Server le applicazioni partner vengono configurate usando il cmdlet [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . Oltre a specificare l'URI di metadati, devi anche impostare il livello di attendibilità dell'applicazione su completo. Ciò consentirà a Exchange di rappresentare se stesso e qualsiasi utente autorizzato nell'ambito. Ad esempio:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

In alternativa, puoi creare un'applicazione partner copiando e modificando il codice di script trovato nella documentazione per l'autenticazione da server a server Skype for Business Server. Per altre informazioni, Vedi l'articolo su come [gestire l'autenticazione server-Server (OAuth) e le applicazioni partner in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) .
  
Se sono state configurate correttamente le applicazioni partner sia per Skype for Business Server che per Exchange Server, è stata configurata anche l'autenticazione da server a server tra i due prodotti. Skype for Business Server include un cmdlet di Windows PowerShell, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) che consente di verificare che l'autenticazione da server a server sia stata configurata correttamente e che il servizio di archiviazione di Skype for Business Server possa connettersi a Exchange Server. Il cmdlet esegue la connessione alla cassetta postale di un utente di Exchange Server, scrivendo un elemento nella cartella Cronologia conversazioni per l'utente e quindi (facoltativamente) eliminando tale elemento.
  
Per testare l'integrazione di Skype for Business Server ed Exchange Server, eseguire un comando simile al seguente da Skype for Business Server Management Shell:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Nel comando precedente, SipUri rappresenta l'indirizzo SIP di un utente con un account su Exchange Server; il comando non riuscirà in questo caso non è un account utente valido.
  
> [!NOTE]
> Se si riceve una risposta di 401 da questo cmdlet, è probabile che la configurazione predefinita di Exchange non includa il supporto per l'accettazione dei token OAuth. Per altre informazioni sull'uso di OAuth in Exchange, vedere [configurare l'autenticazione OAuth con SharePoint 2013 e Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Se il test ha esito positivo e la connettività è stata stabilita, è possibile procedere alla configurazione di funzionalità facoltative, ad esempio l'integrazione di archiviazione e l'archivio contatti unificato.
