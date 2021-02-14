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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Seguire i passaggi descritti in questo argomento per modificare la configurazione di una distribuzione esistente di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359112"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificare la configurazione di una distribuzione di Cloud Connector esistente

> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Seguire i passaggi descritti in questo argomento per modificare la configurazione di una distribuzione esistente di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificare la configurazione di un singolo sito
<a name="BKMK_SIngleSite"> </a>

Se nel sito è presente un solo appliance, quando si desidera modificare le impostazioni di configurazione dopo la distribuzione, è possibile modificare il file CloudConnector.ini e avviare di nuovo la distribuzione.
  
1. Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nel server host: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Eseguire il cmdlet seguente per annullare la registrazione dell'appliance:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aggiornare il CloudConnector.ini file nella directory appliance.
    
4. Eseguire il cmdlet seguente per aggiornare la configurazione: questo passaggio è applicabile solo alla versione 2. Per le versioni precedenti, andare al passaggio successivo.
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Eseguire il cmdlet seguente per registrare di nuovo l'applicazione:
    
   ```powershell
   Register-CcAppliance
   ```

6. Eseguire il cmdlet seguente per installare Skype for Business Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Se nel sito sono presenti più appliance, è necessario eseguire questa procedura, modificare il file CloudConnector.ini e ridistribuire le appliance una alla volta.
  
1. Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nell'appliance corrente: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Eseguire il cmdlet seguente per annullare la registrazione dell'appliance:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aggiornare il CloudConnector.ini file nella directory appliance.
    
4. Eseguire il cmdlet seguente per aggiornare la configurazione: questo passaggio è applicabile solo alla versione 2. Per le versioni precedenti, andare al passaggio successivo.
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Eseguire il cmdlet seguente per registrare di nuovo l'applicazione:
    
   ```powershell
   Register-CcAppliance
   ```

6. Eseguire il cmdlet seguente in tutti gli altri appliance del sito per recuperare la configurazione più recente:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Eseguire il cmdlet seguente per ridistribuire Cloud Connector nell'appliance corrente:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificare la configurazione di più siti
<a name="BKMK_MultipleSites"> </a>

Per modificare la configurazione per più siti in una distribuzione, eseguire la procedura per un singolo sito, aggiornando un sito alla volta.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Modificare la configurazione dell'organizzazione di Microsoft 365 o Office 365 per abilitare gli aggiornamenti automatici
<a name="BKMK_MultipleSites"> </a>

Per abilitare gli aggiornamenti automatici del sistema operativo e gli aggiornamenti automatici bit, è necessario utilizzare l'account di amministratore tenant di Skype for Business per la gestione online e usare PowerShell remoto del tenant come indicato di seguito.
  
Se sono stati disabilitati gli aggiornamenti automatici del sistema operativo o gli aggiornamenti automatici di Bits, l'host e la macchina virtuale potrebbero perdere importanti aggiornamenti di Windows e Cloud Connector non verrà aggiornato automaticamente alla nuova versione. È consigliabile abilitare gli aggiornamenti automatici.
  
1. La proprietà EnableAutoUpdate del sito deve essere impostata su true (valore predefinito). Eseguire il cmdlet seguente per assicurarsi che EnableAutoUpdate sia impostato su true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Creare un intervallo di tempo di aggiornamento automatico per il tenant.
    
    L'intervallo di tempo può essere giornaliero, settimanale e mensile. Tutte le finestre di tempo necessitano di un'ora di inizio e di una durata.
    
   - Per un intervallo di tempo giornaliero sono necessari solo l'ora di inizio e la durata. 
    
   - Per un intervallo di tempo settimanale, sono necessari giorni della settimana, che possono essere un solo giorno o più giorni.
    
   - Per un intervallo di tempo mensile, possono essere disponibili due tipi. Il primo tipo è specificare il giorno del mese, che può essere un singolo giorno. Il secondo tipo è quello di specificare le settimane del mese, insieme ai giorni della settimana, che possono essere entrambi un singolo elemento o più elementi.
    
   - Ogni tenant può avere finestre di tempo 20 definite. L'intervallo di tempo predefinito verrà creato per un nuovo tenant come intervallo di tempo predefinito per l'aggiornamento del sistema operativo e l'aggiornamento dei bit. Eseguire i cmdlet seguenti per impostare l'intervallo di tempo giornaliero, settimanale o mensile:
    
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

   - Assegnare finestre di tempo di aggiornamento al sito. 
    
     L'ora di aggiornamento dei bit e le finestre dell'ora di aggiornamento del sistema operativo vengono configurate separatamente. Entrambe possono essere assegnate a finestre singole o multiple. Ogni intervallo di tempo può essere assegnato a siti diversi e a scopi diversi (aggiornamento dei bit e aggiornamento del sistema operativo). Eseguire il cmdlet seguente per impostare l'intervallo di tempo per il sito: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aggiornare le credenziali di amministratore tenant dedicato
