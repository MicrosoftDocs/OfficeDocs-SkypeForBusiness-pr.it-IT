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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Il cmdlet Convert-CcIsoToVhdx crea un file del disco rigido virtuale di base (VHDX) utilizzando un file ISO di Windows Server 2012 R2 fornito dal cliente. Il file VHDX verrà utilizzato durante la distribuzione di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802426"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Il cmdlet Convert-CcIsoToVhdx crea un file del disco rigido virtuale di base (VHDX) utilizzando un file ISO di Windows Server 2012 R2 fornito dal cliente. Il file VHDX verrà utilizzato durante la distribuzione di Skype for Business Cloud Connector Edition.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parametri

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Obbligatorio <br/> |System.String  <br/> | Percorso del file ISO di Windows Server 2012 R2. <br/> |
|GeneralizeOnly  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Se il processo di conversione non riesce durante l'aggiornamento di Windows, puoi provare a configurare una rete/proxy e aggiornare Windows manualmente. Al termine del lavoro manuale, è possibile eseguire questo cmdlet con il parametro -GeneralizeOnly e completare i processi rimanenti.  <br/> |
|PauseBeforeUpdate  <br/> |Facoltativo  <br/> |System.Management.Automation.SwitchParameter  <br/> |Per aggiornare Windows, potrebbe essere necessaria una configurazione manuale di rete/proxy nella macchina virtuale di base. Se si specifica questo parametro, il processo di conversione verrà sospeso prima dell'aggiornamento di Windows. Al termine della configurazione manuale, è possibile riprendere il processo.  <br/> |
   
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene preparato il file VHDX di base utilizzando un file ISO di Windows Server 2012 R2 che si trova in "C:\Windows_Server_2012_R2-EN-US-x64.ISO": 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Esempio 2

Se il cmdlet Convert-CcIsoToVhdx non riesce durante l'aggiornamento di Windows, probabilmente è dovuto a una configurazione di rete/proxy errata. È possibile seguire le istruzioni nel messaggio di errore e accedere alla macchina virtuale di base per risolvere il problema e aggiornare Windows manualmente. Al termine del lavoro manuale, eseguire di nuovo il cmdlet con il parametro -GeneralizeOnly per completare i processi rimanenti: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Esempio 3

Se è necessaria una configurazione manuale per aggiornare Windows, è possibile utilizzare il parametro -PauseBeforeUpdate. Con questo parametro, Cloud Connector verrà sospeso prima del processo di aggiornamento di Windows. È quindi possibile completare la configurazione manuale e riprendere il processo di conversione nel modo seguente:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Convert-CcIsoToVhdx crea prima una macchina virtuale di base, installa alcuni componenti di base da cui cloud connector dipende e quindi installa gli aggiornamenti di Windows. Infine, generalizza la macchina virtuale (sysprep) per ottenere un file VHDX di base che verrà utilizzato dalle macchine virtuali di un'appliance Cloud Connector. 
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Convert-CcIsoToVhdx non accetta input da pipeline. 
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

