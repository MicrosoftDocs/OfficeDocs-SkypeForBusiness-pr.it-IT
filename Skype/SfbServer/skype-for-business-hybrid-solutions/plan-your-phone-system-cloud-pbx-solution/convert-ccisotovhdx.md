---
title: Convert-CcIsoToVhdx
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Il cmdlet Convert-CcIsoToVhdx crea un file di disco rigido virtuale di base (VHDX) usando un file ISO di Windows Server 2012 R2 fornito dal cliente. Il file VHDX verrà usato durante la distribuzione di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 780002c54a77746c51f418cae077ffcc9b1fb608
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001346"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Il cmdlet Convert-CcIsoToVhdx crea un file di disco rigido virtuale di base (VHDX) usando un file ISO di Windows Server 2012 R2 fornito dal cliente. Il file VHDX verrà usato durante la distribuzione di Skype for Business Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parametri

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Obbligatorio <br/> |System.String  <br/> | Percorso del file ISO di Windows Server 2012 R2. <br/> |
|GeneralizeOnly  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se il processo di conversione non riesce durante Windows Update, è possibile provare a configurare una rete/proxy e aggiornare le finestre manualmente. Dopo aver completato il lavoro manuale, puoi eseguire questo cmdlet con il parametro-GeneralizeOnly e completare i processi rimanenti.  <br/> |
|PauseBeforeUpdate  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Per aggiornare Windows, potrebbe essere necessario qualche configurazione manuale della rete/proxy sulla VM di base. Il processo di conversione verrà sospeso prima di Windows Update se questo parametro è disponibile. Dopo aver completato la configurazione manuale, è possibile riprendere il processo.  <br/> |
   
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente prepara il file VHDX di base usando un file ISO di Windows Server 2012 R2 che si trova in "C:\ Windows_Server_2012_R2-EN-US-x64. ISO": 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Esempio 2

Se il cmdlet Convert-CcIsoToVhdx non riesce durante Windows Update, è probabilmente a causa di una configurazione di rete/proxy non corretta. È possibile seguire le istruzioni nel messaggio di errore e accedere alla macchina virtuale di base per correggere il problema e aggiornare le finestre manualmente. Dopo aver completato il lavoro manuale, eseguire di nuovo il cmdlet con il parametro-GeneralizeOnly per completare i processi rimanenti: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Esempio 3

Se è necessaria la configurazione manuale per aggiornare Windows, è possibile usare il parametro-PauseBeforeUpdate. Con questo parametro, il connettore Cloud verrà sospeso prima del processo di Windows Update. È quindi possibile completare la configurazione manuale e riprendere il processo di conversione nel modo seguente:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Convert-CcIsoToVhdx crea prima una VM di base, installa alcuni componenti di base da cui dipende il Cloud Connector e quindi installa gli aggiornamenti di Windows. Infine, generalizza la macchina virtuale (Sysprep) per ottenere un file di VHDX di base che verrà usato dalle macchine virtuali di un appliance di connessione cloud. 
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Convert-CcIsoToVhdx non accetta l'input da pipeline. 
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

