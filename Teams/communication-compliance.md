---
title: Conformità alle comunicazioni con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Informazioni sulla conformità alle comunicazioni, parte del set di soluzioni di rischio Insider, dal punto di vista di Microsoft Teams (fa parte della funzionalità di conformità alle comunicazioni M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328255"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformità alle comunicazioni con Microsoft Teams

La conformità alle comunicazioni è una soluzione di rischio insider in Microsoft 365 che consente di ridurre al minimo i rischi di comunicazione, consentendo di rilevare, acquisire e agire sui messaggi inappropriati nell'organizzazione.

Per Microsoft Teams, la conformità alle comunicazioni consente di identificare i seguenti [tipi](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) di contenuto inappropriato nei canali di Teams o nelle chat 1:1 e di gruppo:

- Linguaggio offensivo, profano e molesto
- Immagini di adulto, ghiacciato e gory
- Condivisione di informazioni riservate

Per altre informazioni sulla conformità alle comunicazioni e su come configurare i criteri per l'organizzazione, vedere [Conformità alle comunicazioni in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Come usare la conformità alle comunicazioni in Microsoft Teams

La conformità alle comunicazioni e Microsoft Teams sono strettamente integrate e possono contribuire a ridurre al minimo i rischi di comunicazione nell'organizzazione. Dopo aver configurato i primi criteri di conformità alle comunicazioni, è possibile gestire attivamente i messaggi e i contenuti inappropriati di Microsoft Teams contrassegnati automaticamente negli avvisi.

### <a name="getting-started"></a>Introduzione

Introduzione alla conformità alle comunicazioni [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) in Microsoft Teams inizia con la pianificazione e la creazione di criteri predefiniti o personalizzati per identificare le attività degli utenti inappropriati nei canali di Teams o in 1:1 e gruppi. Tenere presente che è necessario [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) configurare alcune autorizzazioni e prerequisiti di base durante il processo di configurazione.

Gli amministratori di Teams possono configurare i criteri di conformità alle comunicazioni ai livelli seguenti:

- **Livello utente:** i criteri a questo livello si applicano a un singolo utente di Teams o possono essere applicati a tutti gli utenti di Teams nell'organizzazione. Questi criteri riguardano i messaggi che questi utenti possono inviare in chat 1:1 o di gruppo. Le comunicazioni in chat per gli utenti vengono monitorate automaticamente in tutti i microsoft Teams di cui gli utenti sono membri.
- **Livello team:** i criteri a questo livello si applicano a un canale di Microsoft Team. Questi criteri riguardano solo i messaggi inviati nel canale di Teams.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Intervenire sui messaggi inappropriati in Microsoft Teams

Dopo aver configurato i criteri e aver ricevuto avvisi di conformità alle comunicazioni per i messaggi di Microsoft Teams, è il momento di consentire ai revisori della conformità dell'organizzazione di intervenire su questi messaggi. I revisori possono proteggere l'organizzazione esaminando gli avvisi di conformità alle comunicazioni e rimuovendo i messaggi contrassegnati dalla visualizzazione in Microsoft Teams.

![Rimuovere un messaggio in Teams](./media/communication-compliance-remove-teams-message.png)

I messaggi e i contenuti rimossi vengono sostituiti con notifiche per gli utenti che spiegano che il messaggio o il contenuto è stato rimosso e quali criteri sono applicabili alla rimozione. Il mittente del messaggio o del contenuto rimosso viene inoltre informato dello stato di rimozione e viene fornito il contenuto originale del messaggio per il contesto relativo alla rimozione. Il mittente può anche visualizzare la condizione del criterio specifica che si applica alla rimozione del messaggio.

Esempio di suggerimento per i criteri visualizzato dal mittente:

![Suggerimento per i criteri per il mittente](./media/communication-compliance-warning-1.png)

Esempio di notifica di condizione dei criteri visualizzata dal mittente:

![Informazioni sulle condizioni dei criteri per il mittente](./media/communication-compliance-warning-2.png)

Esempio di suggerimento per i criteri visualizzato dal destinatario:

![Suggerimento per i criteri per il destinatario](./media/communication-compliance-warning-3.png)
