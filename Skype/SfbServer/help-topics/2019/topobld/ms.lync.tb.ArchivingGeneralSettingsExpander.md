---
title: Espansione delle impostazioni generali del server di archiviazione
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'In Generatore di topologie è possibile modificare le proprietà di un singolo server che esegue l''archiviazione facendo clic con il pulsante destro del mouse sul server che esegue Archiviazione nell''albero della console e scegliendo Azione sulla barra degli strumenti oppure facendo clic su un''attività nel riquadro Azioni e quindi scegliendo Modifica proprietà e modificando una delle opzioni seguenti:'
---

# <a name="archiving-server-general-settings-expander"></a>Espansione delle impostazioni generali del server di archiviazione
 
In Generatore di topologie è possibile modificare le proprietà di un singolo server che esegue l'archiviazione facendo clic con il pulsante destro del mouse sul server che esegue Archiviazione  nell'albero della console e scegliendo Azione sulla barra degli strumenti oppure facendo clic su un'attività nel riquadro Azioni e quindi scegliendo **Modifica** proprietà e modificando una delle opzioni seguenti:
  
- **FQDN**, per modificare il nome di dominio completo (FQDN) del server che si desidera distribuire come server che esegue il server di archiviazione.
    
- **Archivio SQL**, per modificare l'istanza di SQL Server da utilizzare per il database SQL Server di archiviazione. Se si modifica il database SQL Server di un server che esegue il server di archiviazione, sarà necessario riavviare il server che esegue il server di archiviazione per assicurarsi che le modifiche vengano applicate.
    
- **Condivisione file**, per cambiare la cartella da utilizzare per l'archivio file di archiviazione. Se si cambia la condivisione file di un server di archiviazione, sarà necessario riavviare il server di archiviazione perché la modifica abbia effetto. Sarà inoltre necessario spostare i file di conferenza precedenti nella nuova cartella della condivisione file per evitare perdite di tali file archiviati.
    
> [!NOTE]
> Per modificare i pool associati a un server che esegue il server di archiviazione, selezionare l'opzione **Modifica proprietà** per il singolo nodo di pool Front End o per il nodo Survivable Branch Appliance attualmente associato al server che esegue il server di archiviazione.
  
> [!NOTE]
> Il nodo di archiviazione include un server che esegue il server di archiviazione, se tale server è stato aggiunto in precedenza nella topologia in Generatore di topologie. È possibile modificare le proprietà di qualsiasi server che esegue il server di archiviazione nell'elenco. Tuttavia, la messaggistica istantanea o le conferenze Web (messaggistica) non possono essere archiviate finché non si configura anche il servizio per il server che esegue l'archiviazione. 
  

