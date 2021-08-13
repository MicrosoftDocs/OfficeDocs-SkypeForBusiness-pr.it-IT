---
title: Spostare gli utenti restanti
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'È possibile spostare gli utenti nella nuova distribuzione Skype for Business Server 2019 utilizzando Skype for Business Server Pannello di controllo o Skype for Business Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione graduale a Skype for Business Server 2019. Per informazioni dettagliate sui prerequisiti per il completamento delle procedure descritte in questo argomento, vedere Configure clients for migration. Per la procedura dettagliata sullo spostamento degli utenti, vedere Phase 4: Move test users to the pilot pool.'
ms.openlocfilehash: a2742acf32899aca71c28da733c723640a8c1e9200f26f793a918eac04714f15
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300632"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Spostare gli utenti rimanenti Skype for Business Server 2019

È possibile spostare gli utenti nella nuova distribuzione Skype for Business Server 2019 utilizzando Skype for Business Server Pannello di controllo o Skype for Business Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione graduale a Skype for Business Server 2019. Per informazioni dettagliate sui prerequisiti per il completamento delle procedure descritte in questo argomento, vedere [Configure clients for migration](configure-clients-for-migration.md). Per la procedura dettagliata sullo spostamento degli utenti, vedere [Phase 4: Move test users to the pilot pool.](phase-4-move-test-users-to-the-pilot-pool.md)
  
> [!IMPORTANT]
> Non è possibile utilizzare lo snap-in Utenti e computer di Active Directory o gli strumenti di amministrazione legacy per spostare gli utenti dall'ambiente legacy Skype for Business Server 2019. 
  
Quando si sposta un utente in un pool di Skype for Business Server 2019, i dati per l'utente vengono spostati nel database back-end associato al nuovo pool. 
  
> [!IMPORTANT]
> In questi dati sono incluse le riunioni attive create dall'utente legacy. Ad esempio, se un utente  legacy ha configurato una conferenza riunione, tale conferenza sarà ancora disponibile nel nuovo pool di Skype for Business Server 2019 dopo lo spostamento dell'utente. I dettagli per l'accesso alla riunione continueranno a essere gli stessi URLe ID conferenza. L'unica differenza è che la conferenza è ora ospitata nel pool Skype for Business Server 2019 e non nel pool legacy. 
  
> [!NOTE]
> L'homing degli utenti Skype for Business Server 2019 non richiede la distribuzione di client aggiornati contemporaneamente. Le nuove funzionalità degli utenti saranno disponibili per gli utenti solo quando eseguono l'aggiornamento al nuovo software client. 
  
### <a name="post-migration-task"></a>Attività post-migrazione

1. Dopo aver spostato gli utenti, verificare i criteri di conferenza loro assegnati. 
    
2. Per garantire che le riunioni organizzate dagli utenti ospitati in Skype for Business Server 2019 funzionino senza problemi con gli utenti federati ospitati in un'installazione legacy, il criterio di conferenza assegnato agli utenti migrati deve consentire ai partecipanti anonimi.
    
3. Nei criteri di conferenza  che consentono ai partecipanti anonimi è stato selezionato Consenti ai partecipanti di invitare utenti anonimi nel Pannello di controllo di Skype for Business Server 2019 e **allowAnonymousParticipantsInMeetings** impostato su **True** nell'output del cmdlet **Get-CsConferencingPolicy** in Skype for Business Server Management Shell. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

