---
title: Configurare i criteri di bootstrap del client
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Riepilogo: come gestire Criteri di gruppo.'
ms.openlocfilehash: 073bd23219b3fa0a39ed06a94a5ef0586a740e6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831650"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurare i criteri di bootstrap del client
 
**Riepilogo:** Come gestire Criteri di gruppo.
  
La Console Gestione Criteri di gruppo e l'Editor oggetti Criteri di gruppo sono strumenti utilizzati per gestire Criteri di gruppo. I modelli amministrativi di Criteri di gruppo di Office sono lync16.admx (ADMX) e .adml (ADML), che contengono le impostazioni dei criteri basate sul Registro di sistema per Skype for Business configurate per gli oggetti Criteri di gruppo nel dominio. I file ADML sono complementi specifici della lingua ai file ADMX. Ogni file ADMX e ADML contiene le impostazioni dei criteri per una singola Office applicazione. È possibile scaricare gratuitamente i Office modelli amministrativi [2016 (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) dall'Area download Microsoft.
  
Per Skype for Business client, è consigliabile configurare diversi criteri di avvio automatico dei client prima che gli utenti abilitino il server per la prima volta. Ad esempio, i server predefiniti e la modalità di sicurezza che il client deve utilizzare fino al completamento dell'accesso. Puoi usare Criteri di gruppo per stabilire queste impostazioni nei registri dei computer degli utenti prima di accedere e iniziare a ricevere le impostazioni di provisioning in-band dal server. Nella tabella seguente sono elencate le impostazioni di Criteri di gruppo disponibili per Skype for Business.
  
**Criteri di gruppo Impostazioni per Skype for Business**

