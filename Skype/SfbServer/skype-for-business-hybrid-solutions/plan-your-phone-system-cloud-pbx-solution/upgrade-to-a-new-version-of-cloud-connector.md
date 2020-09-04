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
description: Informazioni su come eseguire l'aggiornamento della distribuzione di Cloud Connector Edition.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359292"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Eseguire l'aggiornamento a una nuova versione di Cloud Connector

> [!Important]
> Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online. Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Informazioni su come eseguire l'aggiornamento della distribuzione di Cloud Connector Edition.
  
Se è stato configurato un account tenant di gestione online e gli aggiornamenti automatici sono stati abilitati, la distribuzione esistente di Skype for Business Cloud Connector Edition verrà aggiornata automaticamente alla versione più recente, in base alla configurazione della finestra di tempo per l'aggiornamento automatico. È inoltre possibile eseguire un aggiornamento manuale. 
  
Le versioni di Cloud Connector Edition 1.4.1 e versioni successive eseguono gli aggiornamenti automatici per impostazione predefinita. Se si desidera eseguire l'aggiornamento alla versione più recente (2,1) manualmente, vedere [upgrade a single site to a New Version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) più avanti in questo argomento.
  
Per l'aggiornamento automatico è necessario che il servizio Cloud Connector sia in esecuzione. Nei passaggi seguenti viene descritto il processo per gli aggiornamenti automatici:
  
- Il processo di aggiornamento automatico verrà eseguito in base alla pianificazione configurata per gli aggiornamenti automatici.
    
- Attività di aggiornamento del sistema operativo
    
  - Controllare e scaricare gli aggiornamenti del sistema operativo per tutte le macchine virtuali dei connettori cloud. 
    
  - Installare e aggiornare tutte le macchine virtuali del connettore Cloud una alla volta e riavviare.
    
  - Dopo il riavvio delle macchine virtuali del connettore Cloud, controllare se è necessario un altro riavvio.
    
  - Dopo che le macchine virtuali dei connettori cloud sono state patchate, ripetere il processo per il computer host del Cloud Connector.
    
  - Dopo il corretto avvio del computer host del connettore Cloud, vengono completate tutte le attività di aggiornamento del sistema operativo in sospeso.
    
- Attività di aggiornamento del connettore Cloud
    
  - Scaricare e controllare il file di versione dal sito di download.
    
  - Scaricare il nuovo file version. msi. 
    
  - Disinstallare il file MSI precedente; installare il nuovo file MSI.
    
  - Scaricare la nuova versione dei bit di Skype for business.
    
  - Registrazione dell'accessorio tramite la chiamata a Register-CcAppliance.
    
  - Installare la nuova versione del connettore Cloud.
    
  - Svuotare il dispositivo vecchio e cambiare la connessione di rete al nuovo accessorio.
    
> [!NOTE]
>  Quando il connettore Cloud viene aggiornato a una nuova generazione, i cmdlet del connettore cloud potrebbero non essere aggiornati. Questa situazione può verificarsi, ad esempio, se una finestra di PowerShell viene lasciata aperta quando si verifica l'aggiornamento automatico. Per caricare i cmdlet aggiornati, è possibile eseguire una delle operazioni seguenti: > chiudere PowerShell nell'accessorio Cloud Connector e quindi riaprire PowerShell. > oppure, è possibile eseguire Import-Module CloudConnector-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Aggiornare un singolo sito a una nuova versione
<a name="BKMK_Upgrade"> </a>

Se è presente un solo dispositivo nel sito che si desidera aggiornare, eseguire le operazioni seguenti:
  
1. Disinstallare la versione del connettore cloud esistente nei ** \> \> programmi e nelle funzionalità dei programmi del pannello di controllo**.
    
2. Installare la nuova versione di CloudConnector.msi da [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Verificare di disporre del file CloudConnector.ini per la versione che si sta installando e di aver aggiornato tutti i valori necessari per l'ambiente. Non è possibile utilizzare il file ini da una versione precedente. Se si esegue l'aggiornamento del connettore Cloud, fare riferimento all'argomento [preparare l'accessorio Cloud Connector](prepare-your-cloud-connector-appliance.md) e verificare che SiteName e EnableReferSupport siano impostati sul valore corretto nel file CloudConnector.ini.
    
4. Avviare una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'accessorio corrente:
    
   ```powershell
   Register-CcAppliance
   ```

5. Eseguire il cmdlet seguente per scaricare la versione più recente:
    
   ```powershell
   Start-CcDownload
   ```

6. Per avviare l'installazione, eseguire il cmdlet seguente: 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. Eseguire il cmdlet seguente per attivare la nuova distribuzione e disattivare la versione precedente:
    
   ```powershell
   Switch-CcVersion
   ```

Se nel sito sono presenti più dispositivi, seguire la procedura descritta in precedenza per aggiornare ogni accessorio uno alla volta.
  
Se si desidera aggiornare l'amministratore del dominio, l'amministratore della macchina virtuale, l'amministratore della modalità provvisoria e le credenziali di amministratore tenant, è possibile eseguire il cmdlet con il parametro  _UpdateAllCredentials_ per reimpostare tutte le credenziali:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Quando si inizia a eseguire l'aggiornamento a una nuova versione, l'utente verrà quindi promosso per immettere le nuove credenziali. 
  
Se si desidera reimpostare solo le credenziali di amministratore tenant, eseguire il cmdlet seguente:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Aggiornare più siti a una nuova versione
<a name="BKMK_Upgrade"> </a>

Seguire la procedura per l'aggiornamento di un singolo sito, l'aggiornamento di un sito alla volta per ogni sito della distribuzione. Verificare e [convalidare la distribuzione del connettore Cloud](validate-your-cloud-connector-deployment.md) dopo l'aggiornamento di ogni sito.
  

