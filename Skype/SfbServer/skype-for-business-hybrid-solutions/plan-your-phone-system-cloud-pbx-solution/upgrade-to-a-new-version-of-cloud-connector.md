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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.
ms.openlocfilehash: 3398fcdf9437a496cf5f4fb94f0fb92dc6a1da42
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588428"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Eseguire l'aggiornamento a una nuova versione di Cloud Connector

> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).
 
Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.
  
Se è stato configurato un account tenant di gestione online e sono stati abilitati gli aggiornamenti automatici, la distribuzione esistente di Skype for Business Cloud Connector Edition verrà aggiornata automaticamente alla versione più recente, in base alla configurazione dell'intervallo di tempo di aggiornamento automatico. È inoltre possibile eseguire un aggiornamento manuale. 
  
Cloud Connector Edition versioni 1.4.1 e successive esegue gli aggiornamenti automatici per impostazione predefinita. Se si desidera eseguire manualmente l'aggiornamento alla versione più recente (2.1), vedere Aggiornare un singolo sito [a una nuova versione](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) più avanti in questo argomento.
  
L'aggiornamento automatico richiede che il servizio Cloud Connector sia in esecuzione. I passaggi seguenti descrivono il processo per gli aggiornamenti automatici:
  
- Il processo di aggiornamento automatico verrà eseguito in base alla pianificazione configurata per gli aggiornamenti automatici.
    
- Attività di aggiornamento del sistema operativo
    
  - Controllare e scaricare gli aggiornamenti del sistema operativo per tutte le macchine virtuali cloud Connector. 
    
  - Installare e aggiornare tutte le macchine virtuali di Cloud Connector una alla volta e riavviare.
    
  - Dopo il riavvio delle macchine virtuali del connettore cloud, verificare se è necessario un altro riavvio.
    
  - Dopo la corretta applicazione di patch alle macchine virtuali del connettore cloud, ripetere il processo per il computer host del connettore cloud.
    
  - Dopo l'avvio corretto del computer host cloud Connector, tutte le attività di aggiornamento del sistema operativo in sospeso vengono completate.
    
- Attività di aggiornamento del connettore cloud
    
  - Scaricare e controllare il file della versione dal sito di download.
    
  - Scaricare la nuova versione .msi file. 
    
  - Disinstallare il vecchio file msi; installare il nuovo file msi.
    
  - Scarica la nuova versione di Skype for Business bit.
    
  - Registrare l'appliance chiamando Register-CcAppliance.
    
  - Installare la nuova versione di Cloud Connector.
    
  - Svuotare il vecchio dispositivo e passare la connessione di rete al nuovo dispositivo.
    
> [!NOTE]
>  Quando Cloud Connector si aggiorna a una nuova build, i cmdlet di Cloud Connector potrebbero non essere aggiornati. Ciò può verificarsi, ad esempio, se una finestra di PowerShell viene lasciata aperta durante l'aggiornamento automatico. Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:> Chiudere PowerShell nell'appliance Cloud Connector e quindi riaprire PowerShell.> Oppure, è possibile eseguire Import-Module CloudConnector -Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Aggiornare un singolo sito a una nuova versione
<a name="BKMK_Upgrade"> </a>

Se nel sito è presente un solo dispositivo che si desidera aggiornare, eseguire le operazioni seguenti:
  
1. Disinstallare la versione esistente di Cloud Connector nel **Pannello di controllo Programmi e \> \> funzionalità**.
    
2. Installare la nuova versione di CloudConnector.msi da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Verificare di disporre del file CloudConnector.ini per la versione che si sta installando e di aver aggiornato tutti i valori necessari per l'ambiente. Non è possibile utilizzare il file .ini di una versione precedente. Se si sta aggiornando Cloud Connector, fare riferimento all'argomento [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) e assicurarsi che SiteName e EnableReferSupport siano impostati sul valore corretto nel file CloudConnector.ini.
    
4. Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'appliance corrente:
    
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

Se nel sito sono presenti più appliance, seguire i passaggi precedenti per aggiornare ogni appliance uno alla volta.
  
Se si desidera aggiornare le credenziali di amministratore di dominio, amministratore della macchina virtuale, amministratore della modalità Cassaforte e amministratore tenant, è possibile eseguire il cmdlet con il parametro _UpdateAllCredentials_ per reimpostare tutte le credenziali:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Quindi, quando inizi a eseguire l'aggiornamento a una nuova versione, ti verrà promosso per immettere le nuove credenziali. 
  
Se si desidera reimpostare solo le credenziali di amministratore tenant, eseguire il cmdlet seguente:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Aggiornare più siti a una nuova versione
<a name="BKMK_Upgrade"> </a>

Seguire la procedura per aggiornare un singolo sito, aggiornando un sito alla volta per ogni sito della distribuzione. Verificare e [convalidare la distribuzione del connettore cloud](validate-your-cloud-connector-deployment.md) dopo l'aggiornamento di ogni sito.
