---
title: Espansione delle impostazioni generali del server di archiviazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: "In Generatore di topologie è possibile modificare le proprietà per un singolo server che esegue il server di archiviazione, facendo clic con il pulsante destro del mouse sul server che esegue il server di archiviazione nell'albero della console e selezionando Azione sulla barra degli strumenti oppure facendo clic su un'attività nel riquadro Azioni, quindi selezionando Modifica proprietà e modificando una delle opzioni seguenti:"
ms.openlocfilehash: 2de8465be3f9a650aad3dd9b44b995a7dc6a7a67
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697871"
---
# <a name="archiving-server-general-settings-expander"></a>Espansione delle impostazioni generali del server di archiviazione
 
In Generatore di topologie è possibile modificare le proprietà per un singolo server che esegue il server di archiviazione, facendo clic con il pulsante destro del mouse sul server che esegue il server di archiviazione nell'albero della console e selezionando **Azione** sulla barra degli strumenti oppure facendo clic su un'attività nel riquadro Azioni, quindi selezionando **Modifica proprietà** e modificando una delle opzioni seguenti:
  
- **FQDN**, per modificare il nome di dominio completo (FQDN) del server che si desidera distribuire come server che esegue il server di archiviazione.
    
- **Archivio SQL**, per modificare l'istanza di SQL Server da utilizzare per il database SQL Server di archiviazione. Se si modifica il database SQL Server di un server che esegue il server di archiviazione, sarà necessario riavviare il server che esegue il server di archiviazione per assicurarsi che le modifiche vengano applicate.
    
- **Condivisione file**, per cambiare la cartella da utilizzare per l'archivio file di archiviazione. Se si cambia la condivisione file di un server di archiviazione, sarà necessario riavviare il server di archiviazione perché la modifica abbia effetto. Sarà inoltre necessario spostare i file di conferenza precedenti nella nuova cartella della condivisione file per evitare perdite di tali file archiviati.
    
> [!NOTE]
> Per modificare i pool associati a un server che esegue il server di archiviazione, selezionare l'opzione **Modifica proprietà** per il singolo nodo di pool Front End o per il nodo Survivable Branch Appliance attualmente associato al server che esegue il server di archiviazione.
  
> [!NOTE]
> Il nodo di archiviazione include un server che esegue il server di archiviazione, se tale server è stato aggiunto in precedenza nella topologia in Generatore di topologie. È possibile modificare le proprietà di qualsiasi server che esegue il server di archiviazione nell'elenco. Tuttavia, non è possibile archiviare messaggi istantanei o messaggi di conferenze Web finché non si imposta anche il servizio per il server che esegue il server di archiviazione. 
  

