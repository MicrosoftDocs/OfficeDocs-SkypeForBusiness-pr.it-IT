---
title: Conformità delle comunicazioni con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Informazioni sulla conformità delle comunicazioni, parte del set di soluzioni di rischio Insider, dalla prospettiva Microsoft Teams (questo fa parte della funzionalità di conformità delle comunicazioni di M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8fa1bcc7190050fd06c15717aebf8648f94b090
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597150"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformità delle comunicazioni con Microsoft Teams

La conformità delle comunicazioni è una soluzione di rischio insider in Microsoft 365 che consente di ridurre al minimo i rischi per la comunicazione aiutandoli a rilevare, acquisire e agire su messaggi non appropriati nell'organizzazione.

Per Microsoft teams, la conformità delle comunicazioni consente di identificare i [seguenti tipi](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) di contenuto non appropriato nei canali di teams o in 1:1 e chat di gruppo:

- Linguaggio offensivo, profano e molesto
- Immagini adulte, audace e cruente
- Condivisione di informazioni riservate

>[!IMPORTANT]
>I canali privati di Microsoft teams non sono supportati dalla conformità delle comunicazioni. Le comunicazioni tramite chat inviate dagli utenti Guest agli utenti del team non vengono monitorate per contenuti non appropriati.

Per altre informazioni sulla conformità delle comunicazioni e su come configurare i criteri per l'organizzazione, vedere [conformità delle comunicazioni in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Come usare la conformità delle comunicazioni in Microsoft Teams

Conformità delle comunicazioni e Microsoft teams sono strettamente integrati e consentono di ridurre al minimo i rischi per la comunicazione nell'organizzazione. Dopo aver configurato i primi criteri di conformità delle comunicazioni, è possibile gestire attivamente i messaggi e i contenuti di Microsoft teams inappropriati che vengono contrassegnati automaticamente in avvisi.

### <a name="getting-started"></a>Introduzione

Per iniziare a usare la conformità delle comunicazioni in Microsoft teams, inizia con la [pianificazione](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) e la creazione di criteri predefiniti o personalizzati per identificare le attività degli utenti non appropriate nei canali dei team o in 1:1 e gruppi. Tieni presente che è necessario [configurare](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) alcune autorizzazioni e prerequisiti di base come parte del processo di configurazione.

Gli amministratori dei team possono configurare i criteri di conformità delle comunicazioni ai livelli seguenti:

- **Livello utente**: i criteri a questo livello si applicano a un singolo utente di teams o possono essere applicati a tutti gli utenti di Teams dell'organizzazione. Questi criteri includono i messaggi che possono essere inviati da questi utenti in 1:1 o in chat di gruppo. Le comunicazioni tramite chat per gli utenti vengono monitorate automaticamente in tutti i team di Microsoft in cui gli utenti sono membri.
- **Livello teams**: i criteri a questo livello si applicano a un canale di Microsoft Team. Questi criteri coprono i messaggi inviati solo nel canale teams.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Agire su messaggi non appropriati in Microsoft Teams

Dopo aver configurato i criteri e aver ricevuto avvisi per la conformità delle comunicazioni per i messaggi di Microsoft teams, è ora che i revisori di conformità dell'organizzazione intervengano in questi messaggi. I revisori possono aiutare a salvaguardare l'organizzazione rivedendo gli avvisi di conformità delle comunicazioni e rimuovendo i messaggi contrassegnati dalla visualizzazione in Microsoft teams.

![Rimuovere un messaggio in teams](./media/communication-compliance-remove-teams-message.png)

I messaggi rimossi e il contenuto vengono sostituiti con le notifiche per i visualizzatori che spiegano che il messaggio o il contenuto è stato rimosso e quali criteri sono applicabili alla rimozione. Al mittente del messaggio o del contenuto rimosso viene anche notificato lo stato di rimozione e viene fornito il contenuto originale del messaggio per il contesto relativo alla relativa rimozione. Il mittente può anche visualizzare la condizione di criteri specifica che si applica alla rimozione del messaggio.

Esempio di suggerimento per i criteri visualizzato dal mittente:

![Suggerimento per i criteri per il mittente](./media/communication-compliance-warning-1.png)

Esempio di notifica della condizione dei criteri visualizzata dal mittente:

![Informazioni sulle condizioni dei criteri per il mittente](./media/communication-compliance-warning-2.png)

Esempio di suggerimento per i criteri visualizzato dal destinatario:

![Suggerimento per i criteri per il destinatario](./media/communication-compliance-warning-3.png)