---
title: Export-CcConfigurationSampleFile
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
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Il cmdlet Export-CcConfigurationSampleFile esporta un file di configurazione di esempio di Skype for Business Cloud Connector Edition (ini) nella directory appliance di un'applicazione Cloud Connector. È possibile modificare e rinominare il file da utilizzare per la distribuzione.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801006"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Il cmdlet Export-CcConfigurationSampleFile esporta un file di configurazione di esempio di Skype for Business Cloud Connector Edition (ini) nella directory appliance di un'applicazione Cloud Connector. È possibile modificare e rinominare il file da utilizzare per la distribuzione.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene scaricato un file di configurazione di esempio dal sito Microsoft e scritto nella directory appliance dell'appliance Cloud Connector:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

La versione corrente di Cloud Connector richiede di fornire diversi parametri nel file ini; ad esempio, parametri come gli indirizzi IP delle macchine virtuali per i componenti del connettore cloud, i nomi dei componenti, i parametri del gateway e così via.
  
Questo cmdlet, quando viene eseguito nel computer host di Cloud Connector, scarica un file ini di esempio con esempi di configurazione dal sito Microsoft. Il cmdlet scrive il file nella directory appliance dell'applicazione Cloud Connector. La directory dell'appliance viene specificata utilizzando il cmdlet Set-CcApplianceDirectory locale.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Export-CcConfigurationSampleFile non accetta input da pipeline. 
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

