---
title: Spostare gli utenti rimanenti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Puoi trasferire gli utenti nella nuova distribuzione di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione fluida a Skype for Business Server 2019. Per informazioni dettagliate sui prerequisiti per completare le procedure descritte in questo argomento, vedere Configurare i client per la migrazione. Per informazioni dettagliate sullo spostamento degli utenti, vedere la fase 4: spostare gli utenti del test nel pool pilota.'
ms.openlocfilehash: ac384e9f9e4aaaa534f5b646f1d847485dbb4c23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813264"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Trasferire gli utenti rimanenti in Skype for Business Server 2019

Puoi trasferire gli utenti nella nuova distribuzione di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione fluida a Skype for Business Server 2019. Per informazioni dettagliate sui prerequisiti per completare le procedure descritte in questo argomento, vedere [configurare i client per la migrazione](configure-clients-for-migration.md). Per informazioni dettagliate sullo spostamento degli utenti, vedere [la fase 4: spostare gli utenti del test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Non è possibile usare lo snap-in utenti e computer di Active Directory o gli strumenti di amministrazione legacy per trasferire gli utenti dall'ambiente legacy a Skype for Business Server 2019. 
  
Quando si sposta un utente in un pool di Skype for Business Server 2019, i dati per l'utente vengono spostati nel database back-end associato al nuovo pool. 
  
> [!IMPORTANT]
> Sono incluse le riunioni attive create dall'utente legacy. Ad esempio, se un utente legacy ha configurato una conferenza **riunioni** , la conferenza sarà ancora disponibile nel nuovo pool di Skype for Business Server 2019 dopo lo spostamento dell'utente. I dettagli per accedere alla riunione saranno comunque lo stesso **URL conferenza e ID conferenza**. L'unica differenza è che la conferenza è ora ospitata nel pool di Skype for Business Server 2019 e non nel pool legacy. 
  
> [!NOTE]
> Gli utenti homing in Skype for Business Server 2019 non richiedono la distribuzione di client aggiornati contemporaneamente. Le nuove funzionalità saranno disponibili per gli utenti solo dopo aver eseguito l'aggiornamento al nuovo software client. 
  
### <a name="post-migration-task"></a>Attività post-migrazione

1. Dopo aver spostato gli utenti, verificare i criteri di conferenza assegnati. 
    
2. Per fare in modo che le riunioni organizzate dagli utenti ospitati in Skype for Business Server 2019 siano perfettamente compatibili con gli utenti federati residenti nell'installazione legacy, i criteri di conferenza assegnati agli utenti migrati dovrebbero consentire ai partecipanti anonimi.
    
3. I criteri di conferenza che consentono ai partecipanti anonimi **di consentire ai partecipanti di invitare utenti anonimi** selezionati in Skype for business server 2019 pannello di controllo e hanno **AllowAnonymousParticipantsInMeetings** impostato su **true** nell'output del cmdlet **Get-CsConferencingPolicy** in Skype for Business Server Management Shell. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

