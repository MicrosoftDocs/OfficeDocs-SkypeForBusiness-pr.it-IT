---
title: Modificare la configurazione di una distribuzione di Cloud Connector esistente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Seguire i passaggi descritti in questo argomento per modificare la configurazione di un'esistente versione di Skype for Business Cloud Connector 1.4.1 o versione successiva.
ms.openlocfilehash: 7e46d614a5aaf3c34d9401e2ec53ba72e8adba71
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190730"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificare la configurazione di una distribuzione di Cloud Connector esistente
 
Seguire i passaggi descritti in questo argomento per modificare la configurazione di un'esistente versione di Skype for Business Cloud Connector 1.4.1 o versione successiva. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificare la configurazione di un singolo sito
<a name="BKMK_SIngleSite"> </a>

Se nel sito è presente un solo dispositivo, quando si vogliono modificare le impostazioni di configurazione dopo la distribuzione dell'appliance, è possibile modificare il file CloudConnector. ini e riavviare la distribuzione.
  
1. Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nel server host: 
    
   ```
   Uninstall-CcAppliance
   ```

2. Eseguire il cmdlet seguente per annullare la registrazione dell'appliance:
    
   ```
   Unregister-CcAppliance
   ```

3. Aggiornare il file CloudConnector. ini nella directory appliance.
    
4. Eseguire il cmdlet seguente per aggiornare la configurazione: (questo passaggio è applicabile solo alla versione 2, per le versioni precedenti, passare al passaggio successivo).
    
   ```
   Import-CcConfiguration 
   ```

5. Eseguire il cmdlet seguente per registrare di nuovo l'accessorio:
    
   ```
   Register-CcAppliance
   ```

6. Eseguire il cmdlet seguente per installare Skype for Business Cloud Connector Edition:
    
   ```
   Install-CcAppliance
   ```

Se nel sito sono presenti più dispositivi, è necessario seguire questi passaggi, modificare il file CloudConnector. ini e ridistribuire gli elettrodomestici uno alla volta.
  
1. Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nell'appliance corrente: 
    
   ```
   Uninstall-CcAppliance
   ```

2. Eseguire il cmdlet seguente per annullare la registrazione dell'appliance:
    
   ```
   Unregister-CcAppliance
   ```

3. Aggiornare il file CloudConnector. ini nella directory appliance.
    
4. Eseguire il cmdlet seguente per aggiornare la configurazione: (questo passaggio è applicabile solo alla versione 2, per le versioni precedenti, passare al passaggio successivo).
    
   ```
   Import-CcConfiguration 
   ```

5. Eseguire il cmdlet seguente per registrare di nuovo l'accessorio:
    
   ```
   Register-CcAppliance
   ```

6. Eseguire il cmdlet seguente in tutti gli altri dispositivi del sito per raccogliere la configurazione più recente:
    
   ```
   Publish-CcAppliance
   ```

7. Eseguire il cmdlet seguente per ridistribuire Cloud Connector nell'appliance corrente:
    
   ```
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificare la configurazione di più siti
<a name="BKMK_MultipleSites"> </a>

Per modificare la configurazione di più siti in una distribuzione, seguire i passaggi per un singolo sito, aggiornando un sito alla volta.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Modificare la configurazione del tenant di Office 365 per abilitare gli aggiornamenti automatici
<a name="BKMK_MultipleSites"> </a>

Per abilitare gli aggiornamenti automatici del sistema operativo e gli aggiornamenti automatici dei bit, è necessario usare l'account di amministratore del tenant di Skype for business per la gestione online e usare il tenant Remote PowerShell come segue.
  
Se sono stati disabilitati gli aggiornamenti automatici del sistema operativo o i bit, l'host e la macchina virtuale potrebbero non essere più importanti per gli aggiornamenti di Windows e Cloud Connector non verrà aggiornato automaticamente alla nuova versione. Si consiglia vivamente di abilitare gli aggiornamenti automatici.
  
1. La proprietà EnableAutoUpdate del sito deve essere impostata su true (il valore predefinito). Eseguire il cmdlet seguente per verificare che EnableAutoUpdate sia impostato su true:
    
   ```
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Creare la finestra dell'ora di aggiornamento automatico per il tenant.
    
    La finestra temporale può essere giornaliera, settimanale e mensile. Tutte le finestre temporali richiedono un'ora di inizio e una durata.
    
   - Per una finestra dell'ora giornaliera, sono necessari solo l'ora di inizio e la durata. 
    
   - Per un intervallo di tempo settimanale sono necessari i giorni della settimana, che può essere un singolo giorno o più giorni.
    
   - Per un intervallo di tempo mensile, possono essere presenti due tipi. Il primo tipo consiste nel specificare il giorno del mese, che può essere un singolo giorno. Il secondo tipo prevede la specificazione delle settimane del mese, insieme ai giorni della settimana, che possono essere entrambi un singolo elemento o più elementi.
    
   - Ogni tenant può avere finestre di 20 ore definite. Verrà creata la finestra ora predefinita per un nuovo tenant come finestra temporale predefinita per l'aggiornamento dei sistemi operativi e l'aggiornamento dei bit. Eseguire i cmdlet seguenti per impostare la finestra temporale giornaliera, settimanale o mensile:
    
   ```
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Assegnare il tempo di aggiornamento di Windows al sito. 
    
     Le finestre tempo di aggiornamento BITS e ora di aggiornamento del sistema operativo vengono configurate separatamente. A entrambe possono essere assegnate finestre singole o multiple. Ogni finestra temporale può essere assegnata a siti diversi e a uno scopo diverso (aggiornamento BITS e aggiornamento del sistema operativo). Eseguire il cmdlet seguente per impostare la finestra temporale per il sito: 
    
   ```
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aggiornare le credenziali di amministratore del tenant dedicate
<a name="BKMK_MultipleSites"> </a>

