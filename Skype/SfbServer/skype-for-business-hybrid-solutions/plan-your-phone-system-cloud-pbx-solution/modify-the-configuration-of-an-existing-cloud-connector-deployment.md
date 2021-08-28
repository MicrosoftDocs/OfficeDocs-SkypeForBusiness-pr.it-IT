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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Seguire i passaggi descritti in questo argomento per modificare la configurazione di una distribuzione Skype for Business Cloud Connector Edition 1.4.1 o successiva.
ms.openlocfilehash: 5d0771e1f6a62015cf040a899c88696016366e47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590010"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificare la configurazione di una distribuzione di Cloud Connector esistente

> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Seguire i passaggi descritti in questo argomento per modificare la configurazione di una distribuzione Skype for Business Cloud Connector Edition 1.4.1 o successiva. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificare la configurazione di un singolo sito
<a name="BKMK_SIngleSite"> </a>

Se nel sito è presente un solo dispositivo, quando si desidera modificare le impostazioni di configurazione dopo la distribuzione dell'appliance, è possibile modificare il file CloudConnector.ini e avviare di nuovo la distribuzione.
  
1. Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nel server host: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Eseguire il cmdlet seguente per annullare la registrazione dell'appliance:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aggiornare il CloudConnector.ini file nella directory appliance.
    
4. Eseguire il cmdlet seguente per aggiornare la configurazione: Questo passaggio è applicabile solo alla versione 2. Per le versioni precedenti, passare al passaggio successivo.
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Eseguire il cmdlet seguente per registrare di nuovo l'appliance:
    
   ```powershell
   Register-CcAppliance
   ```

6. Eseguire il cmdlet seguente per installare Skype for Business Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Se nel sito sono presenti più appliance, è necessario eseguire la procedura seguente, modificare il file CloudConnector.ini e ridistribuire le appliance una alla volta.
  
1. Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nell'appliance corrente: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Eseguire il cmdlet seguente per annullare la registrazione dell'appliance:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aggiornare il CloudConnector.ini file nella directory appliance.
    
4. Eseguire il cmdlet seguente per aggiornare la configurazione: Questo passaggio è applicabile solo alla versione 2. Per le versioni precedenti, passare al passaggio successivo.
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Eseguire il cmdlet seguente per registrare di nuovo l'appliance:
    
   ```powershell
   Register-CcAppliance
   ```

6. Eseguire il cmdlet seguente in tutte le altre appliance del sito per recuperare la configurazione più recente:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Eseguire il cmdlet seguente per ridistribuire Cloud Connector nell'appliance corrente:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificare la configurazione di più siti
<a name="BKMK_MultipleSites"> </a>

Per modificare la configurazione per più siti in una distribuzione, seguire i passaggi per un singolo sito, aggiornando un sito alla volta.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Modificare la configurazione dell'organizzazione Microsoft 365 o Office 365 per abilitare gli aggiornamenti automatici
<a name="BKMK_MultipleSites"> </a>

Per abilitare gli aggiornamenti automatici del sistema operativo e gli aggiornamenti automatici bit, è necessario utilizzare l'account di amministratore tenant di Skype for Business per la gestione online e usare PowerShell remoto tenant come indicato di seguito.
  
Se sono stati disabilitati gli aggiornamenti automatici del sistema operativo o gli aggiornamenti automatici di Bits, l'host e la macchina virtuale potrebbero perdere aggiornamenti importanti Windows e Cloud Connector non verrà aggiornato automaticamente alla nuova versione. È consigliabile abilitare gli aggiornamenti automatici.
  
