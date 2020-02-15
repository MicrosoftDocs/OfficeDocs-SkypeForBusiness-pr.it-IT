---
title: Configurare i criteri di avvio automatico dei client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Riepilogo: informazioni su come gestire i criteri di gruppo.'
ms.openlocfilehash: 4db9becc32e8f9bca99f06ac4533d33e82666591
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029057"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurare i criteri di avvio automatico dei client
 
**Riepilogo:** Come gestire i criteri di gruppo.
  
La console Gestione criteri di gruppo e l'Editor oggetti Criteri di gruppo sono strumenti che è possibile utilizzare per gestire i criteri di gruppo. Con il modello amministrativo di criteri di gruppo di Office sono inclusi i modelli amministrativi di lync16. ADMX (ADMX) e ADML (ADML), che contengono le impostazioni dei criteri basati sul Registro di sistema per Skype for business che vengono configurate per gli oggetti Criteri di gruppo nel dominio. I file ADML sono complementi specifici della lingua per i file ADMX. Ogni file ADMX e ADML contiene le impostazioni dei criteri per una singola applicazione di Office. È possibile [scaricare i file dei modelli amministrativi di Office 2016 (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) gratuitamente dall'area download Microsoft.
  
Per i client Skype for business, sono disponibili diversi criteri di avvio del client che è consigliabile configurare prima che gli utenti eseguano l'accesso al server per la prima volta. Ad esempio, i server e la modalità di sicurezza predefiniti che il client deve utilizzare fino al completamento dell'accesso. È possibile utilizzare criteri di gruppo per definire queste impostazioni nei registri dei computer degli utenti prima di accedere e iniziare a ricevere le impostazioni di provisioning in banda dal server. Nella tabella seguente sono elencate le impostazioni di criteri di gruppo disponibili per Skype for business.
  
**Impostazioni di criteri di gruppo per Skype for business**