Le modifiche amministrative nel tenant di Office 365 per il connettore Cloud vengono effettuate da un account con le autorizzazioni necessarie. Nelle versioni per i connettori cloud prima di 2,0, l'account è un account amministratore globale dedicato del tenant. In Cloud Connector versioni 2,0 e successive l'account può essere un account di Office 365 con i diritti di amministratore di Skype for business.
  
Se le credenziali dell'account di amministratore cambiano in Office 365, è necessario aggiornare anche le credenziali memorizzate nella cache locale in Cloud Connector eseguendo il comando di PowerShell dell'amministratore seguente in ogni appliance del Cloud Connector distribuito:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aggiornare la password per il server host
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Questa sezione è applicabile a Cloud Connector versione 2,0 e successive. 
  
Tutte le credenziali del connettore Cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Quando la password nel server host cambia, sarà necessario aggiornare le credenziali archiviate localmente.
  
Per aggiornare le credenziali archiviate localmente nell'appliance Cloud Connector, usare i cmdlet [Get-CcCredential](get-cccredential.md) e [set-CcCredential](set-cccredential.md) e seguire questa procedura:
  
1. Eseguire i comandi seguenti per recuperare le password necessarie in seguito: 
    
   - Get-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType CceService-DisplayPassword
    
2. Modificare la password dell'account nel server host.
    
3. Riavviare il server host.
    
4. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
5. Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione. Assicurati di immettere la stessa password immessa prima per la distribuzione di Cloud Connector.
    
Per impostazione predefinita, VmAdmin e DomainAdmin usano la stessa password di CceService. Se le password di DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire le operazioni seguenti:
  
1. Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:
    
1. Quando viene richiesto di specificare le credenziali dell'account precedente, immettere le credenziali usate per la password di CceService.
    
2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password di DomainAdmin restituita nel passaggio 1.
    
2. Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:
    
1. Quando viene richiesto di specificare le credenziali dell'account precedente, immettere le credenziali usate per la password di CceService.
    
2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password di VmAdmin restituita nel passaggio 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aggiornare la password per l'account di CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Questa sezione è applicabile a Cloud Connector versione 2.0.1 e successive. 
  
Il servizio Cloud Connector esegue il servizio di gestione dei Cloud Connector. L'account CceService viene creato durante la distribuzione di Cloud Connector Edition e archiviato nei file seguenti: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "e"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".
  
Per assicurarsi che tutti gli elettrodomestici possano accedere alla condivisione della directory del sito, la password per l'account CceService deve essere uguale per tutti gli elettrodomestici distribuiti nel sito. Tieni presente quanto segue:
  
- Per impostazione predefinita, l'account CceService è configurato come "password non scade mai". Quando si aggiorna la password, Microsoft consiglia di mantenere questa configurazione.
    
- È consigliabile aggiornare la password durante i periodi di utilizzo non di punta e all'esterno delle finestre di aggiornamento automatico per bits o aggiornamenti di Windows. Quando si aggiorna la password, l'accessorio deve essere svuotato e riavviato, che richiede del tempo. Il riavvio dell'appliance interrompe le operazioni di aggiornamento automatico. 
    
- Quando si modifica la password dell'account di CceService, sarà necessario specificare tutte le credenziali e aggiornarle nel file archiviato localmente. 
    
Per ogni appliance che appartiene allo stesso sito PSTN, sarà necessario specificare quanto segue: 
  