1. La proprietà EnableAutoUpdate del sito deve essere impostata su true (valore predefinito). Eseguire il cmdlet seguente per assicurarsi che EnableAutoUpdate sia impostato su true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Creare un intervallo di tempo di aggiornamento automatico per il tenant.
    
    L'intervallo di tempo può essere giornaliero, settimanale e mensile. Tutte le finestre di tempo necessitano di un'ora di inizio e di una durata.
    
   - Per un intervallo di tempo giornaliero, sono necessarie solo l'ora di inizio e la durata. 
    
   - Per un intervallo di tempo settimanale, sono necessari giorni della settimana, che possono essere un solo giorno o più giorni.
    
   - Per un intervallo di tempo mensile, possono essere disponibili due tipi. Il primo tipo è specificare il giorno del mese, che può essere un singolo giorno. Il secondo tipo è quello di specificare le settimane del mese, insieme ai giorni della settimana, che possono essere entrambi un singolo elemento o più elementi.
    
   - Ogni tenant può avere 20 finestre di tempo definite. L'intervallo di tempo predefinito verrà creato per un nuovo tenant come intervallo di tempo predefinito per l'aggiornamento del sistema operativo e l'aggiornamento dei bit. Eseguire i cmdlet seguenti per impostare l'intervallo di tempo giornaliero, settimanale o mensile:
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Assegnare le finestre dell'ora di aggiornamento al sito. 
    
     Le finestre Ora aggiornamento bit e Ora aggiornamento sistema operativo sono configurate separatamente. A entrambi è possibile assegnare finestre singole o multiple. Ogni intervallo di tempo può essere assegnato a siti diversi e a scopi diversi (aggiornamento dei bit e aggiornamento del sistema operativo). Eseguire il cmdlet seguente per impostare l'intervallo di tempo per il sito: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aggiornare le credenziali di amministratore tenant dedicato
<a name="BKMK_MultipleSites"> </a>

Le modifiche amministrative nell'Microsoft 365 o Office 365 per Cloud Connector vengono apportate da un account con le autorizzazioni necessarie. Nelle versioni di Cloud Connector precedenti alla 2.0, tale account è un account amministratore tenant globale dedicato. In Cloud Connector versioni 2.0 e successive, tale account può essere un account Microsoft 365 o Office 365 con diritti Skype for Business amministratore.
  
Se le credenziali dell'account amministratore cambiano in Microsoft 365 o Office 365, è inoltre necessario aggiornare le credenziali memorizzate localmente nella cache in Cloud Connector eseguendo il seguente comando di PowerShell di amministratore in ogni appliance del connettore cloud distribuita:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aggiornare la password per il server host
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Questa sezione è applicabile a Cloud Connector versione 2.0 e successive. 
  
Tutte le credenziali del connettore cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml". Quando la password nel server host cambia, sarà necessario aggiornare le credenziali archiviate localmente.
  
Per aggiornare le credenziali archiviate localmente nell'appliance Cloud Connector, utilizzare i cmdlet [Get-CcCredential](get-cccredential.md) e [Set-CcCredential](set-cccredential.md) ed eseguire la procedura seguente:
  
1. Eseguire i comandi seguenti per recuperare le password necessarie in un secondo momento: 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Modificare la password dell'account nel server host.
    
3. Riavviare il server host.
    
4. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml".
    
5. Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere di nuovo le password dopo la descrizione. Assicurati di immettere la stessa password immessa prima per la distribuzione di Cloud Connector.
    
Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService. Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire la procedura seguente:
  
1. Eseguire Set-CcCredential -AccountType DomainAdmin come segue:
    
1. Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password DomainAdmin restituita nel passaggio 1.
    
2. Eseguire Set-CcCredential -AccountType VmAdmin come segue:
    
1. Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password VmAdmin restituita nel passaggio 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aggiornare la password per l'account CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Questa sezione è applicabile a Cloud Connector versione 2.0.1 e successive. 
  
Il servizio Cloud Connector esegue il servizio di gestione dei connettori cloud. L'account CceService viene creato durante la distribuzione di Cloud Connector Edition e archiviato nei file seguenti: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml" e "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
Per garantire che tutte le appliance possano accedere alla condivisione di directory del sito, la password per l'account CceService deve essere la stessa in tutte le appliance distribuite all'interno del sito. Tenere presente quanto segue:
  
- Per impostazione predefinita, l'account CceService è configurato come "Password never expires". Quando si aggiorna la password, Microsoft consiglia di mantenere questa configurazione.
    
- È consigliabile aggiornare la password durante i periodi di utilizzo non di picco e al di fuori delle finestre di tempo di aggiornamento automatico per bit o Windows aggiornamenti. Quando si aggiorna la password, l'appliance deve essere svuotata e riavviata, il che richiede tempo. Il riavvio dell'appliance interromperà le operazioni di aggiornamento automatico. 
    
- Quando si modifica la password dell'account CceService, sarà necessario specificare tutte le credenziali e aggiornarle nel file archiviato localmente. 
    
Per ogni appliance appartenente allo stesso sito PSTN, è necessario specificare quanto segue: 
  
