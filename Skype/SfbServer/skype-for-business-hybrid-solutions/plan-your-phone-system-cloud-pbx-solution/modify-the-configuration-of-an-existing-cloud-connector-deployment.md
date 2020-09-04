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
description: Seguire la procedura descritta in questo argomento per modificare la configurazione di una distribuzione di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva esistente.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359112"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Modificare la configurazione di una distribuzione di Cloud Connector esistente

> [!Important]
> Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online. Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Seguire la procedura descritta in questo argomento per modificare la configurazione di una distribuzione di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva esistente. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Modificare la configurazione di un singolo sito
<a name="BKMK_SIngleSite"> </a>

Se nel sito è presente un solo dispositivo, quando si desidera modificare le impostazioni di configurazione dopo la distribuzione dell'accessorio, è possibile modificare il file CloudConnector.ini e riavviare di nuovo la distribuzione.
  
1. Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nel server host: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Eseguire il seguente cmdlet per annullare la registrazione dell'accessorio:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aggiornare il file CloudConnector.ini nella directory appliance.
    
4. Eseguire il cmdlet seguente per aggiornare la configurazione: (questo passaggio è applicabile solo per la versione 2, per le versioni precedenti, passare al passaggio successivo).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Eseguire il cmdlet seguente per registrare nuovamente l'accessorio:
    
   ```powershell
   Register-CcAppliance
   ```

6. Eseguire il seguente cmdlet per installare Skype for Business Cloud Connector Edition:
    
   ```powershell
   Install-CcAppliance
   ```

Se nel sito sono presenti più dispositivi, è necessario attenersi alla seguente procedura, modificare il file CloudConnector.ini e ridistribuire gli elettrodomestici uno alla volta.
  
1. Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nell'accessorio corrente: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Eseguire il seguente cmdlet per annullare la registrazione dell'accessorio:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aggiornare il file CloudConnector.ini nella directory appliance.
    
4. Eseguire il cmdlet seguente per aggiornare la configurazione: (questo passaggio è applicabile solo per la versione 2, per le versioni precedenti, passare al passaggio successivo).
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Eseguire il cmdlet seguente per registrare nuovamente l'accessorio:
    
   ```powershell
   Register-CcAppliance
   ```

6. Eseguire il cmdlet seguente in tutti gli altri dispositivi del sito per raccogliere la configurazione più recente:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Eseguire il cmdlet seguente per ridistribuire il connettore Cloud nell'accessorio corrente:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Modificare la configurazione di più siti
<a name="BKMK_MultipleSites"> </a>

Per modificare la configurazione di più siti in una distribuzione, seguire la procedura per un singolo sito, aggiornando un sito alla volta.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Modificare la configurazione dell'organizzazione Microsoft 365 o Office 365 per abilitare gli aggiornamenti automatici
<a name="BKMK_MultipleSites"> </a>

Per abilitare gli aggiornamenti automatici del sistema operativo e gli aggiornamenti automatici dei bit, è necessario utilizzare l'account di amministratore del tenant di Skype for business per la gestione online e utilizzare Remote PowerShell tenant come indicato di seguito.
  
Se sono stati disabilitati gli aggiornamenti automatici dei bit o degli aggiornamenti automatici del sistema operativo, l'host e la macchina virtuale potrebbero non essere più importanti per gli aggiornamenti di Windows e Cloud Connector non verrà aggiornato automaticamente alla nuova versione. È consigliabile abilitare gli aggiornamenti automatici.
  
1. È necessario che la proprietà EnableAutoUpdate del sito sia impostata su true (il valore predefinito). Eseguire il cmdlet seguente per assicurarsi che EnableAutoUpdate sia impostato su true:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Creare la finestra di tempo di aggiornamento automatico per il tenant.
    
    La finestra temporale può essere giornaliera, settimanale e mensile. Tutte le finestre temporali necessitano di un'ora di inizio e una durata.
    
   - Per una finestra di tempo giornaliero, sono necessari solo l'ora di inizio e la durata. 
    
   - Per una finestra di tempo settimanale, sono necessari giorni della settimana, che possono essere un solo giorno o più giorni.
    
   - Per una finestra di tempo mensile, possono essere presenti due tipi. Il primo tipo è quello di specificare il giorno del mese, che può essere un solo giorno. Il secondo tipo è quello di specificare le settimane del mese, insieme ai giorni della settimana, che possono essere entrambi un singolo elemento o più elementi.
    
   - Ogni tenant può disporre di 20 finestre temporali definite. La finestra di tempo predefinita verrà creata per un nuovo tenant come finestra temporale predefinita per l'aggiornamento dei sistemi operativi e l'aggiornamento dei bit. Eseguire i seguenti cmdlet per impostare la finestra di tempo giornaliero, settimanale o mensile:
    
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

   - Assegnare le finestre di tempo di aggiornamento al sito. 
    
     Le finestre dell'ora di aggiornamento dei bit e del sistema operativo sono configurate separatamente. Entrambe possono essere assegnate a una o più finestre temporali. Ogni finestra di tempo può essere assegnata a siti diversi e a un altro scopo (aggiornamento dei bit e aggiornamento del sistema operativo). Eseguire il cmdlet seguente per impostare la finestra temporale per il sito: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aggiornare le credenziali di amministratore tenant dedicate
