---
title: Considerazioni sulla migrazione di Skype room System
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
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente con più versioni di Skype for Business Server e Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805786"
---
# <a name="skype-room-system-migration-considerations"></a>Considerazioni sulla migrazione di Skype room System
 
Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente con più versioni di Skype for Business Server e Lync Server.
  
## <a name="migration-considerations"></a>Considerazioni sulla migrazione

In questa sezione vengono fornite indicazioni per la distribuzione di Skype room System in un ambiente multi-pool che include diverse versioni di Skype for Business Server o Lync Server. 
  
Il componente User Replicator (UR) in Lync Server Ottiene gli oggetti utente da Active Directory e li inserisce nel database di SQL Server back-end di Lync Server. Solo l'UR in Lync Server 2013 è a conoscenza degli oggetti del sistema in sala Skype. L'UR nelle versioni precedenti di Lync Server e Office Communications Server non rileva gli attributi di Active Directory che designano gli oggetti di LRS e pertanto non li ha informati. 
  
Se un account di sistema di Skype room cerca di accedere a Lync e esegue l'individuazione automatica in base al record SRV o a un record DNS, e se tali account puntano a una versione precedente di Lync Server o Office Communications Server, LRS riceverà una risposta di 404 non trovata dal pool legacy. Il pool legacy non sarà in grado di reindirizzare Skype room System al relativo pool Lync Server 2013 Home. 
  
È possibile risolvere il problema con le opzioni seguenti: 
  
- Posizionare il record SRV di individuazione automatica (_sipinternaltls. _tcp. contoso. com) nel pool di Lync Server 2013.
    
- Se la prima opzione non è possibile, è necessario configurare manualmente LRS e fornire l'indirizzo del pool di Lync Server 2013 direttamente configurarlo nell'applicazione console del sistema Skype room. 
    
- Se il sistema di Skype Room è distribuito all'esterno della rete aziendale e un server perimetrale di Lync è stato distribuito e configurato in modo da puntare a un pool o a un Director legacy, è necessario un sito server perimetrale secondario, che punta al pool di Lync Server 2013. Per ulteriori informazioni sulla distribuzione di un server perimetrale secondario, vedere la documentazione relativa alla distribuzione di server perimetrali. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilità dei sistemi Skype room con un pool Lync Server 2010

Durante la migrazione, se un utente che si trova in un pool di Lync Server 2010 pianifica una riunione e invita l'account del sistema di chat room Skype, il client del sistema della sala Skype avrà una funzionalità limitata durante la riunione. 
  
Quando il client del sistema Skype room si unisce a una conferenza telefonica pianificata che è stata organizzata da un utente ospitato in Lync Server 2010, Skype room System ha le seguenti limitazioni in-meeting: 
  
- Skype room System non è in grado di visualizzare la raccolta video multi-view.
    
- Se il client del sistema Skype Room è il relatore, non è in grado di applicare il blocco video ai partecipanti.
    
- Skype room System non è in grado di visualizzare la risoluzione video 1080p (in ingresso o in uscita), anche se i criteri di conferenza di Lync Server 2013 lo consentono, a causa delle operazioni seguenti: 
    
  - Lync Server 2010 non supporta la risoluzione 1080p.
    
  - Skype room System è sempre limitato dai criteri di conferenza dell'organizzatore per la risoluzione video. Pertanto, anche se il pool Lync 2010 supporta la risoluzione 720p, Skype room System non sarà in grado di trarre vantaggio dalla risoluzione 720p, purché il criterio dell'organizzatore non lo supporti. 
    
- I client Lync 2013 rilevano la presenza di LRS nella sala riunioni e si disattivano automaticamente per evitare l'eco nella sala riunioni fisica. Questa funzionalità non funziona nelle riunioni ospitate in Lync Server 2010.
    
- Sono presenti limitazioni sulle prestazioni di condivisione del desktop per le riunioni ospitate in Lync Server 2010.
    
- Gli utenti non saranno in grado di partecipare a riunioni private (limitate) ospitate su Lync 2010 con Skype room System.
    