|Impostazione dei criteri di gruppo|Descrizione|
|:-----|:-----|
|Specifica server (ConfigurationMode)  <br/> | Specifica la modalità Skype for Business il trasporto e il server da utilizzare durante l'accesso. All'interno di questa impostazione è necessario specificare quanto segue: <br/>  ServerAddressExternal: specifica il nome del server o l'indirizzo IP utilizzato dai client e dai contatti federati per la connessione dall'esterno del firewall esterno. <br/>  ServerAddressInternal: specifica il nome del server o l'indirizzo IP utilizzato quando i client si connettono dall'interno del firewall dell'organizzazione. <br/>  Trasporto: specifica TCP (Transmission Control Protocol) o TLS (Transport Layer Security). <br/> |
|Versioni server aggiuntive supportate (ConfiguredServerCheckValues)  <br/> |Specifica un elenco di nomi di versione del server separati da punti e virgola a cui Skype for Business Server accederà, oltre alle versioni server supportate per impostazione predefinita.  <br/> |
|Disabilitare il caricamento automatico dei registri degli errori di accesso (DisableAutomaticSendTracing)  <br/> |Carica automaticamente i log degli errori di accesso Skype for Business Server per l'analisi. Se l'accesso ha esito positivo, non viene caricato automaticamente alcun log. Se questo criterio non è configurato, si verifica quanto segue:  <br/> Per Skype for Business utenti online: i log degli errori di accesso vengono caricati automaticamente. Per Skype for Business utenti locali: prima del caricamento viene visualizzata una finestra di dialogo di conferma. Quando questa impostazione è disabilitata, i log di accesso vengono caricati automaticamente nel Skype for Business Server per gli utenti Skype for Business locali e Skype for Business online. Quando questa impostazione è abilitata, i log di accesso non vengono mai caricati automaticamente.  <br/> |
|Disabilitare il fallback HTTP per la connessione SIP (DisableHttpConnect)  <br/> |Impedisce Skype for Business Server di connettersi al server tramite HTTP, se TLS o TCP non sono disponibili. Per impostazione predefinita, Skype for Business tenta innanzitutto di connettersi al server utilizzando TLS o TCP e, se nessuno di questi metodi di trasporto ha esito positivo, Skype for Business tenta di connettersi utilizzando HTTP. Utilizzare questi criteri per disabilitare il tentativo di connessione HTTP di fallback.  <br/> |
|Richiedi credenziali di accesso (DisableNTCredentials)  <br/> |Richiede all'utente di fornire le credenziali di accesso per Skype for Business anziché utilizzare automaticamente Windows credenziali durante l'accesso a un server SIP.  <br/> |
|Disabilitare il controllo della versione del server (DisableServerCheck)  <br/> |Se si imposta questo criterio su 1, impedisce Skype for Business il nome del server e la versione prima di eseguire l'accesso. Per impostazione predefinita, Skype for Business questi controlli prima dell'accesso.  <br/> |
|Abilitare l'utilizzo di BITS per scaricare i file del servizio Rubrica (EnableBitsForGalDownload)  <br/> |Consente Skype for Business l'utilizzo di BitS (Background Intelligent Transfer Service) per scaricare i file dei servizi rubrica.  <br/> |
|Configurare la modalità di sicurezza SIP (EnableSIPHighSecurityMode)  <br/> |Consente Skype for Business inviare e ricevere messaggi istantanei in modo più sicuro. Tale criterio non produce alcun effetto sui servizi di Windows .NET o Microsoft Exchange Server.  <br/> Se non si configura questa impostazione di criteri, Skype for Business possibile utilizzare qualsiasi trasporto. Tuttavia, se non utilizza TLS e se il server autentica gli utenti, Skype for Business deve utilizzare l'autenticazione NTLM o Kerberos.  <br/> |
|Ritardo iniziale download rubrica globale (GalDownloadInitialDelay)  <br/> |Specifica il periodo di tempo che deve trascorrere prima che si verifichi un download dell'elenco indirizzi globale. Il valore predefinito è 60 minuti, ovvero il server ritarda il download del file dell'elenco indirizzi globale per un periodo casuale compreso tra 0 e 60 minuti.  <br/> |
|Impedire agli utenti di eseguire Skype for Business (PreventRun)  <br/> |Impedisce agli utenti di eseguire Skype for Business. È possibile configurare questa impostazione di criterio sia in Configurazione computer che in Configurazione utente, ma l'impostazione in Configurazione computer ha la precedenza.  <br/> |
|Consentire l'archiviazione delle password utente (SavePassword)  <br/> |Consente Skype for Business di archiviare le password.  <br/> |
|Configurare la modalità di compressione SIP (SipCompression)  <br/> |Specifica quando attivare la compressione SIP. Per impostazione predefinita, la compressione SIP è abilitata in base alla velocità della scheda. Tenere presente che l'impostazione di questo criterio potrebbe comportare un aumento del tempo di accesso.  <br/> |
|Elenco domini attendibili (TrustModelData)  <br/> |Elenca i domini trusted che non corrispondono al prefisso del dominio SIP del cliente.  <br/> |
   
I criteri configurati nel server hanno la priorità sulle impostazioni di Criteri di gruppo e sulle opzioni client configurate dall'utente. Nella tabella riportata di seguito viene riepilogato l'ordine di priorità delle impostazioni in caso di conflitto.
  
**Priorità di Criteri di gruppo**

|**Precedenza**|**Percorso o metodo di impostazione**|
|:-----|:-----|
|1  <br/> |Skype for Business Server provisioning in banda  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |Finestra di dialogo Opzioni Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Per definire le impostazioni di Criteri di gruppo utilizzando i Skype for Business dei modelli amministrativi

1. Crea una cartella a livello radice per contenere tutti i file ADMX indipendenti dalla lingua. Ad esempio, creare la cartella radice per l'archivio centrale nel controller di dominio in questa posizione:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Questa procedura presuppone che si desideri gestire più computer nel dominio. In questo caso, i modelli vengono archiviati in un archivio centrale nella cartella Sysvol nel controller di dominio primario. In questo modo viene fornita una posizione di archiviazione centrale replicata per i modelli amministrativi di dominio. 
  
2. Creare una sottocartella per ogni lingua che verrà utilizzata. Queste sottocartelle conterranno i file di risorse ADML specifici della lingua. Ad esempio, creare una sottocartella per l'inglese (EN-US) degli Stati Uniti in questa posizione:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