<a name="BKMK_MultipleSites"> </a>

Le modifiche amministrative nell'organizzazione di Microsoft 365 o Office 365 per il connettore Cloud sono eseguite da un account con le autorizzazioni necessarie. Nelle versioni di connettori cloud precedenti all'2,0, quell'account è un account amministratore globale dedicato del tenant. In Cloud Connector Versions 2,0 e versioni successive, quell'account può essere un account Microsoft 365 o Office 365 con i diritti di amministratore di Skype for business.
  
Se le credenziali dell'account di amministratore cambiano in Microsoft 365 o Office 365, è inoltre necessario aggiornare le credenziali memorizzate nella cache locale in Cloud Connector eseguendo il comando di PowerShell di amministratore seguente su ogni accessorio Cloud Connector distribuito:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aggiornare la password per il server host
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Questa sezione è applicabile al connettore Cloud versione 2,0 e versioni successive. 
  
Tutte le credenziali del connettore Cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ". Quando la password sul server host cambia, sarà necessario aggiornare le credenziali memorizzate localmente.
  
Per aggiornare le credenziali memorizzate localmente nell'accessorio Cloud Connector, utilizzare i cmdlet [Get-CcCredential](get-cccredential.md) e [set-CcCredential](set-cccredential.md) e attenersi alla seguente procedura:
  
1. Eseguire i seguenti comandi per recuperare le password necessarie in un secondo momento: 
    
   - Get-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType CceService-DisplayPassword
    
2. Modificare la password dell'account sul server host.
    
3. Riavviare il server host.
    
4. Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".
    
5. Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione. Assicurarsi di immettere la stessa password immessa prima per la distribuzione del connettore Cloud.
    
Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService. Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire le operazioni seguenti:
  
1. Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:
    
1. Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.
    
2. Quando viene richiesto per la nuova credenziale account, immettere la password per la password di DomainAdmin restituita nel passaggio 1.
    
2. Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:
    
1. Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.
    
2. Quando viene richiesto per la nuova credenziale account, immettere la password per la password di VmAdmin restituita nel passaggio 1. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aggiornare la password per l'account CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Questa sezione è applicabile a Cloud Connector versione 2.0.1 e successive. 
  
Il servizio Cloud Connector esegue il servizio di gestione Cloud Connector. L'account CceService viene creato durante la distribuzione di Cloud Connector Edition e archiviato nei seguenti file: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML "e"% SystemDrive% \Programdata\Cloudconnector\credentials..CceService.xml ".
  
Per assicurarsi che tutti gli apparecchi possano accedere alla condivisione directory del sito, la password per l'account CceService deve essere identica su tutti gli elettrodomestici distribuiti all'interno del sito. Tenere presente quanto segue:
  
- Per impostazione predefinita, l'account CceService è configurato come "password non scade mai". Quando si aggiorna la password, Microsoft consiglia di mantenere la configurazione.
    
- È necessario aggiornare la password durante periodi di utilizzo non di picco e al di fuori delle finestre di tempo di aggiornamento automatico per i bit o gli aggiornamenti di Windows. Quando si aggiorna la password, l'accessorio deve essere svuotato e riavviato, che richiede un certo tempo. Il riavvio dell'accessorio interromperà le operazioni di aggiornamento automatico. 
    
- Quando si modifica la password dell'account CceService, sarà necessario specificare tutte le credenziali e aggiornarle nel file archiviato localmente. 
    
Per ogni accessorio che appartiene allo stesso sito PSTN, è necessario specificare quanto segue: 
  
