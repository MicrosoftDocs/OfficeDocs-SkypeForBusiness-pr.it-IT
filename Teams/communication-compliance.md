---
title: Conformità alle comunicazioni con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Informazioni sulla conformità delle comunicazioni, parte del set di soluzioni di rischio insider, dal punto di vista di Microsoft Teams (fa parte della funzionalità di conformità alle comunicazioni M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf032669edc7255571e2501774ac0d0ee0df47d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121534"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformità alle comunicazioni con Microsoft Teams

La conformità alle comunicazioni è una soluzione di rischio insider in Microsoft 365 che consente di ridurre al minimo i rischi di comunicazione consentendo di rilevare, acquisire e agire in base a messaggi inappropriati nell'organizzazione.

Per Microsoft Teams, la conformità alle comunicazioni consente di identificare i seguenti [tipi](/microsoft-365/compliance/communication-compliance-feature-reference) di contenuto inappropriato nei canali di Teams o nelle chat 1:1 e di gruppo:

- Linguaggio offensivo, profano e molesto
- Immagini per adulti, racy e gory
- Condivisione di informazioni riservate

Per altre informazioni sulla conformità delle comunicazioni e su come configurare i criteri per l'organizzazione, vedere [Conformità alle comunicazioni in Microsoft 365.](/microsoft-365/compliance/communication-compliance)

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Come usare la conformità alle comunicazioni in Microsoft Teams

La conformità alle comunicazioni e Microsoft Teams sono strettamente integrate e consentono di ridurre al minimo i rischi di comunicazione all'interno dell'organizzazione. Dopo aver configurato i primi criteri di conformità delle comunicazioni, è possibile gestire attivamente i messaggi e il contenuto non appropriati di Microsoft Teams contrassegnati automaticamente negli avvisi.

### <a name="getting-started"></a>Introduzione

Per iniziare a usare la [](/microsoft-365/compliance/communication-compliance-plan) conformità alle comunicazioni in Microsoft Teams, si inizia con la pianificazione e la creazione di criteri predefiniti o personalizzati per identificare le attività degli utenti inappropriati nei canali di Teams o nei gruppi 1:1 e. Tenere presente che è necessario configurare [alcune](/microsoft-365/compliance/communication-compliance-configure) autorizzazioni e prerequisiti di base nell'ambito del processo di configurazione.

Gli amministratori di Teams possono configurare i criteri di conformità delle comunicazioni ai livelli seguenti:

- **Livello utente:** i criteri di questo livello si applicano a un singolo utente di Teams o possono essere applicati a tutti gli utenti di Teams dell'organizzazione. Questi criteri riguardano i messaggi che questi utenti possono inviare in chat 1:1 o di gruppo. Le comunicazioni chat per gli utenti vengono monitorate automaticamente in tutti i Microsoft Teams in cui gli utenti sono membri.
- **Livello team:** i criteri di questo livello si applicano a un canale Microsoft Team. Questi criteri riguardano solo i messaggi inviati nel canale teams.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Agire in base ai messaggi inappropriati in Microsoft Teams

Dopo aver configurato i criteri e aver ricevuto avvisi di conformità alle comunicazioni per i messaggi di Microsoft Teams, è il momento che i revisori della conformità dell'organizzazione eseempano azioni su questi messaggi. I revisori possono aiutare a proteggere l'organizzazione esaminando gli avvisi di conformità alle comunicazioni e rimuovendo i messaggi contrassegnati dalla visualizzazione in Microsoft Teams.

![Rimuovere un messaggio in Teams](./media/communication-compliance-remove-teams-message.png)

I messaggi e i contenuti rimossi vengono sostituiti con notifiche per gli utenti che spiegano che il messaggio o il contenuto è stato rimosso e quali criteri sono applicabili alla rimozione. Il mittente del messaggio o del contenuto rimosso viene inoltre informato dello stato di rimozione e fornisce il contenuto originale del messaggio per il contesto relativo alla rimozione. Il mittente può anche visualizzare la condizione specifica dei criteri applicabile alla rimozione del messaggio.

Esempio di suggerimento per i criteri visualizzato dal mittente:

![Suggerimento per i criteri per il mittente](./media/communication-compliance-warning-1.png)

Esempio di notifica delle condizioni dei criteri visualizzata dal mittente:

![Informazioni sulle condizioni dei criteri per il mittente](./media/communication-compliance-warning-2.png)

Esempio di suggerimento per i criteri visualizzato dal destinatario:

![Suggerimento per i criteri per il destinatario](./media/communication-compliance-warning-3.png)