<a name="BKMK_MultipleSites"> </a>

Le modifiche amministrative nell'organizzazione di Microsoft 365 o Office 365 per Cloud Connector vengono apportate da un account con le autorizzazioni necessarie. Nelle versioni di Cloud Connector precedenti alla 2.0, tale account è un account di amministratore del tenant globale dedicato. In Cloud Connector versioni 2.0 e successive, tale account può essere un account di Microsoft 365 o Office 365 con diritti di amministratore di Skype for Business.
  
Se le credenziali dell'account amministratore cambiano in Microsoft 365 o Office 365, è necessario aggiornare anche le credenziali memorizzate nella cache locale in Cloud Connector eseguendo il comando di Amministratore di PowerShell seguente in ogni appliance cloud connector distribuita:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aggiornare la password per il server host
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Questa sezione è applicabile a Cloud Connector versione 2.0 e successive. 
  
Tutte le credenziali del connettore cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml". Quando la password nel server host cambia, sarà necessario aggiornare le credenziali archiviate localmente.
  
Per aggiornare le credenziali archiviate localmente nell'applicazione Cloud Connector, utilizzare i cmdlet [Get-CcCredential](get-cccredential.md) e [Set-CcCredential](set-cccredential.md) ed eseguire la procedura seguente:
  
1. Eseguire i comandi seguenti per recuperare le password necessarie in un secondo momento: 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Modificare la password dell'account nel server host.
    
3. Riavviare il server host.
    
4. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".
    
5. Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere nuovamente le password seguendo la descrizione. Assicurarsi di immettere la stessa password immessa prima per la distribuzione di Cloud Connector.
    
Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService. Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire la procedura seguente:
  
1. Eseguire Set-CcCredential -AccountType DomainAdmin come segue:
    
1. Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password DomainAdmin restituita nel passaggio 1.
    
2. Eseguire Set-CcCredential -AccountType VmAdmin come segue:
    
1. Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
2. Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password vmadmin restituita nel passaggio 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aggiornare la password per l'account CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Questa sezione è applicabile a Cloud Connector versione 2.0.1 e successive. 
  
Il servizio Cloud Connector esegue il servizio di gestione del connettore cloud. L'account CceService viene creato durante la distribuzione di Cloud Connector Edition e archiviato nei file seguenti: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" e "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
Per garantire che tutti gli appliance possano accedere alla condivisione della directory del sito, la password per l'account CceService deve essere la stessa in tutte le appliance distribuite all'interno del sito. Tenere presente quanto segue:
  
- Per impostazione predefinita, l'account CceService è configurato come "Nessuna scadenza password". Quando si aggiorna la password, Microsoft consiglia di mantenere questa configurazione.
    
- È consigliabile aggiornare la password durante i periodi di utilizzo non di punta e al di fuori delle finestre di tempo di aggiornamento automatico per bit o aggiornamenti di Windows. Quando si aggiorna la password, l'applicazione deve essere scaricata e riavviata, il che richiede del tempo. Il riavvio dell'applicazione interromperà le operazioni di aggiornamento automatico. 
    
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

2. Eseguire il cmdlet Enter-CcUpdate per svuotare l'applicazione e spostarlo in modalità di manutenzione manuale.
    
3. Aggiornare la password dell'account CceService nel server host.
    
4. Riavviare il server host.
    
