---
title: Espansione delle impostazioni generali del server di archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: "In Generatore di topologie è possibile modificare le proprietà di un singolo server che esegue l'archiviazione facendo clic con il pulsante destro del mouse sul server che esegue l'archiviazione nell'albero della console e facendo clic su azione sulla barra degli strumenti oppure facendo clic su un'attività nel riquadro azioni e quindi facendo clic su Modifica proprietà e modificando una delle opzioni seguenti:"
ms.openlocfilehash: 091f6f9b83c6127975654c32a81782621f7af70d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803396"
---
# <a name="archiving-server-general-settings-expander"></a>Espansione delle impostazioni generali del server di archiviazione
 
In Generatore di topologie è possibile modificare le proprietà di un singolo server che esegue l'archiviazione facendo clic con il pulsante destro del mouse sul server che esegue l'archiviazione nell'albero della console e facendo clic su **azione** sulla barra degli strumenti oppure facendo clic su un'attività nel riquadro azioni e quindi facendo clic su **modifica proprietà** e modificando una delle opzioni seguenti:
  
- **FQDN**, per modificare il nome di dominio completo (FQDN) del server che si desidera distribuire come server che esegue il server di archiviazione.
    
- **Archivio SQL**, per modificare l'istanza di SQL Server da utilizzare per il database SQL Server di archiviazione. Se si modifica il database SQL Server di un server che esegue il server di archiviazione, sarà necessario riavviare il server che esegue il server di archiviazione per assicurarsi che le modifiche vengano applicate.
    
- **Condivisione file**, per cambiare la cartella da utilizzare per l'archivio file di archiviazione. Se si cambia la condivisione file di un server di archiviazione, sarà necessario riavviare il server di archiviazione perché la modifica abbia effetto. Sarà inoltre necessario spostare i file di conferenza precedenti nella nuova cartella della condivisione file per evitare perdite di tali file archiviati.
    
> [!NOTE]
> Per modificare i pool associati a un server che esegue il server di archiviazione, selezionare l'opzione **Modifica proprietà** per il singolo nodo di pool Front End o per il nodo Survivable Branch Appliance attualmente associato al server che esegue il server di archiviazione.
  
> [!NOTE]
> Il nodo di archiviazione include un server che esegue il server di archiviazione, se tale server è stato aggiunto in precedenza nella topologia in Generatore di topologie. È possibile modificare le proprietà di qualsiasi server che esegue il server di archiviazione nell'elenco. Tuttavia, la messaggistica istantanea o le conferenze Web (messaggistica) non possono essere archiviate fino a quando non si configura anche il servizio per il server che esegue l'archiviazione. 
  

