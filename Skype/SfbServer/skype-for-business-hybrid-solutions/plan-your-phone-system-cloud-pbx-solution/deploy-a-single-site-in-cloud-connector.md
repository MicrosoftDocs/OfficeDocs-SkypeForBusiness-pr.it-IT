---
title: Distribuire un sito singolo in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Informazioni sulla distribuzione di un singolo sito PSTN in Cloud Connector Edition.
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358932"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Distribuire un sito singolo in Cloud Connector
 
> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Informazioni sulla distribuzione di un singolo sito PSTN in Cloud Connector Edition.
  
È possibile distribuire Skype for Business Cloud Connector Edition con o senza il supporto di Disponibilità elevata (HA). Se si desidera abilitare la funzionalità di attivazione della funzionalità di aggiornamento, è necessario distribuire due o più appliance all'interno di un sito. È inoltre possibile convertire un'applicazione esistente per supportare la funzionalità di ha dopo la distribuzione.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Distribuire il primo dispositivo Skype for Business Cloud Connector Edition

Per distribuire il primo dispositivo in un sito, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'applicazione:
  
```powershell
Register-CcAppliance
```

Seguire le istruzioni per specificare il nome e la password dell'account di amministratore tenant. Utilizzare l'account creato per la gestione online di Cloud Connector. Seguire inoltre le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore di dominio e la password di amministratore della macchina virtuale. 
  
Nella versione 1.4.2 e versioni precedenti, seguire anche le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore del dominio e la password di amministratore della macchina virtuale. 
  
Nella versione 2.0 e successive, seguire anche le istruzioni per fornire la password del certificato esterno, la password CceService e la password CABackupFile.
  
Per avviare l'installazione, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Aggiungere un'applicazione a un sito esistente

È possibile estendere un sito Cloud Connector esistente per supportare l'ha aggiungendo ulteriori appliance al sito. 
  
1. Seguire i passaggi per preparare l'applicazione Cloud Connector come descritto in [Preparare l'applicazione Cloud Connector.](prepare-your-cloud-connector-appliance.md) Si noti che alcuni passaggi sono necessari solo per il primo dispositivo della distribuzione. Verificare che la directory del sito esista e sia configurata correttamente per il supporto della rubrica.
    
2. Eseguire il cmdlet seguente solo nel server host appena aggiunto per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione di Microsoft 365 o Office 365. Se si desidera aggiungere più appliance contemporaneamente, eseguire il cmdlet in ogni server host appena aggiunto uno alla volta:
    
   ```powershell
   Register-CcAppliance
   ```

3. Aggiornare la topologia nelle appliance esistenti eseguendo il cmdlet seguente in ogni server host. Eseguire il cmdlet solo nelle appliance esistenti.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Eseguire il cmdlet seguente solo sui server host appena aggiunti. Non eseguire questo cmdlet nell'applicazione esistente. Se si desidera aggiungere più appliance contemporaneamente, eseguire il cmdlet in ogni server host appena aggiunto uno alla volta.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Se la directory del sito è stata impostata su un percorso di cartella locale, è necessario definire una condivisione file per questa cartella e utilizzare un percorso UNC per la directory siti nel nuovo dispositivo. È possibile lasciare la prima directory del sito del dispositivo con il percorso locale o modificarla in modo da utilizzare il percorso UNC per la condivisione nella stessa cartella. Se il percorso della directory del sito condiviso cambia, tutte le appliance installate in precedenza devono essere disinstallate e quindi reinstallate. > Importante: la password per l'account CceService e l'account CABackupFile deve essere la stessa in tutte le appliance distribuite all'interno del sito, in modo che le appliance possano accedere alla condivisione della directory dei siti e al file di backup della CA crittografata nella directory del sito. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Rimuovere un dispositivo da un sito esistente

Se si desidera rimuovere un'applicazione da un sito esistente:
  
1. Eseguire il cmdlet seguente solo sui server host che si desidera rimuovere dal sito per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione di Microsoft 365 o Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Eseguire il cmdlet seguente solo sui server host da cui si desidera rimuovere tutte le macchine virtuali dell'appliance.
    
   ```powershell
   Uninstall-CcAppliance
   ```


