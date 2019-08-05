---
title: Configurare i criteri di avvio del client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Riepilogo: come gestire i criteri di gruppo.'
ms.openlocfilehash: 29e60ea772348ed5f483669cc1d17f8c13e96a02
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190475"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurare i criteri di avvio del client
 
**Riepilogo:** Come gestire i criteri di gruppo.
  
La console Gestione criteri di gruppo e l'Editor oggetti Criteri di gruppo sono strumenti usati per gestire i criteri di gruppo. Il modello amministrativo di criteri di gruppo di Office include lync16. ADMX (ADMX) e ADML (ADML), che contengono le impostazioni dei criteri basate sul Registro di sistema per Skype for business configurate per gli oggetti Criteri di gruppo nel dominio. I file ADML sono complementi specifici della lingua per i file ADMX. Ogni file ADMX e ADML contiene le impostazioni dei criteri per una singola applicazione di Office. È possibile [scaricare i file dei modelli amministrativi di Office 2016 (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) gratuitamente dall'area download Microsoft.
  
Per i client Skype for business, è necessario prevedere diversi criteri di avvio del client che è consigliabile configurare prima che gli utenti accedino al server per la prima volta. Ad esempio, i server e la modalità di sicurezza predefiniti che il client deve usare fino al completamento dell'accesso. È possibile usare criteri di gruppo per stabilire queste impostazioni nei registri computer degli utenti prima di accedere e iniziare a ricevere le impostazioni di provisioning in banda dal server. La tabella seguente elenca le impostazioni dei criteri di gruppo disponibili per Skype for business.
  
**Impostazioni di criteri di gruppo per Skype for business**

