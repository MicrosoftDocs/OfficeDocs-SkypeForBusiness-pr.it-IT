---
title: Considerazioni sulla migrazione di Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente con più versioni di Skype for Business Server e Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805786"
---
# <a name="skype-room-system-migration-considerations"></a>Considerazioni sulla migrazione di Skype Room System
 
Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente con più versioni di Skype for Business Server e Lync Server.
  
## <a name="migration-considerations"></a>Considerazioni sulla migrazione

Questa sezione fornisce indicazioni per la distribuzione di Skype Room System in un ambiente multi-pool che include diverse versioni di Skype for Business Server o Lync Server. 
  
Il componente User Replicator (UR) in Lync Server ottiene gli oggetti utente da Active Directory e li inserisce nel database back-end di Lync Server SQL Server database. Solo l'UR in Lync Server 2013 è a conoscenza degli oggetti di Skype Room System. L'UR nelle versioni precedenti di Lync Server e Office Communications Server non rileva gli attributi di Active Directory che designano gli oggetti LRS e pertanto non ne era a conoscenza. 
  
Se un account skype room system tenta di accedere a Lync ed esegue l'individuazione automatica in base al record SRV o al record A DNS, e se tali account puntano a una versione precedente di Lync Server o Office Communications Server, LRS riceverà una risposta 404 Non trovato dal pool legacy. Il pool legacy non sarà in grado di reindirizzare Skype Room System al pool principale di Lync Server 2013. 
  
È possibile risolvere il problema con le opzioni seguenti: 
  
- Puntare il record SRV di individuazione automatica (_sipinternaltls._tcp.contoso.com) al pool di Lync Server 2013.
    
- Se la prima opzione non è possibile, è necessario configurare manualmente LRS e fornire l'indirizzo del pool di Lync Server 2013 configurandolo direttamente nell'applicazione console di Skype Room System. 
    
- Se il sistema Skype Room viene distribuito all'esterno della rete aziendale e un server perimetrale Lync è stato distribuito e configurato per puntare a un pool o a un director legacy, è necessario un sito di server perimetrali secondario, che punta al pool lync server 2013. Per ulteriori informazioni sulla distribuzione di un server perimetrale secondario, vedere la documentazione relativa alla distribuzione del server perimetrale. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilità di Skype Room System con un pool di Lync Server 2010

Durante la migrazione, se un utente che si trova in un pool di Lync Server 2010 pianifica una riunione e invita l'account Skype Room System, il client Skype Room System avrà funzionalità limitate durante la partecipazione alla riunione. 
  
Quando il client Skype Room System partecipa a una conferenza telefonica pianificata organizzata da un utente in Lync Server 2010, Skype Room System presenta le seguenti limitazioni durante le riunioni: 
  
- Skype Room System non può mostrare la raccolta video multi-vista.
    
- Se il client Skype Room System è il relatore, non può applicare il blocco video ai partecipanti.
    
- Skype Room System non può mostrare una risoluzione video di 1080p (in ingresso o in uscita), anche se il criterio di conferenza di Lync Server 2013 lo consente, a causa dei seguenti: 
    
  - Lync Server 2010 non supporta la risoluzione 1080p.
    
  - Skype Room System è sempre limitato dai criteri di conferenza dell'organizzatore per la risoluzione video. Pertanto, anche se il pool di Lync 2010 supporta la risoluzione 720p, Skype Room System non sarà in grado di sfruttare la risoluzione 720p, purché i criteri dell'organizzatore non lo supportino. 
    
- I client Lync 2013 rilevano la presenza LRS nella sala riunioni e si disattivano automaticamente per evitare l'eco nella sala riunioni fisica. Questa funzionalità non funziona nelle riunioni ospitate in Lync Server 2010.
    
- Esistono limitazioni sulle prestazioni di condivisione desktop per le riunioni ospitate in Lync Server 2010.
    
- Gli utenti non potranno partecipare a riunioni private (con restrizioni) ospitate in Lync 2010 con Skype Room System.
    