1. Eseguire i seguenti comandi per recuperare i nomi account e le password che verranno utilizzate in un secondo momento:
    
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

2. Eseguire il cmdlet Enter-CcUpdate per svuotare l'accessorio e spostarlo in modalità di manutenzione manuale.
    
3. Aggiornare la password dell'account CceService sul server host.
    
4. Riavviare il server host.
    
5. Eseguire il cmdlet Restore-CcCredentials per immettere di nuovo le password dopo la descrizione. 
    
    Assicurarsi di immettere la stessa password immessa prima per la distribuzione del connettore Cloud, ad eccezione dell'account CceService. Per l'account CceService, immettere la nuova password. Verificare che la nuova password per l'account CceService sia uguale per tutti gli elettrodomestici nel sito PSTN.
    
6. Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService. Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire le operazioni seguenti:
    
7. Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:
    
   - Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.
    
   - Quando viene richiesto per la nuova credenziale account, immettere la password per la password di DomainAdmin restituita nel passaggio 1.
    
8. Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:
    
   - Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.
    
   - Quando viene richiesto per la nuova credenziale account, immettere la password per la password di VmAdmin restituita nel passaggio 1. 
    
9. Eseguire il cmdlet Exit-CcUpdate per spostare l'apparecchio fuori dalla modalità di manutenzione manuale.
    
10. Dopo aver completato la procedura in tutti gli elettrodomestici nello stesso sito PSTN, eliminare i seguenti file nella directory radice del sito:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Aggiungere un nuovo dominio SIP
<a name="BKMK_UpdatePassword"> </a>

Per aggiungere un nuovo dominio SIP (o più domini SIP) alla distribuzione del connettore cloud esistente, eseguire le operazioni seguenti:
  
1. Assicurarsi di aver completato la procedura per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS. Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere [aggiungere un dominio a microsoft 365 o office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aggiornare il file di configurazione del connettore Cloud con il nuovo dominio SIP o i domini.
    
3. Richiedere un nuovo certificato esterno di Edge con nomi di SAN aggiuntivi per SIP. Domain per ogni dominio SIP definito nella configurazione del connettore Cloud. 
    
4. Impostare il percorso per il nuovo certificato esterno del server perimetrale come indicato di seguito:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Seguire le istruzioni per [modificare la configurazione di un singolo sito](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [modificare la configurazione di più siti](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Modificare il dominio SIP principale
<a name="BKMK_UpdatePassword"> </a>

Se è necessario modificare il dominio SIP principale nella distribuzione del connettore Cloud, eseguire le operazioni seguenti:
  
1. Assicurarsi di aver completato la procedura per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS. Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere [aggiungere un dominio a microsoft 365 o office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aggiornare il file di configurazione del connettore Cloud con il nuovo dominio SIP.
    
3. Richiedere un nuovo certificato esterno di Edge con nomi di SAN aggiuntivi per SIP. Domain per ogni dominio SIP definito nella configurazione del connettore Cloud. 
    
4. Impostare il percorso per il nuovo certificato esterno del server perimetrale come indicato di seguito:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Rimuovere la registrazione del tenant per ogni accessorio in un sito eseguendo il cmdlet seguente in PowerShell amministratore su cloud Connector:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Rimuovere la registrazione del sito per ogni sito eseguendo il seguente cmdlet in PowerShell per Skype for business online:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Disinstallare ogni accessorio eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registrare ogni accessorio eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installare ogni dispositivo, uno alla volta, eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Sostituire il certificato del perimetro esterno con un nuovo certificato
<a name="BKMK_UpdatePassword"> </a>

Quando è necessario sostituire il certificato perimetrale esterno negli apparecchi del connettore Cloud, è necessario ottenere un nuovo certificato Edge, preparare il file PFX contenente la chiave privata e la catena di certificati completi e quindi eseguire le operazioni seguenti in ogni accessorio:
  
1. Utilizzare il cmdlet Enter-CcUpdate per attivare la modalità di manutenzione.
    
2. Eseguire il comando seguente: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Se la password del nuovo certificato è identica alla vecchia, l'importazione avrà esito positivo. Se la password è diversa, verrà visualizzato un messaggio di errore che indica che la password è errata e sarà necessario reimpostare la password eseguendo il cmdlet Register-CcAppliance con il parametro-local e quindi ripetendo il passaggio 2. 
    
4. Estrarre l'apparecchio dalla modalità di manutenzione utilizzando il cmdlet Exit-CcUpdate.
    

