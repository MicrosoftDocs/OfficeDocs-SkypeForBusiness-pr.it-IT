---
title: Considerazioni sulla migrazione di Skype room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente che include più versioni di Skype for Business Server e Lync Server.
ms.openlocfilehash: f5da7f92c7ab947d5e6d68c19823d227f8ae3ca3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234209"
---
# <a name="skype-room-system-migration-considerations"></a>Considerazioni sulla migrazione di Skype room System
 
Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente che include più versioni di Skype for Business Server e Lync Server.
  
## <a name="migration-considerations"></a>Considerazioni sulla migrazione

Questa sezione fornisce indicazioni per la distribuzione di Skype room System in un ambiente con più pool che include versioni diverse di Skype for Business Server o Lync Server. 
  
Il componente User Replicator (UR) in Lync Server Ottiene gli oggetti utente da Active Directory e li inserisce nel database di SQL Server back-end di Lync Server. Solo l'UR in Lync Server 2013 è a conoscenza degli oggetti di sistema room Skype. L'UR nelle versioni precedenti di Lync Server e Office Communications Server non rileva gli attributi di Active Directory che designano gli oggetti LRS e quindi non ne erano a conoscenza. 
  
Se un account di sistema per Skype room cerca di accedere a Lync e esegue l'individuazione automatica in base al record SRV o al DNS un record Cerca e se questi account puntano a una versione precedente di Lync Server o Office Communications Server, LRS riceverà una risposta di 404 non trovata da  il pool legacy. Il pool legacy non sarà in grado di reindirizzare Skype room System al proprio pool di Lync Server 2013 Home. 
  
Per risolvere il problema, è possibile usare le opzioni seguenti: 
  
- Posizionare il record SRV di individuazione automatica (_sipinternaltls. _tcp. contoso. com) nel pool di Lync Server 2013.
    
- Se la prima opzione non è possibile, è necessario configurare manualmente LRS e specificare l'indirizzo del pool di Lync Server 2013, configurando direttamente l'applicazione console di Skype room System. 
    
- Se il sistema room Skype è distribuito all'esterno della rete aziendale e un Edge Server Lync è stato distribuito e configurato in modo che punti a un pool o a un amministratore legacy, è necessario un sito Edge Server secondario, che punta al pool di Lync Server 2013. Per altre informazioni sulla distribuzione di un server perimetrale secondario, vedere la documentazione sulla distribuzione di Edge Server. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interoperabilità del sistema Skype room con un pool di Lync Server 2010

Durante la migrazione, se un utente che si trova in un pool di Lync Server 2010 pianifica una riunione e invita l'account di sistema room Skype, il client di sistema room Skype avrà funzionalità limitate durante la riunione. 
  
Quando il client della sala di Skype room si unisce a una conferenza telefonica pianificata organizzata da un utente ospitato in Lync Server 2010, Skype room System ha le seguenti limitazioni per le riunioni: 
  
- Skype room System non è in grado di visualizzare la raccolta di video con visualizzazione multipla.
    
- Se il client del sistema di chat room Skype è il relatore, non può applicare il blocco video ai partecipanti.
    
- Skype room System non può visualizzare la risoluzione video 1080p (in ingresso o in uscita), anche se il criterio di conferenza di Lync Server 2013 lo consente, a causa delle operazioni seguenti: 
    
  - Lync Server 2010 non supporta la risoluzione 1080p.
    
  - Skype room System è sempre limitato dai criteri di conferenza dell'organizzatore per la risoluzione video. Pertanto, anche se il pool di Lync 2010 supporta la risoluzione 720p, Skype room System non sarà in grado di sfruttare la risoluzione 720p purché il criterio dell'organizzatore non lo supporti. 
    
- I client Lync 2013 rilevano la presenza di LRS nella sala riunioni e si riattivano automaticamente per evitare l'eco nella sala riunioni fisica. Questa caratteristica non funziona nelle riunioni ospitate in Lync Server 2010.
    
- Esistono limitazioni sulle prestazioni di condivisione desktop per le riunioni ospitate in Lync Server 2010.
    
- Gli utenti non potranno partecipare a riunioni private (con restrizioni) ospitate in Lync 2010 con Skype room System.
    

