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
ms.openlocfilehash: 09aa2e2a7417539757c70368e4f7a508de57bc7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799706"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Distribuire un sito singolo in Cloud Connector
 
Informazioni sulla distribuzione di un singolo sito PSTN in Cloud Connector Edition.
  
È possibile distribuire Skype for Business Cloud Connector Edition con o senza supporto per la disponibilità elevata (HA). Se si vuole abilitare HA, è necessario distribuire due o più dispositivi all'interno di un sito. È anche possibile convertire un dispositivo esistente per supportarlo dopo la distribuzione.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Distribuire il primo appliance di Skype for Business Cloud Connector Edition

Per distribuire il primo appliance in un sito, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'accessorio:
  
```powershell
Register-CcAppliance
```

Seguire le istruzioni per specificare il nome dell'account di amministratore del tenant e la password. Usare l'account creato per la gestione di Cloud Connector online. Seguire inoltre le istruzioni fornite per specificare la password del certificato esterno, la password di amministratore in modalità provvisoria, la password di amministratore del dominio e la password di amministratore VM. 
  
In versione 1.4.2 e versioni precedenti seguire anche le istruzioni fornite per specificare la password del certificato esterno, la password di amministratore della modalità provvisoria, la password di amministratore del dominio e la password di amministratore della VM. 
  
In versione 2,0 e successive seguire anche le istruzioni per specificare la password del certificato esterno, la password di CceService e la password di CABackupFile.
  
Per avviare l'installazione, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Aggiungere un dispositivo a un sito esistente

È possibile estendere un sito del connettore cloud esistente per supportare la disponibilità aggiungendo altri dispositivi al sito. 
  
1. Seguire la procedura per preparare l'accessorio Cloud Connector come descritto in [preparare l'accessorio per il Cloud Connector](prepare-your-cloud-connector-appliance.md). Tieni presente che alcuni passaggi sono necessari solo per il primo appliance della distribuzione. Verificare che la directory del sito esista e sia correttamente configurata per il supporto di HA.
    
2. Eseguire il cmdlet seguente solo nel server host appena aggiunto per aggiornare le informazioni sulla topologia nella configurazione del tenant di Office 365. Se si vogliono aggiungere più dispositivi contemporaneamente, eseguire il cmdlet su ogni server host appena aggiunto uno alla volta:
    
   ```powershell
   Register-CcAppliance
   ```

3. Aggiornare la topologia in dispositivi esistenti eseguendo il cmdlet seguente in ogni server host. Eseguire solo il cmdlet negli elettrodomestici esistenti.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Eseguire il cmdlet seguente solo per i server host appena aggiunti. Non eseguire questo cmdlet nell'appliance esistente. Se si vogliono aggiungere più dispositivi contemporaneamente, eseguire il cmdlet su ogni server host appena aggiunto uno alla volta.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Se la directory del sito è stata impostata su un percorso di cartella locale, è necessario definire una condivisione file per questa cartella e usare un percorso UNC per la directory del sito nel nuovo accessorio. Per usare il percorso UNC della condivisione nella stessa cartella, è possibile che la prima directory del sito dell'appliance sia associata al percorso locale o modificarla. Se la posizione della directory condivisa del sito cambia, è necessario disinstallare gli apparecchi installati in precedenza e quindi reinstallarli. > importante: la password per l'account CceService e per l'account CABackupFile deve essere uguale per tutti gli elettrodomestici distribuiti nel sito, in modo che gli apparecchi possano accedere alla condivisione della directory del sito e al file di backup della CA crittografata nella directory del sito. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Rimuovere un dispositivo da un sito esistente

Se si vuole rimuovere un dispositivo da un sito esistente:
  
1. Eseguire il cmdlet seguente solo nei server host che si desidera rimuovere dal sito per aggiornare le informazioni sulla topologia nella configurazione del tenant di Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Eseguire il cmdlet seguente solo nei server host da cui si vogliono rimuovere tutte le macchine virtuali dell'appliance.
    
   ```powershell
   Uninstall-CcAppliance
   ```