|Impostazione dei criteri di gruppo|Descrizione|
|:-----|:-----|
|Specificare il server (ConfigurationMode)  <br/> | Specifica il modo in cui Skype for business identifica il trasporto e il server da utilizzare durante l'accesso. All'interno di questa impostazione, è necessario specificare quanto segue: <br/>  ServerAddressExternal: specifica il nome o l'indirizzo IP del server utilizzato dai client e dai contatti federati quando si effettua la connessione dall'esterno del firewall esterno. <br/>  ServerAddressInternal: specifica il nome o l'indirizzo IP del server utilizzato quando i client si connettono dall'interno del firewall dell'organizzazione. <br/>  Transport: specifica il protocollo TCP (Transmission Control Protocol) o TLS (Transport Layer Security). <br/> |
|Versioni di server aggiuntive supportate (ConfiguredServerCheckValues)  <br/> |Specifica un elenco di nomi di versioni server separati da punti e virgole su cui si accederà Skype for Business Server, oltre alle versioni server supportate per impostazione predefinita.  <br/> |
|Disabilitare il caricamento automatico dei log degli errori di accesso (DisableAutomaticSendTracing)  <br/> |Carica automaticamente i log degli errori di accesso a Skype for Business Server per l'analisi. Se l'accesso ha esito positivo, non vengono caricati automaticamente i registri. Se questo criterio non è configurato, si verifica quanto segue:  <br/> Per gli utenti di Skype for business online: i log di errore di accesso vengono caricati automaticamente. Per gli utenti di Skype for business in locale: viene visualizzata una finestra di dialogo di conferma per l'utente prima del caricamento. Quando questa impostazione è disabilitata, i log di accesso vengono caricati automaticamente su Skype for Business Server per gli utenti di Skype for business in locale e Skype for business online. Quando questa impostazione è abilitata, i registri di accesso non vengono mai caricati automaticamente.  <br/> |
|Disabilitare il fallback HTTP per la connessione SIP (DisableHttpConnect)  <br/> |Impedisce a Skype for Business Server di tentare la connessione al server tramite HTTP, se TLS o TCP non sono disponibili. Per impostazione predefinita, Skype for business prima tenta di connettersi al server tramite TLS o TCP e, se nessuno di questi metodi di trasporto ha esito positivo, Skype for business tenta di connettersi tramite HTTP. Utilizzare questi criteri per disabilitare il tentativo di connessione HTTP di fallback.  <br/> |
|Richiedi credenziali di accesso (DisableNTCredentials)  <br/> |Richiede all'utente di fornire le credenziali di accesso per Skype for business anziché utilizzare automaticamente le credenziali di Windows durante l'accesso a un server SIP.  <br/> |
|Disabilitare il controllo della versione del server (DisableServerCheck)  <br/> |Se si imposta questo criterio su 1, è prevedibile che Skype for business controlli il nome e la versione del server prima di eseguire l'accesso. Per impostazione predefinita, Skype for business effettua questi controlli prima di effettuare l'accesso.  <br/> |
|Abilitare l'utilizzo di bit per scaricare i file del servizio Rubrica (EnableBitsForGalDownload)  <br/> |Consente a Skype for business di utilizzare BITS (Background Intelligent Transfer Service) per scaricare i file dei servizi della Rubrica.  <br/> |
|Configurare la modalità di protezione SIP (EnableSIPHighSecurityMode)  <br/> |Consente a Skype for business di inviare e ricevere messaggi istantanei in modo più sicuro. Tale criterio non produce alcun effetto sui servizi di Windows .NET o Microsoft Exchange Server.  <br/> Se non si configura questa impostazione dei criteri, Skype for business può utilizzare qualsiasi trasporto. Tuttavia, se non utilizza TLS e se il server esegue l'autenticazione degli utenti, Skype for business deve utilizzare l'autenticazione NTLM o Kerberos.  <br/> |
|Ritardo iniziale del download della Rubrica globale (GalDownloadInitialDelay)  <br/> |Specifica il periodo di tempo che deve trascorrere prima che si verifichi un download dell'elenco indirizzi globale. Il valore predefinito è 60 minuti, il che significa che il server ritarderà il download del file GAL per un periodo casuale compreso tra 0 e 60 minuti.  <br/> |
|Impedire agli utenti di eseguire Skype for business (PreventRun)  <br/> |Impedisce agli utenti di eseguire Skype for business. È possibile configurare questa impostazione di criterio sia in Configurazione computer che in Configurazione utente, ma l'impostazione in Configurazione computer ha la precedenza.  <br/> |
|Consenti archiviazione delle password degli utenti (SavePassword)  <br/> |Consente a Skype for business di archiviare le password.  <br/> |
|Configurare la modalità di compressione SIP (SipCompression)  <br/> |Specifica quando attivare la compressione SIP. Per impostazione predefinita, la compressione SIP è abilitata in base alla velocità della scheda. Tenere presente che l'impostazione di questo criterio potrebbe comportare un aumento del tempo di accesso.  <br/> |
|Elenco di domini attendibili (TrustModelData)  <br/> |Elenca i domini attendibili che non corrispondono al prefisso del dominio SIP del cliente.  <br/> |
   
I criteri configurati nel server hanno la priorità sulle impostazioni di Criteri di gruppo e sulle opzioni client configurate dall'utente. Nella tabella riportata di seguito viene riepilogato l'ordine di priorità delle impostazioni in caso di conflitto.
  
**Priorità di Criteri di gruppo**

|**Precedenza**|**Percorso o metodo di impostazione**|
|:-----|:-----|
|1   <br/> |Provisioning in banda di Skype for Business Server  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |La finestra di dialogo Opzioni in Skype for business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Per definire le impostazioni di criteri di gruppo utilizzando i file del modello amministrativo di Skype for business

1. Creare una cartella di livello radice che contenga tutti i file ADMX indipendenti dalla lingua. Ad esempio, creare la cartella radice per l'archivio centrale nel controller di dominio in questo percorso:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > In questa procedura si presuppone che si desideri gestire più computer nel dominio. In questo caso, i modelli vengono archiviati in un archivio centrale nella cartella SYSVOL del controller di dominio primario. In questo modo viene fornito un percorso di archiviazione centrale replicato per i modelli amministrativi di dominio. 
  
2. Creare una sottocartella per ogni lingua che verrà utilizzata. Tali sottocartelle conterranno i file di risorse ADML specifici per la lingua. Ad esempio, creare una sottocartella per gli Stati Uniti (EN-US) in questa posizione:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

