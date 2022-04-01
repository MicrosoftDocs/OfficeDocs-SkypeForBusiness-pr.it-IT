---
title: Conformità alle comunicazioni con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Learning sulla conformità delle comunicazioni, parte del set di soluzioni di rischio insider, dal punto di vista Microsoft Teams (fa parte della funzionalità di conformità alle comunicazioni M365).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33a2f72307b82fa4264f264e0f98a4d0aed45ae4
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592841"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformità alle comunicazioni con Microsoft Teams

La conformità alle comunicazioni è una soluzione di rischio insider in Microsoft 365 che consente di ridurre al minimo i rischi di comunicazione consentendo di rilevare, acquisire e agire in base a messaggi inappropriati nell'organizzazione.

Per Microsoft Teams, la conformità alle comunicazioni consente di identificare i [](/microsoft-365/compliance/communication-compliance-feature-reference) tipi di contenuto inappropriato seguenti nei canali Teams, nei canali Teams privati o nelle chat 1:1 e di gruppo:

- Linguaggio offensivo, profano e molesto
- Immagini per adulti, racy e gory
- Condivisione di informazioni riservate

Per altre informazioni sulla conformità delle comunicazioni e su come configurare i criteri per l'organizzazione, vedere [Conformità delle comunicazioni in Microsoft 365](/microsoft-365/compliance/communication-compliance). Per informazioni sulle sottoscrizioni Microsoft 365 che includono la conformità alle comunicazioni, vedere [Soluzioni di rischio Insider](/microsoft-365/compliance/insider-risk-solution-overview#communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Come usare la conformità alle comunicazioni in Microsoft Teams

La conformità e la Microsoft Teams comunicazioni sono strettamente integrate e consentono di ridurre al minimo i rischi di comunicazione nell'organizzazione. Dopo aver configurato i primi criteri di conformità per le comunicazioni, è possibile gestire attivamente i messaggi Microsoft Teams inappropriati e il contenuto contrassegnati automaticamente negli avvisi.

### <a name="getting-started"></a>Introduzione

Introduzione alla conformità delle comunicazioni in Microsoft Teams inizia con la pianificazione e [](/microsoft-365/compliance/communication-compliance-plan) la creazione di criteri predefiniti o personalizzati per identificare le attività degli utenti inappropriati nei canali Teams o nei gruppi 1:1. Tenere presente che è necessario [configurare alcune autorizzazioni](/microsoft-365/compliance/communication-compliance-configure) e prerequisiti di base nell'ambito del processo di configurazione.

Teams amministratori possono configurare i criteri di conformità delle comunicazioni ai livelli seguenti:

- **Livello utente**: i criteri di questo livello si applicano a un singolo Teams utente o possono essere applicati a Teams utenti dell'organizzazione. Questi criteri riguardano i messaggi che questi utenti possono inviare in chat 1:1 o di gruppo. Le comunicazioni chat per gli utenti vengono monitorate automaticamente in Microsoft Teams in cui gli utenti sono membri.
- **Teams livello**: i criteri di questo livello si applicano a un canale Microsoft Teams, incluso un canale privato. Questi criteri riguardano solo i messaggi inviati nel Teams canale.

### <a name="report-a-concern-in-microsoft-teams"></a>Segnalare un problema in Microsoft Teams

*L'opzione Segnala un* problema nei Teams messaggi è abilitata per impostazione predefinita e può essere controllata tramite i criteri di messaggistica Teams messaggistica nell'Teams [di amministrazione.](/microsoftteams/manage-teams-in-modern-portal) In questo modo gli utenti dell'organizzazione possono inviare messaggi inappropriati per la revisione da parte dei revisori della conformità delle comunicazioni per i criteri. Per altre informazioni sui messaggi segnalati dall'utente nella conformità alle comunicazioni, vedere [Criteri di conformità delle comunicazioni](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy).

![Segnala un menu di interesse.](./media/communication-compliance-report-a-concern-full-menu.png)

Dopo aver inviato il messaggio per la revisione, l'utente riceve una conferma dell'invio in Microsoft Teams. Gli altri partecipanti alla chat non vedono questa notifica.

![Segnalare una conferma di preoccupazione.](./media/communication-compliance-report-a-concern.png)

Gli utenti dell'organizzazione ottengono automaticamente i criteri globali a meno che non si creino e assegnino criteri personalizzati. Modificare le impostazioni nei criteri globali oppure creare e assegnare uno o più criteri personalizzati per attivare o disattivare questa caratteristica. Per altre informazioni, vedere [Gestire i criteri di messaggistica in Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Agire in base ai messaggi inappropriati Microsoft Teams

Dopo aver configurato i criteri e aver ricevuto avvisi di conformità alle comunicazioni per i messaggi Microsoft Teams, è il momento che i revisori della conformità dell'organizzazione agitino in base a questi messaggi. Verranno inclusi anche i messaggi segnalati dall'utente, se abilitati per l'organizzazione. I revisori possono aiutare a proteggere l'organizzazione esaminando gli avvisi di conformità alle comunicazioni e rimuovendo i messaggi contrassegnati dalla visualizzazione Microsoft Teams.

![Rimuovere un messaggio in Teams.](./media/communication-compliance-remove-teams-message.png)

I messaggi e i contenuti rimossi vengono sostituiti con notifiche per gli utenti che spiegano che il messaggio o il contenuto è stato rimosso e quali criteri sono applicabili alla rimozione. Il mittente del messaggio o del contenuto rimosso viene inoltre informato dello stato di rimozione e fornito con il contenuto originale del messaggio per il contesto relativo alla rimozione. Il mittente può anche visualizzare la condizione specifica dei criteri applicabile alla rimozione del messaggio.

Esempio di suggerimento per i criteri visualizzato dal mittente:

![Suggerimento per i criteri per il mittente.](./media/communication-compliance-warning-1.png)

Esempio di notifica dei criteri visualizzata dal mittente:

![Informazioni sulle condizioni dei criteri per il mittente.](./media/communication-compliance-warning-2.png)

Esempio di suggerimento per i criteri visualizzato dal destinatario:

![Suggerimento per i criteri per il destinatario.](./media/communication-compliance-warning-3.png)