1. Eseguire i comandi seguenti per recuperare i nomi e le password degli account che verranno utilizzati in seguito:
    
   ```powershell
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

2. Eseguire il cmdlet Enter-CcUpdate per svuotare l'appliance e spostarlo in modalità di manutenzione manuale.
    
3. Aggiornare la password dell'account CceService nel server host.
    
4. Riavviare il server host.
    
5. Eseguire il cmdlet Restore-CcCredentials per immettere di nuovo le password dopo la descrizione. 
    
    Assicurati di immettere la stessa password immessa in precedenza per la distribuzione di Cloud Connector ad eccezione dell'account CceService. Per l'account CceService, immettere la nuova password. Verificare che la nuova password per l'account CceService sia la stessa per tutte le appliance nel sito PSTN.
    
6. Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService. Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire la procedura seguente:
    
7. Eseguire Set-CcCredential -AccountType DomainAdmin come segue:
    
   - Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
   - Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password DomainAdmin restituita nel passaggio 1.
    
8. Eseguire Set-CcCredential -AccountType VmAdmin come segue:
    
   - Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
   - Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password VmAdmin restituita nel passaggio 1. 
    
9. Eseguire il cmdlet Exit-CcUpdate per spostare l'appliance fuori dalla modalità di manutenzione manuale.
    
10. Dopo aver completato questi passaggi in tutte le appliance nello stesso sito PSTN, eliminare i file seguenti nella directory radice del sito:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Aggiungere un nuovo dominio SIP
<a name="BKMK_UpdatePassword"> </a>

Per aggiungere un nuovo dominio SIP (o più domini SIP) alla distribuzione esistente di Cloud Connector, eseguire le operazioni seguenti:
  
1. Assicurarsi di aver completato i passaggi per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS. Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aggiornare il file di configurazione del connettore cloud con il nuovo dominio SIP o i nuovi domini.
    
3. Richiedere un nuovo certificato esterno Edge con nomi SAN aggiuntivi per sip.domain per ogni dominio SIP definito nella configurazione del connettore cloud. 
    
4. Impostare il percorso per il nuovo certificato esterno edge come segue:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Seguire le istruzioni per [Modificare la configurazione di un singolo sito](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o Modificare la configurazione di più [siti.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>Modificare il dominio SIP primario
<a name="BKMK_UpdatePassword"> </a>

Se è necessario modificare il dominio SIP primario nella distribuzione di Cloud Connector, eseguire le operazioni seguenti:
  
1. Assicurarsi di aver completato i passaggi per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS. Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aggiornare il file di configurazione del connettore cloud con il nuovo dominio SIP.
    
3. Richiedere un nuovo certificato esterno Edge con nomi SAN aggiuntivi per sip.domain per ogni dominio SIP definito nella configurazione del connettore cloud. 
    
4. Impostare il percorso per il nuovo certificato esterno edge come segue:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Rimuovere la registrazione tenant per ogni appliance in un sito eseguendo il cmdlet seguente in PowerShell per l'amministratore in Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Rimuovere la registrazione del sito per ogni sito eseguendo il cmdlet seguente in Skype for Business PowerShell online:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Disinstallare ogni appliance eseguendo il cmdlet seguente in PowerShell per l'amministratore nel connettore cloud:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registrare ogni appliance eseguendo il cmdlet seguente in PowerShell per l'amministratore in Cloud Connector:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installare ogni appliance, uno per uno, eseguendo il cmdlet seguente in PowerShell per l'amministratore in Cloud Connector:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Sostituire il certificato edge esterno con un nuovo certificato
<a name="BKMK_UpdatePassword"> </a>

Quando è necessario sostituire il certificato edge esterno nelle appliance Cloud Connector, è necessario ottenere un nuovo certificato Edge, preparare il file PFX contenente la chiave privata e la catena di certificati completa e quindi eseguire le operazioni seguenti in ogni appliance:
  
1. Impostare l'appliance in modalità manutenzione utilizzando il cmdlet Enter-CcUpdate.
    
2. Eseguire il comando seguente: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Se la password del nuovo certificato è uguale a quella precedente, l'importazione avrà esito positivo. Se la password è diversa, verrà visualizzato un errore che indica che la password non è corretta e sarà necessario reimpostarla eseguendo il cmdlet Register-CcAppliance con il parametro -Local e quindi ripetendo il passaggio 2. 
    
4. Rimuovere l'appliance dalla modalità di manutenzione utilizzando il cmdlet Exit -CcUpdate.
