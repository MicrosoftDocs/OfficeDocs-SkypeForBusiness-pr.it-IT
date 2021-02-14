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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359292"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Eseguire l'aggiornamento a una nuova versione di Cloud Connector

> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
 
Informazioni su come aggiornare la distribuzione di Cloud Connector Edition.
  
Se è stato configurato un account tenant di gestione online e sono stati abilitati gli aggiornamenti automatici, la distribuzione esistente di Skype for Business Cloud Connector Edition verrà aggiornata automaticamente alla versione più recente, in base alla configurazione dell'intervallo di tempo di aggiornamento automatico. È inoltre possibile eseguire un aggiornamento manuale. 
  
Cloud Connector Edition versione 1.4.1 e successive esegue gli aggiornamenti automatici per impostazione predefinita. Se si desidera eseguire manualmente l'aggiornamento alla versione più recente (2.1), vedere Aggiornare un singolo sito a una [nuova versione](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) più avanti in questo argomento.
  
L'aggiornamento automatico richiede che il servizio Cloud Connector sia in esecuzione. I passaggi seguenti descrivono il processo per gli aggiornamenti automatici:
  
- Il processo di aggiornamento automatico verrà eseguito in base alla pianificazione configurata per gli aggiornamenti automatici.
    
- Attività di aggiornamento del sistema operativo
    
  - Controllare e scaricare gli aggiornamenti del sistema operativo per tutte le macchine virtuali del connettore cloud. 
    
  - Installare e aggiornare tutte le macchine virtuali di Cloud Connector una alla volta e riavviare.
    
  - Dopo il riavvio delle macchine virtuali di Cloud Connector, verificare se è necessario un altro riavvio.
    
  - Dopo aver corretto l'applicazione di patch alle macchine virtuali del connettore Cloud, ripetere il processo per il computer host cloud connector.
    
  - Dopo l'avvio corretto del computer host cloud Connector, vengono completate tutte le attività di aggiornamento del sistema operativo in sospeso.
    
- Attività di aggiornamento di Cloud Connector
    
  - Scaricare e controllare il file della versione dal sito di download.
    
  - Scaricare il file MSI della nuova versione. 
    
  - Disinstallare il vecchio file msi; installare il nuovo file msi.
    
  - Scaricare la nuova versione dei bit di Skype for Business.
    
  - Registrare l'applicazione chiamando Register-CcAppliance.
    
  - Installare la nuova versione di Cloud Connector.
    
  - Svuotare il vecchio dispositivo e passare la connessione di rete al nuovo dispositivo.
    
> [!NOTE]
>  Quando Cloud Connector esegue l'aggiornamento a una nuova build, i cmdlet di Cloud Connector potrebbero non essere aggiornati. Ciò può verificarsi, ad esempio, se una finestra di PowerShell viene lasciata aperta durante l'aggiornamento automatico. Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti:> Chiudere PowerShell nell'applicazione Cloud Connector e quindi riaprire PowerShell.> Oppure, è possibile eseguire Import-Module CloudConnector -Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Aggiornare un singolo sito a una nuova versione
<a name="BKMK_Upgrade"> </a>

Se nel sito è presente un solo dispositivo da aggiornare, eseguire le operazioni seguenti:
  
1. Disinstallare la versione esistente di Cloud Connector in **Programmi e funzionalità del Pannello di \> \> controllo.**
    
2. Installare la nuova versione di CloudConnector.msi da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Verificare di disporre del CloudConnector.ini per la versione che si sta installando e di aver aggiornato tutti i valori necessari per il proprio ambiente. Non è possibile utilizzare il file ini di una versione precedente. Se si sta aggiornando Cloud Connector, fare riferimento all'argomento Preparare l'applicazione [Cloud Connector](prepare-your-cloud-connector-appliance.md) e assicurarsi che SiteName e EnableReferSupport siano impostati sul valore corretto nel file CloudConnector.ini.
    
4. Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'applicazione corrente:
    
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
  
Se si desidera aggiornare le credenziali di amministratore di dominio, amministratore della macchina virtuale, amministratore in modalità provvisoria e amministratore tenant, è possibile eseguire il cmdlet con il parametro  _UpdateAllCredentials_ per reimpostare tutte le credenziali:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Quindi, quando si inizia l'aggiornamento a una nuova versione, si verrà alzati di livello per immettere le nuove credenziali. 
  
Se si desidera solo reimpostare le credenziali di amministratore tenant, eseguire il cmdlet seguente:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Aggiornare più siti a una nuova versione
<a name="BKMK_Upgrade"> </a>

Eseguire la procedura per aggiornare un singolo sito, aggiornando un sito alla volta per ogni sito della distribuzione. Verificare e [convalidare la distribuzione di Cloud Connector](validate-your-cloud-connector-deployment.md) dopo l'aggiornamento di ogni sito.
  

