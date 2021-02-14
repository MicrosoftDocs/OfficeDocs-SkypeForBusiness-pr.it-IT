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
description: 'È possibile spostare gli utenti nella nuova distribuzione di Skype for Business Server 2019 utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione senza problemi a Skype for Business Server 2019. Per informazioni dettagliate sui prerequisiti per il completamento delle procedure descritte in questo argomento, vedere Configure clients for migration. Per la procedura dettagliata sullo spostamento degli utenti, vedere Phase 4: Move test users to the pilot pool.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753714"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Spostare gli utenti rimanenti in Skype for Business Server 2019

È possibile spostare gli utenti nella nuova distribuzione di Skype for Business Server 2019 utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione senza problemi a Skype for Business Server 2019. Per informazioni dettagliate sui prerequisiti per il completamento delle procedure descritte in questo argomento, vedere [Configure clients for migration.](configure-clients-for-migration.md) Per la procedura dettagliata sullo spostamento degli utenti, vedere [Phase 4: Move test users to the pilot pool.](phase-4-move-test-users-to-the-pilot-pool.md)
  
> [!IMPORTANT]
> Non è possibile utilizzare lo snap-in Utenti e computer di Active Directory o gli strumenti di amministrazione legacy per spostare gli utenti dall'ambiente legacy a Skype for Business Server 2019. 
  
Quando si sposta un utente in un pool di Skype for Business Server 2019, i dati per l'utente vengono spostati nel database back-end associato al nuovo pool. 
  
> [!IMPORTANT]
> In questi dati sono incluse le riunioni attive create dall'utente legacy. Ad esempio, se un utente  legacy ha configurato una conferenza riunione, tale conferenza sarà ancora disponibile nel nuovo pool di Skype for Business Server 2019 dopo che l'utente è stato spostato. I dettagli per l'accesso alla riunione continueranno a essere gli stessi URLe ID conferenza. L'unica differenza è che la conferenza è ora ospitata nel pool di Skype for Business Server 2019 e non nel pool legacy. 
  
> [!NOTE]
> Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time. Le nuove funzionalità degli utenti saranno disponibili per gli utenti solo quando eseguono l'aggiornamento al nuovo software client. 
  
### <a name="post-migration-task"></a>Attività post-migrazione

1. Dopo aver spostato gli utenti, verificare i criteri di conferenza loro assegnati. 
    
2. Per garantire che le riunioni organizzate da utenti ospitati su Skype for Business Server 2019 funzionino senza problemi con gli utenti federati ospitati nell'installazione legacy, i criteri di conferenza assegnati agli utenti migrati devono consentire ai partecipanti anonimi.
    
3. I criteri di conferenza  che consentono ai partecipanti anonimi di invitare utenti anonimi selezionati nel Pannello di controllo di Skype for Business Server 2019 e **hanno AllowAnonymousParticipantsInMeetings** impostato su **True** nell'output del cmdlet **Get-CsConferencingPolicy** in Skype for Business Server Management Shell. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

