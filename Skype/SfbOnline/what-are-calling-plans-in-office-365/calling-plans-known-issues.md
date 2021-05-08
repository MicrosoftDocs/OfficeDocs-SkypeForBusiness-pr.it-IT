---
title: Problemi noti relativi ai piani di chiamata
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Informazioni sui problemi noti relativi al piano chiamate per le chiamate PSTN e sulle relative attività.
ms.openlocfilehash: 9c660ee3b173f104e26816460db45c5bcf400837
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238022"
---
# <a name="calling-plans-known-issues"></a>Problemi noti relativi ai piani di chiamata

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

I piani per chiamate sono una nuova funzionalità disponibile in Skype for Business Online. Di seguito sono riportati i problemi correnti che vengono monitorati e esaminati attivamente. Potrebbero essere risolti quando la funzionalità verrà aggiornata nelle build future.
  
## <a name="calling-plans-known-issues"></a>Problemi noti relativi ai piani di chiamata

|**Problema noto**|**Commenti**|
|:-----|:-----|
|La transizione dalle licenze Tech Preview alle licenze di produzione per i piani per chiamate non aggiorna automaticamente la licenza.  <br/> |Acquista prima le nuove licenze in modo che siano pronte per essere assegnate agli utenti. Rimuovere la licenza promozionale (Tech Preview) da un  utente e quindi  assegnare immediatamente all'utente le nuove licenze per il piano per chiamate nazionali e/o nazionali e internazionali.  <br/> Se si rimuovono e si aggiungono licenze per più utenti, è estremamente importante rimuovere  le licenze da tutti gli utenti che usano Windows PowerShell e quindi assegnare immediatamente le licenze per tutti gli utenti anche usando Windows PowerShell. In questo modo si garantisce che non ci siano interruzioni del servizio durante la gestione di grandi volumi di assegnazioni di licenze utente. Per script di PowerShell di esempio, vedere [Assegnare Skype for Business e Microsoft Teams licenze.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Nota:** Se si usa la connettività PSTN locale  per gli utenti ibridi, è necessario assegnare solo **una** licenza Sistema telefonico locale. NON è **consigliabile assegnare** anche un piano per chiamate vocali. Tuttavia, se si stanno abilitando i Piani per chiamate in Microsoft 365 o Office 365 per gli utenti che si  consegnerà a Microsoft 365 o Office 365, è comunque necessario assegnare un Piano per chiamate nazionali o una licenza piano per chiamate nazionali e internazionali per tali utenti.  Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Se è necessario ottenere più numeri di telefono, contattare il [supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
