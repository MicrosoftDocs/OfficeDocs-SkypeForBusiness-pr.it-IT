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
ms.localizationpriority: medium
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Il cmdlet Export-CcConfigurationSampleFile esporta un file Skype for Business Cloud Connector Edition di configurazione di esempio (.ini) nella directory appliance di un dispositivo Cloud Connector. È possibile modificare e rinominare il file da utilizzare per la distribuzione.
ms.openlocfilehash: 409514761c3bfeccebb671d289201fc67f58d220
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603665"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Il cmdlet Export-CcConfigurationSampleFile esporta un file Skype for Business Cloud Connector Edition di configurazione di esempio (.ini) nella directory appliance di un dispositivo Cloud Connector. È possibile modificare e rinominare il file da utilizzare per la distribuzione.
  
Questo cmdlet si applica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente scarica un file di configurazione di esempio dal sito Microsoft e lo scrive nella directory appliance dell'appliance Cloud Connector:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

La versione corrente di Cloud Connector richiede di fornire diversi parametri nel file .ini; ad esempio, parametri come gli indirizzi IP delle macchine virtuali per i componenti del connettore cloud, i nomi dei componenti, i parametri del gateway e così via.
  
Questo cmdlet, quando viene eseguito nel computer host di Cloud Connector, scarica un file di .ini di esempio con esempi di configurazione dal sito Microsoft. Il cmdlet scrive il file nella directory appliance dell'appliance Cloud Connector. La directory dell'appliance viene specificata utilizzando il cmdlet Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Export-CcConfigurationSampleFile non accetta input da pipeline. 
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

