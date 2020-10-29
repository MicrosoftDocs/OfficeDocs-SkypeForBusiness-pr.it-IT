---
title: Gestire l'app attività per l'organizzazione in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: Informazioni su come gestire l'app attività per gli utenti dell'organizzazione.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1372dd4e997d2ebc263afdb2b4b692e9b9deb8c
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790448"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app attività per l'organizzazione in Microsoft Teams

## <a name="overview-of-tasks"></a>Panoramica delle attività

L'app attività offre un'esperienza di gestione delle attività coesa a Microsoft teams, che integra le singole attività con [Microsoft](https://todo.microsoft.com/tasks/) e le attività del team alimentate da Planner in un'unica posizione. Gli utenti possono accedere alle attività come un'app sul lato sinistro di teams e come tabulazione in un canale all'interno di singoli team. **Le attività** e i **piani condivisi** nelle attività consentono agli utenti di visualizzare e gestire tutte le attività individuali e di team e di assegnare priorità al lavoro. Le attività sono disponibili in team desktop, Web e client mobili. 

> [!NOTE]
> Quando eseguiamo l'esperienza di attività nei client desktop di teams, il nome dell'app verrà inizialmente visualizzato come **Planner** per gli utenti. Il nome verrà quindi temporaneamente modificato in **attività da Planner e da fare** e in seguito sarà rinominato in **attività** . Nei client di teams mobile gli utenti vedranno sempre il nome dell'app come **attività** . Potrebbe essere necessario un breve ritardo nella disponibilità dell'esperienza per dispositivi mobili dopo l'esperienza Desktop disponibile.

   ![Screenshot della visualizzazione elenco delle attività nell'elenco Teams](media/manage-tasks-app-tasks.png)

Per le organizzazioni che vogliono semplificare la gestione delle attività per gli operatori di I Firstline, le attività includono anche funzionalità che consentono di indirizzare, pubblicare e tenere traccia delle attività in scala tra i dipendenti di I FIRSTLINE. Ad esempio, la leadership aziendale e regionale può creare e pubblicare elenchi di attività mirati a posizioni rilevanti, come specifici negozi al dettaglio, e tenere traccia dello stato di avanzamento dei report in tempo reale. I responsabili possono assegnare attività al proprio personale e dirigere le attività all'interno delle rispettive posizioni e i dipendenti di I FIRSTLINE hanno un elenco prioritario delle attività assegnate in un dispositivo mobile o desktop. Per abilitare la [pubblicazione delle attività](#task-publishing), è necessario configurare prima di tutto una gerarchia di destinazione del team per l'organizzazione, che definisce il modo in cui tutti i team della gerarchia sono correlati tra loro.

## <a name="what-you-need-to-know-about-tasks"></a>Informazioni utili sulle attività

Le attività sono disponibili come app e come tabulazione in un canale. Tieni presente che l'app include sia singole attività da eseguire che attività del team da Planner, mentre la scheda Mostra solo le attività del team.

Con le attività, gli utenti ottengono un'esperienza desktop, Web e per dispositivi mobili. Se le attività sono installate nel client desktop teams, gli utenti potranno vederlo anche nei client Web e mobile di teams. L'eccezione è gli utenti guest. È importante sapere che gli utenti possono accedere alle attività solo come app dal client teams mobile. Gli utenti vedranno le schede attività in entrambi i client desktop e Web teams.

**Attività personali Mostra le** singole attività di un utente. I **piani condivisi** mostrano le attività a cui l'intero team sta lavorando e include tutti gli elenchi attività aggiunti come scheda attività a un canale. Tenere presente quanto segue:

- Gli elenchi di attività creati dall'utente nell'app attività verranno visualizzati anche per eseguire i client per l'utente. Analogamente, gli elenchi di attività creati da un utente in to do verranno **visualizzati nelle attività in attività** per l'utente. Lo stesso vale per le singole attività.

- Tutte le schede attività aggiunte a un canale verranno visualizzate anche nei client Planner. Quando un utente crea un piano in Planner, il piano non viene visualizzato nell'app attività o Planner, a meno che non venga aggiunto come scheda a un canale. Quando un utente aggiunge una nuova scheda attività, può creare un nuovo elenco o pianificare o sceglierne uno esistente.

## <a name="set-up-tasks"></a>Configurare le attività

> [!IMPORTANT]
> Le impostazioni e i criteri configurati per Planner verranno applicati anche alle attività.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Abilitare o disabilitare le attività dell'organizzazione

Le attività sono abilitate per impostazione predefinita per tutti gli utenti di team dell'organizzazione. Puoi disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps** .
2. Nell'elenco delle app eseguire una delle operazioni seguenti:

    - Per disattivare le attività per l'organizzazione, cercare l'app attività, selezionarla e quindi fare clic su **blocca** .
    - Per attivare le attività per l'organizzazione, cercare l'app attività, selezionarla e quindi fare clic su **Consenti** .

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Abilitare o disabilitare le attività per utenti specifici dell'organizzazione

Per consentire o bloccare gli utenti specifici dell'organizzazione dall'uso delle attività, verificare che le attività siano attivate per l'organizzazione nella pagina [Gestisci app](manage-apps.md) e quindi creare un criterio di autorizzazione dell'app personalizzato e assegnarlo a tali utenti. Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Usare i criteri di configurazione dell'app per aggiungere attività ai team

I criteri di configurazione delle app consentono di personalizzare i team per evidenziare le app più importanti per gli utenti dell'organizzazione. Le app imposte in un criterio sono bloccate alla barra dell'app &mdash; la barra sul lato del client desktop teams e nella parte inferiore dei client per dispositivi mobili in &mdash; cui gli utenti possono accedervi in modo rapido e semplice.

Per aggiungere l'app attività per gli utenti, è possibile modificare il criterio globale (org-Wide default) o creare e assegnare criteri di configurazione dell'app personalizzati. Per altre informazioni, Vedi [gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>Le attività personali di un utente sono visibili se l'utente ha una licenza per Exchange Online

Se non si vuole che un utente veda **le attività personali** , è possibile nasconderlo. A questo scopo, [Rimuovi la licenza di Exchange Online dell'utente](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users). È importante sapere che dopo aver rimosso una licenza di Exchange Online, l'utente non ha più accesso alla propria cassetta postale.  I dati delle cassette postali vengono conservati per 30 giorni, dopodiché i dati verranno rimossi e non possono essere recuperati, a meno che la cassetta postale non venga inserita in un blocco sul [posto o in un blocco per controversia legale](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds).

Non è consigliabile per gli Information Worker, ma potrebbero esserci alcuni scenari in cui potrebbe essere applicabile, ad esempio per gli operatori di I FIRSTLINE che non dipendono dalla posta elettronica.

## <a name="task-publishing"></a>Pubblicazione delle attività

Con la pubblicazione delle attività, l'organizzazione può pubblicare elenchi di attività destinati a posizioni specifiche (Team) nell'organizzazione per definire e condividere un piano di lavoro da completare in tali posizioni.

- Gli utenti del team di pubblicazione, ad esempio i dirigenti aziendali o regionali, possono creare elenchi di attività e pubblicarli in team specifici.<br>
    ![Screenshot della pubblicazione delle attività](media/manage-tasks-app-publish.png)
- I responsabili dei team del destinatario possono esaminare gli elenchi di attività pubblicati e assegnare singole attività ai membri del team.<br>
    ![Screenshot dell'assegnazione di un'attività](media/manage-tasks-app-assign.png)
- I lavoratori di i FIRSTLINE hanno una semplice esperienza per i dispositivi mobili per visualizzare le attività assegnate. Possono allegare foto per mostrare il proprio lavoro quando necessario e contrassegnare le attività come completate.
- Gli editori e i responsabili possono visualizzare i report per visualizzare l'assegnazione e lo stato di completamento delle attività a ogni livello, inclusi per posizione (Team), elenco attività e attività singole.<br>
    ![Screenshot delle attività assegnate per dispositivi mobili](media/manage-tasks-app-reporting.png)

Gli utenti possono creare, gestire e pubblicare elenchi di attività nella scheda **elenchi pubblicati** nell'app attività. Questa scheda Mostra solo per un utente se l'organizzazione ha [configurato una gerarchia di destinazione del team](#set-up-your-team-targeting-hierarchy) e l'utente si trova in un team incluso nella gerarchia. La gerarchia determina se l'utente può pubblicare o ricevere elenchi di attività e visualizzare i report per gli elenchi ricevuti.

### <a name="example-scenario"></a>Scenario di esempio

Ecco un esempio di come funziona la pubblicazione delle attività.

Contoso sta implementando una nuova promozione per l'asporto e la consegna di prodotti alimentari. Per mantenere un'esperienza di marca coerente, è necessario coordinare l'esecuzione costante dell'implementazione in più posizioni nello Store di 300.

Il team di marketing condivide i dettagli della promozione e il relativo elenco di attività con il responsabile delle comunicazioni al dettaglio. Il responsabile delle comunicazioni al dettaglio, che funge da Gatekeeper per gli Store, esamina le informazioni, crea un elenco di attività per la promozione e quindi crea un'attività per ogni unità di lavoro che deve essere eseguita da ognuno degli archivi interessati. Quando l'elenco attività è completo, deve selezionare gli archivi che devono completare il lavoro. In questo caso, la promozione si applica solo agli Store degli Stati Uniti che hanno un ristorante in-Store. In attività filtra l'elenco di negozi in base all'attributo ristorante in-Store, seleziona le posizioni corrispondenti degli Stati Uniti nella gerarchia e quindi pubblica l'elenco attività in tali negozi.

I responsabili dello Store in ogni posizione ricevono una copia delle attività pubblicate e assegnano tali attività ai membri del team. I responsabili possono usare l'esperienza delle attività per comprendere tutto il lavoro necessario in tutti i loro Store. Possono anche usare i filtri disponibili per concentrarsi su un set di lavoro specifico, ad esempio il lavoro dovuto oggi o il lavoro in una determinata area.

I lavoratori di i FIRSTLINE in ogni posizione dell'archivio hanno ora un elenco di priorità del loro lavoro in attività nel dispositivo mobile. Quando termina un'attività, la contrassegna come completata. Alcuni potrebbero anche scegliere di caricare e allegare una foto all'attività per mostrare il proprio lavoro.

La sede centrale di Contoso e i responsabili intermedi possono visualizzare i report per visualizzare l'assegnazione e lo stato di completamento delle attività in ogni negozio e nei negozi. Possono anche eseguire il drill-down fino a un'attività specifica per visualizzare lo stato in diversi punti vendita. Man mano che la data di lancio si avvicina, può individuare eventuali anomalie e archiviare i propri team in base alle esigenze. Questa visibilità consente a Contoso di migliorare l'efficienza dell'implementazione e di creare un'esperienza più coerente nei propri negozi.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configurare la gerarchia di destinazione del team

Per abilitare la pubblicazione delle attività nell'organizzazione, è necessario prima di tutto configurare lo schema di destinazione del team in a. File CSV. Lo schema definisce il modo in cui tutti i team della gerarchia sono correlati tra loro e gli attributi usati per filtrare e selezionare i team. Dopo aver creato lo schema, caricalo in teams per applicarlo alla tua organizzazione. I membri del team di pubblicazione, ad esempio il responsabile delle comunicazioni al dettaglio nello scenario di esempio, possono quindi filtrare i team per gerarchia, attributi o una combinazione di entrambi per selezionare i team pertinenti che dovrebbero ricevere gli elenchi di attività e quindi pubblicare gli elenchi di attività in tali team.

Per istruzioni su come configurare la gerarchia di destinazione del team, vedere [configurare la gerarchia di destinazione del team](set-up-your-team-hierarchy.md).

## <a name="power-automate-and-graph-api"></a>API del grafico e dell'automazione di Power

Attività supporta l'automazione di Power per le operazioni da eseguire e il grafico delle API per Planner. Per altre informazioni, vedere:

- [Panoramica delle attività di Planner e pianificazione delle API](https://docs.microsoft.com/graph/planner-concept-overview)
- [Usare Microsoft per l'uso di Power automatizzate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
