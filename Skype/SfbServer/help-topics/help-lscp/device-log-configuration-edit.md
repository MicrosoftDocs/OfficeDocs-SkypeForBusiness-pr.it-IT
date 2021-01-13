---
title: Modifica della configurazione del Registro dispositivi
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Nella pagina di modifica delle impostazioni del log è possibile aggiungere una configurazione del log del dispositivo che determina la dimensione massima della cache del log, la dimensione massima del file di log o l'intervallo di tempo per cui un file di log viene conservato prima di essere eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.
ms.openlocfilehash: 694729b74209715bd87bed0c3bd59d80f31fff59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807316"
---
# <a name="device-log-configuration-edit"></a>Configurazione dei log del dispositivo: modifica
 
Nella pagina di **** modifica delle impostazioni del log è possibile aggiungere una configurazione del log del dispositivo che determina la dimensione massima della cache del log, la dimensione massima del file di log o l'intervallo di tempo per cui un file di log viene conservato prima di essere eliminato. È possibile modificare queste impostazioni in base ai requisiti dell'organizzazione.
  
> [!CAUTION]
> L'eliminazione dei file comporta la rimozione permanente dal file system. Dopo l'eliminazione di un file non sarà possibile recuperarlo. 
  
## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina di **** modifica delle impostazioni del log è possibile eseguire le attività seguenti:
  
- Aggiungere una configurazione del log del dispositivo a livello globale o per un sito specifico.
    
- Modificare le opzioni per una configurazione del log del dispositivo esistente.
    
## <a name="ui-reference"></a>Riferimenti UI

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.
  
- **Ambito** Identifica l'ambito (globale o sito) della configurazione del registro dei dispositivi.
    
- **Nome** È possibile aggiungere o modificare il nome della configurazione del registro dei dispositivi.
    
- **Dimensioni massime file (byte)** È possibile specificare le dimensioni massime che un file di registro può diventare prima che venga eliminato. Il valore predefinito è 1.024.000 byte (1 MB).
    
- **Dimensioni massime della cache (byte)** È possibile specificare la quantità massima di informazioni (in byte) che possono essere conservate nella cache dei file di registro prima che la cache debba essere cancellata e che i dati vengano scritti in un file di registro. Il valore predefinito è 512.000 byte (0,5 MB).
    
- **Minuti per svuotare la cache (1-60)** È possibile specificare la frequenza con cui le informazioni archiviate nella cache dei file di registro vengono scritte nel file di registro effettivo. Dopo la registrazione dei dati, la cache viene svuotata. Il valore predefinito è 5 minuti.
    
- **Giorni per mantenere i file di registro (1-365)** È possibile specificare il numero di giorni in cui i file di registro vengono mantenuti prima che vengano eliminati. Il valore predefinito è 10 giorni.
    
## <a name="see-also"></a>Vedere anche

[Configurazione dei log del dispositivo](device-log-configuration.md)
