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
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094834"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Distribuire un sito singolo in Cloud Connector
 
> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)

Informazioni sulla distribuzione di un singolo sito PSTN in Cloud Connector Edition.
  
È possibile distribuire Skype for Business Cloud Connector Edition con o senza il supporto della disponibilità elevata. Se si desidera abilitare l'ha, è necessario distribuire due o più appliance all'interno di un sito. È inoltre possibile convertire un'appliance esistente per supportare l'ha dopo la distribuzione.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Distribuire il primo appliance Skype for Business Cloud Connector Edition

Per distribuire la prima appliance in un sito, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'appliance:
  
```powershell
Register-CcAppliance
```

Seguire le istruzioni per specificare il nome e la password dell'account amministratore tenant. Utilizzare l'account creato per la gestione online del connettore cloud. Seguire inoltre le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore di dominio e la password di amministratore della macchina virtuale. 
  
Nella versione 1.4.2 e versioni precedenti, seguire anche le istruzioni per fornire la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore di dominio e la password di amministratore della macchina virtuale. 
  
Nella versione 2.0 e successive, seguire anche le istruzioni per fornire la password del certificato esterno, la password CceService e la password CABackupFile.
  
Per avviare l'installazione, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Aggiungere un'appliance a un sito esistente

È possibile estendere un sito Cloud Connector esistente per supportare l'ha aggiungendo ulteriori appliance al sito. 
  
1. Seguire i passaggi per preparare l'appliance Cloud Connector come descritto in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md). Tenere presente che alcuni passaggi sono necessari solo per la prima appliance della distribuzione. Verificare che la directory del sito esista e che sia configurata correttamente per il supporto dell'ha.
    
2. Eseguire il cmdlet seguente solo nel server host appena aggiunto per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione di Microsoft 365 o Office 365. Se si desidera aggiungere più appliance contemporaneamente, eseguire il cmdlet in ogni server host appena aggiunto uno alla volta:
    
   ```powershell
   Register-CcAppliance
   ```

3. Aggiornare la topologia nelle appliance esistenti eseguendo il cmdlet seguente in ogni server host. Eseguire il cmdlet solo nelle appliance esistenti.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Eseguire il cmdlet seguente solo nei server host appena aggiunti. Non eseguire questo cmdlet nell'appliance esistente. Se si desidera aggiungere più appliance contemporaneamente, eseguire il cmdlet in ogni server host appena aggiunto uno alla volta.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Se la directory del sito è stata impostata su un percorso di cartella locale, è necessario definire una condivisione file per questa cartella e utilizzare un percorso UNC per la directory dei siti nel nuovo dispositivo. È possibile lasciare la prima directory del sito dell'appliance con il percorso locale o modificarla per utilizzare il percorso UNC per la condivisione nella stessa cartella. Se il percorso della directory del sito condiviso cambia, tutte le appliance installate in precedenza devono essere disinstallate e quindi reinstallate. > Importante: la password sia per l'account CceService che per l'account CABackupFile deve essere la stessa in tutte le appliance distribuite all'interno del sito, in modo che le appliance possano accedere alla condivisione della directory del sito e al file di backup della CA crittografato nella directory dei siti. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Rimuovere un'appliance da un sito esistente

Se si desidera rimuovere un'appliance da un sito esistente:
  
1. Eseguire il cmdlet seguente solo sui server host che si desidera rimuovere dal sito per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione di Microsoft 365 o Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Eseguire il cmdlet seguente solo sui server host da cui si desidera rimuovere tutte le macchine virtuali dell'appliance.
    
   ```powershell
   Uninstall-CcAppliance
   ```