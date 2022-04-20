---
title: Conformità delle comunicazioni con Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Learning sulla conformità alle comunicazioni, parte del set di soluzioni di rischio Insider, dal punto di vista Microsoft Teams (fa parte della funzionalità di conformità alle comunicazioni di M365).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 091fe5eba9d17cefc442978cb3090aaca87844d8
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922647"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformità delle comunicazioni con Microsoft Teams

Microsoft Purview Communication Compliance è una soluzione per il rischio Insider in Microsoft 365 che consente di ridurre al minimo i rischi di comunicazione, consentendo di rilevare, acquisire e agire sui messaggi inappropriati nell'organizzazione.

Per Microsoft Teams, la conformità alle comunicazioni consente di identificare i [tipi](/microsoft-365/compliance/communication-compliance-feature-reference) di contenuto non appropriati seguenti nei canali Teams, nei canali Teams privati o nelle chat 1:1 e di gruppo:

- Linguaggio offensivo, profano e molesto
- Immagini adulte, ghiacciate e gory
- Condivisione di informazioni riservate

Per altre informazioni sulla conformità alle comunicazioni e su come configurare i criteri per l'organizzazione, vedere [Informazioni sulla conformità alle comunicazioni](/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Come usare la conformità alle comunicazioni in Microsoft Teams

La conformità alle comunicazioni e le Microsoft Teams sono strettamente integrate e consentono di ridurre al minimo i rischi di comunicazione nell'organizzazione. Dopo aver configurato i criteri di conformità per le comunicazioni, è possibile gestire attivamente i messaggi di Microsoft Teams inappropriati e il contenuto contrassegnato automaticamente negli avvisi.

### <a name="getting-started"></a>Introduzione

Iniziare a usare la conformità alle comunicazioni in Microsoft Teams inizia con la [pianificazione](/microsoft-365/compliance/communication-compliance-plan) e la creazione di criteri predefiniti o personalizzati per identificare le attività utente non appropriate nei canali Teams o in 1:1 e gruppi. Tenere presente che è necessario [configurare](/microsoft-365/compliance/communication-compliance-configure) alcune autorizzazioni e prerequisiti di base nell'ambito del processo di configurazione.

Teams amministratori possono configurare i criteri di conformità delle comunicazioni ai livelli seguenti:

- **Livello utente**: i criteri a questo livello si applicano a un singolo utente Teams o a tutti Teams utenti dell'organizzazione. Questi criteri coprono i messaggi che questi utenti possono inviare in chat 1:1 o di gruppo. Le comunicazioni chat per gli utenti vengono monitorate automaticamente in tutti i Microsoft Teams in cui gli utenti sono membri.
- **Teams livello**: i criteri a questo livello si applicano a un canale Microsoft Teams, incluso un canale privato. Questi criteri coprono solo i messaggi inviati nel canale Teams.

### <a name="report-a-concern-in-microsoft-teams"></a>Segnala un problema in Microsoft Teams

>[!NOTE]
>I messaggi segnalati dall'utente inizieranno a essere disponibili per le organizzazioni con licenza per [la conformità alle comunicazioni](/microsoft-365/compliance/communication-compliance-configure#subscriptions-and-licensing) e Microsoft Teams a partire da maggio 2022. Questa funzionalità dovrebbe essere disponibile per tutte le organizzazioni con licenza entro il 31 agosto 2022.

L'opzione *Segnala un problema* in Teams messaggi è abilitata per impostazione predefinita e può essere controllata tramite criteri di messaggistica Teams [nell'interfaccia di amministrazione di Teams](/microsoftteams/manage-teams-in-modern-portal). In questo modo gli utenti dell'organizzazione possono inviare messaggi inappropriati per la revisione da parte dei revisori della conformità delle comunicazioni per i criteri. Per altre informazioni sui messaggi segnalati dall'utente nella conformità alle comunicazioni, vedere [Criteri di conformità delle comunicazioni](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy).

![Segnala un menu di preoccupazione.](./media/communication-compliance-report-a-concern-full-menu.png)

Dopo aver inviato il messaggio per la revisione, l'utente riceve una conferma dell'invio in Microsoft Teams. Gli altri partecipanti alla chat non vedono questa notifica.

![Segnala una conferma di preoccupazione.](./media/communication-compliance-report-a-concern.png)

Gli utenti dell'organizzazione ottengono automaticamente i criteri globali, a meno che non vengano creati e assegnati criteri personalizzati. Modificare le impostazioni nel criterio globale o creare e assegnare uno o più criteri personalizzati per attivare o disattivare questa caratteristica. Per altre informazioni, vedere [Gestire i criteri di messaggistica in Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Intervenire sui messaggi inappropriati in Microsoft Teams

Dopo aver configurato i criteri e aver ricevuto avvisi di conformità delle comunicazioni per i messaggi di Microsoft Teams, i revisori della conformità dell'organizzazione devono intervenire su questi messaggi. Verranno inclusi anche i messaggi segnalati dall'utente, se abilitati per l'organizzazione. I revisori possono proteggere l'organizzazione esaminando gli avvisi di conformità delle comunicazioni e rimuovendo i messaggi contrassegnati dalla visualizzazione in Microsoft Teams.

![Rimuovere un messaggio in Teams.](./media/communication-compliance-remove-teams-message.png)

I messaggi e il contenuto rimossi vengono sostituiti con notifiche per gli spettatori che spiegano che il messaggio o il contenuto è stato rimosso e quali criteri sono applicabili alla rimozione. Il mittente del messaggio o del contenuto rimosso riceve anche una notifica dello stato di rimozione e fornisce il contenuto originale del messaggio per il contesto relativo alla rimozione. Il mittente può anche visualizzare la condizione dei criteri specifici che si applica alla rimozione dei messaggi.

Esempio di suggerimento per i criteri visualizzato dal mittente:

![Suggerimento per i criteri per il mittente.](./media/communication-compliance-warning-1.png)

Esempio di notifica dei criteri visualizzata dal mittente:

![Informazioni sulla condizione dei criteri per il mittente.](./media/communication-compliance-warning-2.png)

Esempio di suggerimento per i criteri visualizzato dal destinatario:

![Suggerimento per i criteri per il destinatario.](./media/communication-compliance-warning-3.png)