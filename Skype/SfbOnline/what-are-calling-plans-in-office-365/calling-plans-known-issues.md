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
description: Informazioni sui problemi noti relativi al piano per le chiamate PSTN e sulle relative funzioni.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220736"
---
# <a name="calling-plans-known-issues"></a>Problemi noti relativi ai piani di chiamata

I Piani per chiamate sono una nuova funzionalità disponibile in Skype for Business online. Di seguito sono riportati gli attuali problemi che vengono monitorati e esaminati attivamente. Saranno potenzialmente risolti quando la caratteristica verrà aggiornata nelle build future.
  
## <a name="calling-plans-known-issues"></a>Problemi noti relativi ai piani di chiamata

|**Problema noto**|**Commenti**|
|:-----|:-----|
|La transizione dalle licenze di Anteprima tecnica alle licenze di produzione per i Piani per chiamate non aggiorna automaticamente la licenza.  <br/> |Acquistare prima le nuove licenze in modo che siano pronte per essere assegnate agli utenti. Rimuovere la licenza promozionale (Anteprima tecnica)  da un  utente, quindi assegnare IMMEDIATAMENTE all'utente le nuove licenze per il Piano per chiamate nazionali e/o Per chiamate nazionali e internazionali.  <br/> Se si rimuovono e si aggiungono licenze per più utenti, è estremamente importante rimuovere le  licenze da tutti gli utenti che usano Windows PowerShell e quindi assegnare IMMEDIATAMENTE le licenze per tutti gli utenti usando Windows PowerShell. In questo modo si ha la sicurezza che non si verificano interruzioni del servizio durante la gestione di volumi elevati di assegnazioni di licenze utente. Per script PowerShell di esempio, vedi [Assegnare le licenze di Skype for Business e Microsoft Teams.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Nota:** Se si usa la connettività PSTN locale per utenti ibridi, *è* necessario assegnare solo una **licenza Sistema** telefonico. NON è **consigliabile** assegnare anche un piano per le chiamate vocali. Tuttavia, se si abilitano i Piani per chiamate in Microsoft 365 o Office 365 per gli utenti di Microsoft 365 o Office 365, è comunque necessario assegnare **a** tali utenti una licenza per un Piano per chiamate nazionali o Internazionali.  Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Se è necessario ottenere più numeri di telefono, contattare il supporto per i prodotti per le [aziende - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Argomenti correlati
[Domande comuni sul trasferimento dei numeri di telefono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
