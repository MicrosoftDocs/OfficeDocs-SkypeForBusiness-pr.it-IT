---
title: Skype Considerazioni sulla migrazione del sistema sala
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente con più versioni di Skype for Business Server e Lync Server.
ms.openlocfilehash: f3a26b630873bad0d3c8585486c91c7250f452e3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769734"
---
# <a name="skype-room-system-migration-considerations"></a>Skype Considerazioni sulla migrazione del sistema sala
 
Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente con più versioni di Skype for Business Server e Lync Server.
  
## <a name="migration-considerations"></a>Considerazioni sulla migrazione

In questa sezione vengono fornite indicazioni se si distribuisce Skype Room System in un ambiente multi-pool che include diverse versioni di Skype for Business Server o Lync Server. 
  
Il componente User Replicator (UR) in Lync Server ottiene gli oggetti utente da Active Directory e li inserisce nel database di SQL Server back-end di Lync Server. Solo l'UR in Lync Server 2013 è a conoscenza Skype di sistema room. L'UR nelle versioni precedenti di Lync Server e Office Communications Server non rilevava gli attributi di Active Directory che designavano gli oggetti LRS e pertanto non ne era a conoscenza. 
  
Se un account di sistema sala Skype tenta di accedere a Lync ed esegue l'individuazione automatica in base al record SRV o al record DNS A e se tali account puntano a una versione precedente di Lync Server o Office Communications Server, LRS riceverà una risposta 404 Not Found dal pool legacy. Il pool legacy non sarà in grado di reindirizzare Skype room al pool principale di Lync Server 2013. 
  
È possibile risolvere il problema con le opzioni seguenti: 
  
- Puntare il record SRV di individuazione automatica (_sipinternaltls._tcp.contoso.com) al pool di Lync Server 2013.
    
- Se la prima opzione non è possibile, è necessario configurare manualmente LRS e fornire l'indirizzo del pool di Lync Server 2013 configurandolo direttamente nell'applicazione console Skype Room System. 
    
- Se Skype Room System viene distribuito all'esterno della rete aziendale e un server perimetrale Lync è stato distribuito e configurato per puntare a un pool o a un director legacy, è necessario un sito server perimetrale secondario, che punta al pool di Lync Server 2013. Per ulteriori informazioni sulla distribuzione di un server perimetrale secondario, vedere la documentazione relativa alla distribuzione del server perimetrale. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype Interoperabilità del sistema sala con un pool di Lync Server 2010

Durante la migrazione, se un utente che si trova in un pool di Lync Server 2010 pianifica una riunione e invita l'account di sistema sala Skype, il client di sistema sala Skype avrà funzionalità limitate durante la partecipazione alla riunione. 
  
Quando il client Skype Room System partecipa a una conferenza telefonica pianificata organizzata da un utente in Lync Server 2010, Skype Room System presenta le limitazioni seguenti durante le riunioni: 
  
- Skype Room System non è in grado di visualizzare la raccolta video multi-visualizzazione.
    
- Se il Skype del sistema room è il relatore, non può applicare il blocco video ai partecipanti.
    
- Skype Il sistema sala non può visualizzare una risoluzione video di 1080p (in ingresso o in uscita), anche se il criterio di conferenza di Lync Server 2013 lo consente, a causa delle seguenti condizioni: 
    
  - Lync Server 2010 non supporta la risoluzione 1080p.
    
  - Skype Room System è sempre limitato dai criteri di conferenza dell'organizzatore per la risoluzione video. Pertanto, anche se il pool di Lync 2010 supporta la risoluzione 720p, Skype Room System non sarà in grado di sfruttare la risoluzione di 720p purché i criteri dell'organizzatore non la supportino. 
    
- I client Lync 2013 rilevano la presenza LRS nella sala riunioni e si disattivano automaticamente per evitare l'eco nella sala riunioni fisica. Questa funzionalità non funziona nelle riunioni ospitate in Lync Server 2010.
    
- Esistono limitazioni relative alle prestazioni di condivisione desktop per le riunioni ospitate in Lync Server 2010.
    
- Gli utenti non potranno partecipare a riunioni private (con restrizioni) ospitate in Lync 2010 con Skype Room System.
    

