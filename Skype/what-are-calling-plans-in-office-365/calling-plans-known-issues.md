---
title: Problemi noti di piani di chiamata
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: 'Informazioni su problemi noti di piano di chiamata per Office 365 (tramite la chiamata PSTN) e operazioni su di essi. '
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a>Problemi noti di piani di chiamata

Piani di chiamata in Office 365 sono una nuova funzionalità disponibili in Skype Business online. Di seguito sono riportati i problemi correnti che vengono registrati e analizzare attivamente. Verrà risolto potenzialmente quando la caratteristica viene aggiornata in futuro build in Office 365 e Skype Business online.
  
## <a name="calling-plans-known-issues"></a>Problemi noti di piani di chiamata

|**Problemi noti**|**Commenti**|
|:-----|:-----|
|Transizione da Tech Preview licenze per le licenze di produzione per piani di chiamata non vengono aggiornati automaticamente la licenza.  <br/> |Acquistare le licenze nuove innanzitutto in modo che siano pronti per essere assegnati agli utenti. Rimuovere la licenza promozione (Tech Preview) da un utente e quindi assegnare **immediatamente** le nuove licenze **Chiamata pianificare interne** e/o **nazionali e internazionali chiamata pianificare** all'utente. <br/> Se si ha la rimozione e aggiungendo le licenze per più utenti, è estremamente importante per rimuovere tutti gli utenti utilizzando Windows PowerShell le licenze e assegnarle **immediatamente** le licenze per tutti gli utenti anche tramite Windows PowerShell. In questo modo verrà assicurarsi che non vi sia alcuna interruzione del servizio quando si gestiscono volumi elevati di assegnazione di licenze utente. Per gli script di PowerShell di esempio, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Nota:** Se si utilizza una connettività PSTN locale per gli utenti ibrida, è *solo* necessario assegnare una licenza di **Sistema telefonico** . **Non** deve inoltre assegnare una voce pianificare la chiamata. Tuttavia, se si abilita la chiamata dei piani di Office 365 per gli utenti presenti in Office 365, è necessario assegnare ancora un **Interno pianificare la chiamata** o una licenza **nazionali e internazionali la chiamata a pianificare** per tali utenti. Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Se si desidera ottenere altri numeri di telefono rispetto a quella, [contattare il supporto per i prodotti di business - della Guida di amministrazione](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Argomenti correlati
[Trasferimento di domande comuni numeri di telefono](transferring-phone-numbers-common-questions.md)

[Diversi tipi di numeri di telefono utilizzati per la chiamata dei piani](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gestire i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://go.microsoft.com/fwlink/?LinkID=692099)
