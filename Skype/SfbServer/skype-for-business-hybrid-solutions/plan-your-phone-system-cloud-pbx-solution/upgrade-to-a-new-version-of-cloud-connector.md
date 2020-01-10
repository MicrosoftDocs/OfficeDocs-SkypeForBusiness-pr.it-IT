---
title: Eseguire l'aggiornamento a una nuova versione di Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.
ms.openlocfilehash: c340b7325c95d25212c9c1f77f9379a25708cea8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002046"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Eseguire l'aggiornamento a una nuova versione di Cloud Connector
 
Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.
  
Se è stato configurato un account del tenant di gestione online e sono stati abilitati gli aggiornamenti automatici, la distribuzione esistente di Skype for Business Cloud Connector Edition verrà aggiornata automaticamente alla versione più recente, in base alla finestra del periodo di aggiornamento automatico configurazione. È anche possibile eseguire un aggiornamento manuale. 
  
Le versioni di Cloud Connector Edition 1.4.1 e successive eseguono gli aggiornamenti automatici per impostazione predefinita. Se si vuole eseguire l'aggiornamento manualmente alla versione più recente (2,1), vedere [aggiornare un singolo sito a una nuova versione](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) più avanti in questo argomento.
  
L'aggiornamento automatico richiede che il servizio Cloud Connector sia in funzione. I passaggi seguenti descrivono il processo per gli aggiornamenti automatici:
  
- Il processo di aggiornamento automatico verrà eseguito in base alla programmazione configurata per gli aggiornamenti automatici.
    
- Attività di aggiornamento del sistema operativo
    
  - Controllare e scaricare gli aggiornamenti del sistema operativo in tutte le VM Connector di cloud. 
    
  - Installare e aggiornare tutte le VM del connettore Cloud una alla volta e riavviare.
    
  - Dopo il riavvio del Cloud Connector VM, verificare se è necessario un altro riavvio.
    
  - Dopo la corretta correzione delle VM Connector cloud, ripetere il processo per il computer host Cloud Connector.
    
  - Dopo che il computer host del Cloud Connector si avvia correttamente, vengono completate le attività di aggiornamento del sistema operativo in sospeso.
    
- Attività di aggiornamento di Cloud Connector
    
  - Scaricare e controllare il file di versione dal sito di download.
    
  - Scaricare il nuovo file version. msi. 
    
  - Disinstallare il vecchio file MSI; installare il nuovo file MSI.
    
  - Scaricare la nuova versione di bit di Skype for business.
    
  - Registrare l'accessorio chiamando Register-CcAppliance.
    
  - Installare la nuova versione del connettore Cloud.
    
  - Svuotare il vecchio elettrodomestico e passare alla connessione di rete al nuovo dispositivo.
    
> [!NOTE]
>  Quando Cloud Connector viene aggiornato a una nuova build, i cmdlet di Cloud Connector potrebbero non essere aggiornati. Questo può accadere, ad esempio, se una finestra di PowerShell viene aperta mentre si verifica l'aggiornamento automatico. Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti: > chiudere PowerShell nell'appliance di Cloud Connector e quindi riaprire PowerShell. > oppure, è possibile avviare Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Aggiornare un singolo sito a una nuova versione
<a name="BKMK_Upgrade"> </a>

Se nel sito si vuole aggiornare un solo dispositivo, eseguire le operazioni seguenti:
  
1. Disinstallare la versione del connettore cloud esistente nei **programmi \> e \> nelle funzionalità dei programmi del pannello di controllo**.
    
2. Installare la nuova versione di CloudConnector. msi da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Verificare di avere il file CloudConnector. ini per la versione che si sta installando e di avere aggiornato tutti i valori necessari per l'ambiente. Non è possibile usare il file ini da una versione precedente. Se si sta aggiornando il connettore Cloud, vedere l'argomento [preparare l'accessorio Cloud Connector](prepare-your-cloud-connector-appliance.md) e verificare che SiteName e EnableReferSupport siano impostati sul valore corretto nel file CloudConnector. ini.
    
4. Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'accessorio corrente:
    
   ```powershell
   Register-CcAppliance
   ```

5. Eseguire il cmdlet seguente per scaricare la versione più recente:
    
   ```powershell
   Start-CcDownload
   ```

6. Eseguire il cmdlet seguente per avviare l'installazione: 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. Eseguire il cmdlet seguente per attivare la nuova distribuzione e disattivare la versione precedente:
    
   ```powershell
   Switch-CcVersion
   ```

Se nel sito sono presenti più dispositivi, seguire la procedura descritta in precedenza per aggiornare ogni appliance uno alla volta.
  
Se si vuole aggiornare l'amministratore di dominio, l'amministratore della macchina virtuale, l'amministratore della modalità provvisoria e le credenziali di amministratore del tenant, è possibile eseguire il cmdlet con il parametro _UpdateAllCredentials_ per reimpostare tutte le credenziali:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Quando si inizia a eseguire l'aggiornamento a una nuova versione, verrà promosso per l'immissione delle nuove credenziali. 
  
Se si vuole reimpostare solo le credenziali di amministratore del tenant, eseguire il cmdlet seguente:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Aggiornare più siti a una nuova versione
<a name="BKMK_Upgrade"> </a>

Seguire la procedura per l'aggiornamento di un singolo sito, l'aggiornamento di un sito alla volta per ogni sito della distribuzione. Verificare e [convalidare la distribuzione di Cloud Connector](validate-your-cloud-connector-deployment.md) dopo l'aggiornamento di ogni sito.
  