|Impostazione di criteri di gruppo|Descrizione|
|:-----|:-----|
|Specifica server (ConfigurationMode)  <br/> | Specifica in che modo Skype for business identifica il trasporto e il server da usare durante l'accesso. In questa impostazione è necessario specificare quanto segue: <br/>  ServerAddressExternal: specifica il nome del server o l'indirizzo IP usato dai client e dai contatti federati quando ci si connette dall'esterno del firewall esterno. <br/>  ServerAddressInternal: specifica il nome del server o l'indirizzo IP usato quando i client si connettono dall'interno del firewall dell'organizzazione. <br/>  Transport: specifica TCP (Transmission Control Protocol) o Transport Layer Security (TLS). <br/> |
|Versioni del server aggiuntive supportate (ConfiguredServerCheckValues)  <br/> |Specifica un elenco di nomi di versione del server separati da punti e virgole a cui si accederà Skype for Business Server, oltre alle versioni del server supportate per impostazione predefinita.  <br/> |
|Disabilitare il caricamento automatico dei log di errore di accesso (DisableAutomaticSendTracing)  <br/> |Carica automaticamente i registri di errore di accesso a Skype for Business Server per l'analisi. Nessun log viene caricato automaticamente se l'accesso è riuscito. Se questo criterio non è configurato, si verifica quanto segue:  <br/> Per gli utenti di Skype for business online: i log di errore di accesso vengono caricati automaticamente. Per gli utenti di Skype for business locale: la finestra di dialogo di conferma viene visualizzata all'utente prima del caricamento. Quando questa impostazione è disabilitata, i log di accesso vengono caricati automaticamente in Skype for Business Server per gli utenti di Skype for business locale e Skype for business online. Quando questa impostazione è abilitata, i log di accesso non vengono mai caricati automaticamente.  <br/> |
|Disabilitare il fallback HTTP per la connessione SIP (DisableHttpConnect)  <br/> |Impedisce a Skype for Business Server di provare a connettersi al server tramite HTTP, se TLS o TCP non sono disponibili. Per impostazione predefinita, Skype for business tenta innanzitutto di connettersi al server tramite TLS o TCP e, se nessuno di questi metodi di trasporto riesce, Skype for business prova a connettersi tramite HTTP. Usare questo criterio per disabilitare il tentativo di connessione HTTP di fallback.  <br/> |
|Richiedi credenziali di accesso (DisableNTCredentials)  <br/> |Richiede all'utente di specificare le credenziali di accesso per Skype for business invece di usare automaticamente le credenziali di Windows durante l'accesso a un server SIP.  <br/> |
|Disabilitare il controllo della versione del server (DisableServerCheck)  <br/> |Se si imposta questo criterio su 1, Skype for business non controlla il nome del server e la versione prima di eseguire l'accesso. Per impostazione predefinita, Skype for business effettua questi controlli prima di eseguire l'accesso.  <br/> |
|Abilitare l'uso di bit per scaricare i file del servizio Rubrica (EnableBitsForGalDownload)  <br/> |Consente a Skype for business di usare il servizio di trasferimento intelligente in background (BITS) per scaricare i file dei servizi Rubrica.  <br/> |
|Configurare la modalità di sicurezza SIP (EnableSIPHighSecurityMode)  <br/> |Consente a Skype for business di inviare e ricevere messaggi istantanei in modo più sicuro. Questo criterio non ha alcun effetto sui servizi Windows .NET o Microsoft Exchange Server.  <br/> Se non si configura questa impostazione, Skype for business può usare qualsiasi trasporto. Ma se non usa TLS e se il server autentica gli utenti, Skype for business deve usare l'autenticazione NTLM o Kerberos.  <br/> |
|Scarica ritardo iniziale della Rubrica globale (GalDownloadInitialDelay)  <br/> |Specifica il periodo di tempo prima che si verifichi il download dell'elenco indirizzi globale (GAL). Il valore predefinito è 60 minuti, quindi il server ritarda il download del file GAL per un periodo casuale compreso tra 0 e 60 minuti.  <br/> |
|Impedire agli utenti di eseguire Skype for business (PreventRun)  <br/> |Impedisce agli utenti di eseguire Skype for business. È possibile configurare questa impostazione per i criteri in configurazione computer e configurazione utente, ma l'impostazione dei criteri in configurazione computer ha la precedenza.  <br/> |
|Consentire l'archiviazione delle password utente (SavePassword)  <br/> |Consente a Skype for business di archiviare le password.  <br/> |
|Configurare la modalità di compressione SIP (SipCompression)  <br/> |Specifica quando attivare la compressione SIP. Per impostazione predefinita, la compressione SIP è abilitata in base alla velocità della scheda. Tieni presente che l'impostazione di questo criterio può causare un aumento dell'ora di accesso.  <br/> |
|Elenco domini attendibili (TrustModelData)  <br/> |Elenca i domini attendibili che non corrispondono al prefisso del dominio SIP del cliente.  <br/> |
   
I criteri configurati nel server hanno la precedenza sulle impostazioni dei criteri di gruppo e le opzioni client configurate dall'utente. Nella tabella seguente viene riepilogato l'ordine in cui le impostazioni hanno la precedenza quando si verifica un conflitto.
  
**Precedenza dei criteri di gruppo**

|**Precedenza**|**Posizione o metodo di impostazione**|
|:-----|:-----|
|1  <br/> |Provisioning in banda in Skype for Business Server  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Finestra di dialogo Opzioni in Skype for business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Per definire le impostazioni dei criteri di gruppo usando i file del modello amministrativo Skype for business

1. Creare una cartella a livello radice per contenere tutti i file ADMX indipendenti dalla lingua. Ad esempio, crea la cartella radice per l'archivio centrale nel controller di dominio in questa posizione:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > In questa procedura si presuppone che si vogliano gestire più computer nel dominio. In questo caso, i modelli vengono archiviati in un archivio centrale nella cartella SYSVOL del controller di dominio primario. In questo modo viene fornito un percorso di archiviazione centralizzato replicato per i modelli amministrativi del dominio. 
  
2. Creare una sottocartella per ogni lingua che verrà usata. Queste sottocartelle conterranno i file di risorse ADML specifici della lingua. Ad esempio, creare una sottocartella per gli Stati Uniti in inglese (EN-US) in questa posizione:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

