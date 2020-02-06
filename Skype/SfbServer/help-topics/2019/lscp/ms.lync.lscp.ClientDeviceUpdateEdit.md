---
title: Modifica della configurazione del Registro dispositivi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile aggiungere una configurazione del log del dispositivo alla pagina Modifica impostazioni log che determina la dimensione massima della cache del log, la dimensione massima del file di log o l'intervallo di tempo in cui un file di log viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.
ms.openlocfilehash: f2c169038b69fbbb3e68838827a9a77d472c87e4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794525"
---
# <a name="device-log-configuration-edit"></a>Configurazione dei log del dispositivo: modifica
 
È possibile aggiungere una configurazione del log del dispositivo alla pagina **Modifica impostazioni log** che determina la dimensione massima della cache del log, la dimensione massima del file di log o l'intervallo di tempo in cui un file di log viene mantenuto prima che venga eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.
  
> [!CAUTION]
> L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo. 
  
## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Modifica impostazioni log** è possibile eseguire le attività seguenti:
  
- Aggiungere una configurazione del log dei dispositivi a livello globale o per un determinato sito.
    
- Modificare le opzioni per una configurazione del log del dispositivo esistente.
    
## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.
  
- **Ambito** Identifica l'ambito (globale o sito) della configurazione del log dei dispositivi.
    
- **Nome** È possibile aggiungere o modificare il nome della configurazione del log dei dispositivi.
    
- **Dimensione massima del file (byte)** Puoi specificare le dimensioni massime che un file di log può diventare prima che venga eliminato. Il valore predefinito è 1.024.000 byte (1 MB).
    
- **Dimensioni massime della cache (byte)** È possibile specificare la quantità massima di informazioni (in byte) che possono essere conservate nella cache dei file di log prima che la cache sia deselezionata e i dati vengano scritti in un file di log. Il valore predefinito è 512.000 byte (0,5 MB).
    
- **Minuti per svuotare la cache (1-60)** È possibile specificare la frequenza con cui le informazioni memorizzate nella cache dei file di log vengono scritte nel file di log effettivo. Dopo aver registrato i dati, la cache viene deselezionata. Il valore predefinito è cinque minuti.
    
- **Giorni per conservare i file di log (1-365)** È possibile specificare il numero di giorni in cui i file di log vengono mantenuti prima che vengano eliminati. Il valore predefinito è 10 giorni.
    
## <a name="see-also"></a>Vedere anche

[Configurazione dei log del dispositivo](ms.lync.lscp.ClientDeviceCfgMain.md)
