---
title: Configurare le applicazioni partner in Skype for Business Server 2015 e Exchange Server
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: "Riepilogo: configurare l'autenticazione da server a server per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server."
ms.openlocfilehash: a707836a43965f477dc037f71bb68cbda8c8e96c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834046"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurare le applicazioni partner in Skype for Business Server e Exchange Server
 
**Riepilogo:** Configurare l'autenticazione da server a server Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.
  
L'autenticazione da server a server in genere richiede due server che devono comunicare tra loro e un server token di sicurezza di terze parti. Se il server A e il server B devono comunicare, entrambi i server in genere iniziano contattando un server di token e ottenendo un token di sicurezza reciprocamente attendibile. Il server A presenta quindi tale token di sicurezza al Server B (e viceversa) come un modo per garantirne l'autenticità e l'affidabilità.
  
Tuttavia, si tratta di una regola generale. Skype for Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013 non devono usare un server di token di terze parti per comunicare tra loro; questo perché questi prodotti server possono creare token di sicurezza che possono essere accettati l'uno dall'altro senza la necessità di un server di token separato. Questa funzionalità è disponibile solo in Skype for Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013. Se è necessario configurare l'autenticazione da server a server con altri server, inclusi altri prodotti server Microsoft, sarà necessario farlo utilizzando un server di token di terze parti.
  
Per configurare l'autenticazione da server a server tra Skype for Business Server e Exchange Server devi eseguire due operazioni: 1) devi assegnare i certificati appropriati a ogni server; e, 2) è necessario configurare ogni server come applicazione partner dell'altro server: ciò significa che è necessario configurare Skype for Business Server come applicazione partner per Exchange Server e configurare Exchange Server come applicazione partner per Skype for Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurazione di Skype for Business Server come applicazione partner per Exchange Server

Il modo più semplice per configurare Skype for Business Server come applicazione partner con Exchange Server 2016 o Exchange Server 2013 è eseguire lo script Configure-EnterprisePartnerApplication.ps1, uno script Windows PowerShell fornito con Exchange Server. Per eseguire questo script, è necessario fornire l'URL per il documento dei metadati di autenticazione di Skype for Business Server; Questo sarà in genere il nome di dominio completo del pool di Skype for Business Server seguito dal suffisso /metadata/json/1. Ad esempio:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Per configurare Skype for Business Server come applicazione partner, aprire Exchange Management Shell ed eseguire un comando simile al seguente (presupponendo che Exchange sia stato installato nell'unità C: e che utilizzi il percorso di cartella predefinito):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) sui server Cassette postali e Accesso client di Exchange. Per riavviare IIS è possibile utilizzare un comando simile al seguente, che riavvia il servizio sul computer atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Questo comando può essere eseguito da Exchange Management Shell o da qualsiasi altra finestra di comando eseguita con privilegi di amministratore.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configurazione di Exchange Server essere un'applicazione partner per Skype for Business Server

Dopo aver configurato Skype for Business Server come applicazione partner per Exchange Server 2016 o Exchange Server 2013, è necessario configurare Exchange Server come applicazione partner per Skype for Business Server. Questa operazione può essere eseguita utilizzando Skype for Business Server Management Shell e specificando il documento dei metadati di autenticazione per Exchange; In genere si tratta dell'URI del servizio di individuazione automatica di Exchange seguito dal suffisso /metadata/json/1. Ad esempio:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

In Skype for Business Server, le applicazioni partner vengono configurate utilizzando il cmdlet [New-CsPartnerApplication.](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Oltre a specificare l'URI dei metadati, devi anche impostare il livello di attendibilità dell'applicazione su Completo; Ciò consentirà a Exchange di rappresentare sia se stesso che qualsiasi utente autorizzato nell'area di autenticazione. Ad esempio:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

In alternativa, è possibile creare un'applicazione partner copiando e modificando il codice di script disponibile nella documentazione relativa all'autenticazione da server a server di Skype for Business Server. Per ulteriori informazioni, vedere l'articolo gestire l'autenticazione da server a [server (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) e le applicazioni partner in Skype for Business Server.
  
Se le applicazioni partner sono state configurate correttamente sia per Skype for Business Server che per Exchange Server, è stata configurata anche l'autenticazione da server a server tra i due prodotti. Skype for Business Server include un cmdlet di Windows PowerShell, [Test-CsExStorageConnectivity,](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) che consente di verificare che l'autenticazione da server a server sia stata configurata correttamente e che il servizio di archiviazione di Skype for Business Server possa connettersi a Exchange Server. Il cmdlet esegue questa operazione connettendosi alla cassetta postale di un utente Exchange Server, scrivendo un elemento nella cartella Cronologia conversazioni per tale utente e quindi (facoltativamente) eliminando tale elemento.
  
Per testare l'integrazione di Skype for Business Server e Exchange Server, eseguire un comando simile al seguente da Skype for Business Server Management Shell:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

Nel comando precedente SipUri rappresenta l'indirizzo SIP di un utente con un account in Exchange Server; il comando avrà esito negativo in questo caso non è un account utente valido.
  
> [!NOTE]
> Se si riceve una risposta 401 da questo cmdlet, è probabile che la configurazione predefinita di Exchange non includa il supporto per l'accettazione di token Oauth. Per ulteriori informazioni sull'utilizzo di Oauth in Exchange, vedere Configurare l'autenticazione OAuth con [SharePoint 2013 e Skype for Business Server.](https://go.microsoft.com/fwlink/p/?LinkId=513103) 
  
Se il test ha esito positivo e la connettività è stata stabilita, è possibile procedere alla configurazione di funzionalità facoltative come l'integrazione dell'archiviazione e l'archivio contatti unificato.
