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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Il cmdlet Export-CcConfigurationSampleFile esporta un file di configurazione di esempio in Skype for Business Cloud Connector Edition (INI) nella directory appliance di un appliance di connessione cloud. È possibile modificare e rinominare il file da usare per la distribuzione.
ms.openlocfilehash: b62d5d7ffa9e8f10aeae509201c5aa0a1e7fa0a4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003426"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Il cmdlet Export-CcConfigurationSampleFile esporta un file di configurazione di esempio in Skype for Business Cloud Connector Edition (INI) nella directory appliance di un appliance di connessione cloud. È possibile modificare e rinominare il file da usare per la distribuzione.
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente Scarica un file di configurazione di esempio dal sito Microsoft e lo scrive nella directory appliance dell'accessorio Cloud Connector:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

La versione corrente di Cloud Connector richiede di specificare diversi parametri nel file ini; ad esempio, parametri come gli indirizzi IP delle macchine virtuali per i componenti del connettore Cloud, i nomi dei componenti, i parametri del gateway e così via.
  
Questo cmdlet, quando viene eseguito nel computer host di Cloud Connector, Scarica un file ini sample con esempi di configurazione dal sito Microsoft. Il cmdlet scrive il file nella directory appliance dell'accessorio Cloud Connector. La directory Appliance viene specificata usando il cmdlet Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Export-CcConfigurationSampleFile non accetta l'input da pipeline. 
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

