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
ms.openlocfilehash: 334454645be3361794fdd0d16076095a518e58b0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220536"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Distribuire un sito singolo in Cloud Connector
 
Informazioni sulla distribuzione di un singolo sito PSTN in Cloud Connector Edition.
  
È possibile distribuire Skype for Business Cloud Connector Edition con o senza il supporto per la disponibilità elevata (HA). Se si desidera abilitare l'HA, è necessario distribuire due o più dispositivi all'interno di un sito. È inoltre possibile convertire un dispositivo esistente per il supporto di HA dopo la distribuzione.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Distribuire il primo accessorio di Skype for Business Cloud Connector Edition

Per distribuire il primo dispositivo in un sito, aprire una console PowerShell come amministratore ed eseguire il cmdlet seguente per registrare l'accessorio:
  
```powershell
Register-CcAppliance
```

Seguire le istruzioni per fornire il nome e la password dell'account di amministratore del tenant. Utilizzare l'account creato per la gestione di Cloud Connector online. Inoltre, seguire le istruzioni per fornire la password del certificato esterno, la password di amministratore della modalità provvisoria, la password di amministratore del dominio e la password di amministratore VM. 
  
In Release 1.4.2 e versioni precedenti, seguire le istruzioni per fornire la password del certificato esterno, la password di amministratore della modalità provvisoria, la password di amministratore del dominio e la password di amministratore della VM. 
  
Nella versione 2,0 e versioni successive, seguire le istruzioni per fornire la password del certificato esterno, la password di CceService e la password di CABackupFile.
  
Per avviare l'installazione, aprire una console di PowerShell come amministratore ed eseguire il cmdlet seguente:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Aggiungere un dispositivo a un sito esistente

È possibile estendere un sito del connettore cloud esistente per il supporto di HA aggiungendo altri dispositivi al sito. 
  
1. Seguire la procedura per preparare l'accessorio Cloud Connector, come descritto in [Prepare your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md). Tenere presente che alcuni passaggi sono necessari solo per il primo dispositivo della distribuzione. Verificare che la directory del sito esista e sia configurata correttamente per il supporto di HA.
    
2. Eseguire il seguente cmdlet solo nel server host appena aggiunto per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione di Microsoft 365 o Office 365. Se si desidera aggiungere più dispositivi contemporaneamente, eseguire il cmdlet su ogni server host appena aggiunto uno per uno:
    
   ```powershell
   Register-CcAppliance
   ```

3. Aggiornare la topologia negli apparecchi esistenti eseguendo il cmdlet seguente in ogni server host. Eseguire solo il cmdlet negli elettrodomestici esistenti.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Eseguire il seguente cmdlet solo sui server host appena aggiunti. Non eseguire questo cmdlet sull'accessorio esistente. Se si desidera aggiungere più dispositivi contemporaneamente, eseguire il cmdlet su ogni server host appena aggiunto uno alla volta.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Se la directory del sito è stata impostata su un percorso della cartella locale, è necessario definire una condivisione file per la cartella e utilizzare un percorso UNC per la directory del sito nel nuovo accessorio. È possibile lasciare la directory del sito del primo dispositivo con il percorso locale o modificarla in modo da utilizzare il percorso UNC per la condivisione nella stessa cartella. Se il percorso della directory del sito condiviso cambia, è necessario disinstallare tutti gli apparecchi installati in precedenza e quindi reinstallarli. > importante: la password per l'account CceService e l'account CABackupFile deve essere la stessa su tutti gli strumenti distribuiti all'interno del sito, in modo che gli strumenti possano accedere alla condivisione directory del sito e al file di backup della CA crittografata nella directory del sito. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Rimozione di un dispositivo da un sito esistente

Se si desidera rimuovere un dispositivo da un sito esistente:
  
1. Eseguire il seguente cmdlet solo nei server host che si desidera rimuovere dal sito per aggiornare le informazioni sulla topologia nella configurazione dell'organizzazione Microsoft 365 o Office 365.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Eseguire il seguente cmdlet solo nei server host da cui si desidera rimuovere tutte le macchine virtuali dell'accessorio.
    
   ```powershell
   Uninstall-CcAppliance
   ```