1. Eseguire i comandi seguenti per recuperare i nomi e le password degli account che verranno usati in seguito:
    
   ```
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. Eseguire il cmdlet Enter-CcUpdate per svuotare l'appliance e spostarla in modalità di manutenzione manuale.
    
3. Aggiornare la password dell'account CceService nel server host.
    
4. Riavviare il server host.
    
5. Eseguire il cmdlet Restore-CcCredentials per immettere di nuovo le password dopo la descrizione. 
    
    Assicurati di immettere la stessa password immessa prima per la distribuzione di Cloud Connector eccetto per l'account CceService. Per l'account CceService, immettere la nuova password. Assicurarsi che la nuova password per l'account CceService sia uguale per tutti gli elettrodomestici nel sito PSTN.
    
6. Per impostazione predefinita, VmAdmin e DomainAdmin usano la stessa password di CceService. Se le password di DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire le operazioni seguenti:
    
7. Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:
    
   - Quando viene richiesto di specificare le credenziali dell'account precedente, immettere le credenziali usate per la password di CceService.
    
   - Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password di DomainAdmin restituita nel passaggio 1.
    
8. Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:
    
   - Quando viene richiesto di specificare le credenziali dell'account precedente, immettere le credenziali usate per la password di CceService.
    
   - Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password di VmAdmin restituita nel passaggio 1. 
    
9. Eseguire il cmdlet Exit-CcUpdate per rimuovere l'apparecchio dalla modalità di manutenzione manuale.
    
10. Dopo aver completato questi passaggi in tutti gli elettrodomestici nello stesso sito PSTN, eliminare i file seguenti nella directory radice del sito:
    
    - CcLockFile
    
    - FQDN\<del pool di SIP esterno di Site_ Edge\>
    
    - FQDN\<del pool di SIP esterno di Tenant_ Edge\>
    
    - FQDN\<del pool di SIP esterno di TenantConfigLock_ Edge\>
    
## <a name="add-a-new-sip-domain"></a>Aggiungere un nuovo dominio SIP
<a name="BKMK_UpdatePassword"> </a>

Per aggiungere un nuovo dominio SIP (o più domini SIP) alla distribuzione di Cloud Connector esistente, eseguire le operazioni seguenti:
  
1. Verificare di aver completato i passaggi per aggiornare il dominio in Office 365 e avere la possibilità di aggiungere record DNS. Per altre informazioni su come configurare il dominio in Office 365, vedere [aggiungere un dominio a office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aggiornare il file di configurazione del Cloud Connector con il nuovo dominio o domini SIP.
    
3. Richiedere un nuovo certificato esterno di Edge con i nomi SAN aggiuntivi per SIP. Domain per ogni dominio SIP definito nella configurazione del connettore Cloud. 
    
4. Impostare il percorso del nuovo certificato esterno di Edge come indicato di seguito:
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Seguire le istruzioni per [modificare la configurazione di un singolo sito](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [modificare la configurazione di più siti](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificare il dominio SIP principale
<a name="BKMK_UpdatePassword"> </a>

Se è necessario modificare il dominio SIP principale nella distribuzione di Cloud Connector, eseguire le operazioni seguenti:
  
1. Verificare di aver completato i passaggi per aggiornare il dominio in Office 365 e avere la possibilità di aggiungere record DNS. Per altre informazioni su come configurare il dominio in Office 365, vedere [aggiungere un dominio a office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aggiornare il file di configurazione del Cloud Connector con il nuovo dominio SIP.
    
3. Richiedere un nuovo certificato esterno di Edge con i nomi SAN aggiuntivi per SIP. Domain per ogni dominio SIP definito nella configurazione del connettore Cloud. 
    
4. Impostare il percorso del nuovo certificato esterno di Edge come indicato di seguito:
    
   ```
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Rimuovere la registrazione del tenant per ogni appliance di un sito eseguendo il cmdlet seguente in PowerShell per l'amministratore su cloud Connector:
    
   ```
   Unregister-CcAppliance
   ```

6. 
    
    Rimuovere la registrazione del sito per ogni sito eseguendo il cmdlet seguente in Skype for Business Online PowerShell:
    
   ```
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Disinstallare ogni appliance eseguendo il cmdlet seguente in PowerShell per l'amministratore su cloud Connector:
    
   ```
   Uninstall-CcAppliance
   ```

8. 
    
     Registrare ogni appliance eseguendo il cmdlet seguente in PowerShell per l'amministratore su cloud Connector:
    
   ```
   Register-ccAppliance
   ```

9. 
    
     Installare ogni appliance, uno alla volta, eseguendo il cmdlet seguente in PowerShell per l'amministratore su cloud Connector:
    
   ```
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Sostituire il certificato perimetrale esterno con un nuovo certificato
<a name="BKMK_UpdatePassword"> </a>

Quando è necessario sostituire il certificato perimetrale esterno negli apparecchi di connessione cloud, è necessario ottenere un nuovo certificato Edge, preparare il file PFX contenente la chiave privata e la catena di certificati completi e quindi eseguire le operazioni seguenti in ogni appliance:
  
1. Inserire l'appliance in modalità di manutenzione usando il cmdlet Enter-CcUpdate.
    
2. Eseguire il comando seguente: 
    
   ```
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Se la password del nuovo certificato è uguale alla vecchia, l'importazione avrà esito positivo. Se la password è diversa, verrà visualizzato un messaggio di errore che indica che la password è errata e sarà necessario reimpostare la password eseguendo il cmdlet Register-CcAppliance con il parametro-local e ripetendo il passaggio 2. 
    
4. Estrarre l'apparecchio dalla modalità di manutenzione usando il cmdlet Exit-CcUpdate.
    