5. Eseguire il cmdlet Restore-CcCredentials per immettere nuovamente le password seguendo la descrizione. 
    
    Assicurarsi di immettere la stessa password immessa prima per la distribuzione di Cloud Connector, ad eccezione dell'account CceService. Per l'account CceService, immettere la nuova password. Verificare che la nuova password per l'account CceService sia la stessa per tutte le appliance nel sito PSTN.
    
6. Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService. Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire la procedura seguente:
    
7. Eseguire Set-CcCredential -AccountType DomainAdmin come segue:
    
   - Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
   - Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password DomainAdmin restituita nel passaggio 1.
    
8. Eseguire Set-CcCredential -AccountType VmAdmin come segue:
    
   - Quando viene richiesta la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.
    
   - Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password vmadmin restituita nel passaggio 1. 
    
9. Eseguire il cmdlet Exit-CcUpdate per spostare l'applicazione dalla modalità di manutenzione manuale.
    
10. Dopo aver completato questi passaggi in tutte le appliance nello stesso sito PSTN, eliminare i file seguenti nella directory radice del sito:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Aggiungere un nuovo dominio SIP
<a name="BKMK_UpdatePassword"> </a>

Per aggiungere un nuovo dominio SIP (o più domini SIP) alla distribuzione di Cloud Connector esistente, eseguire le operazioni seguenti:
  
1. Assicurarsi di aver completato i passaggi per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS. Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere Aggiungere un dominio [a Microsoft 365 o Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Aggiornare il file di configurazione del connettore cloud con il nuovo dominio SIP o i nuovi domini.
    
3. Richiedere un nuovo certificato esterno edge con nomi SAN aggiuntivi per sip.domain per ogni dominio SIP definito nella configurazione del connettore cloud. 
    
4. Impostare il percorso per il nuovo certificato esterno edge nel modo seguente:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Seguire le istruzioni per [modificare la configurazione di un singolo sito](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o modificare la configurazione di più [siti.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>Modificare il dominio SIP primario
<a name="BKMK_UpdatePassword"> </a>

Se è necessario modificare il dominio SIP primario nella distribuzione di Cloud Connector, eseguire le operazioni seguenti:
  
1. Assicurarsi di aver completato i passaggi per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS. Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere Aggiungere un dominio [a Microsoft 365 o Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Aggiornare il file di configurazione del connettore cloud con il nuovo dominio SIP.
    
3. Richiedere un nuovo certificato esterno edge con nomi SAN aggiuntivi per sip.domain per ogni dominio SIP definito nella configurazione del connettore cloud. 
    
4. Impostare il percorso per il nuovo certificato esterno edge nel modo seguente:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Rimuovere la registrazione del tenant per ogni applicazione in un sito eseguendo il cmdlet seguente nell'amministratore di PowerShell in Cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Rimuovere la registrazione del sito per ogni sito eseguendo il cmdlet seguente in PowerShell di Skype for Business online:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Disinstallare ogni applicazione eseguendo il cmdlet seguente in PowerShell per l'amministratore in Cloud Connector:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registrare ogni appliance eseguendo il cmdlet seguente in PowerShell per l'amministratore in Cloud Connector:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installare ogni appliance, uno alla volta, eseguendo il cmdlet seguente nell'amministratore di PowerShell in Cloud Connector:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Sostituire il certificato perimetrale esterno con un nuovo certificato
<a name="BKMK_UpdatePassword"> </a>

Quando è necessario sostituire il certificato perimetrale esterno nelle appliance del connettore cloud, è necessario ottenere un nuovo certificato edge, preparare il file PFX contenente la chiave privata e la catena di certificati completa e quindi eseguire le operazioni seguenti in ogni appliance:
  
1. Impostare l'applicazione in modalità manutenzione utilizzando il cmdlet Enter-CcUpdate manutenzione.
    
2. Eseguire il comando riportato di seguito: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Se la password del nuovo certificato è la stessa del vecchio, l'importazione avrà esito positivo. Se la password è diversa, verrà visualizzato un messaggio di errore che indica che la password non è corretta e sarà necessario reimpostarla eseguendo il cmdlet Register-CcAppliance con il parametro -Local e quindi ripetendo il passaggio 2. 
    
4. Rimuovere l'applicazione dalla modalità di manutenzione utilizzando il cmdlet Exit -CcUpdate.
    

