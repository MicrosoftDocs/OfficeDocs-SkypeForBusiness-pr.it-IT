---
title: Gestire l'app elenchi per l'organizzazione
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come gestire l'app elenchi in teams per gli utenti dell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7e237ffd041c2207516b714147d555b3a1b9043
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138369"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app elenchi per l'organizzazione in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview-of-lists"></a>Panoramica degli elenchi

L'app elenchi in Microsoft teams aiuta gli utenti dell'organizzazione a tenere traccia delle informazioni, organizzare il lavoro e gestire i flussi. Con gli elenchi, gli utenti possono tenere traccia dei dati, ad esempio problemi, attività, routine, contatti, inventario, incidenti, prestiti, pazienti e altro usando Visualizzazioni, regole e avvisi personalizzabili per consentire la sincronizzazione di tutti i membri del team.

In teams gli utenti accedono agli elenchi come tabulazioni in un canale. Fare clic **+** per aprire la raccolta schede e aggiungere una nuova istanza della scheda App elenchi a un canale per iniziare. 

![Screenshot dell'app elenchi nella raccolta schede](media/lists-tab.png)

Gli utenti possono creare nuovi elenchi o aggiungere elenchi esistenti dall'interno dello stesso team o da un altro sito di SharePoint a cui hanno accesso. I nuovi elenchi possono essere creati da zero, da modelli predefiniti, in base alla struttura di un elenco esistente oppure importando dati da una cartella di lavoro di Excel. L'app elenchi è disponibile nei client desktop, Web e mobili di teams.

![Screenshot che illustra come creare un elenco nell'app elenchi](media/lists-create-list.png)

## <a name="templates"></a>Modelli

I modelli degli elenchi sono adattati a scenari comuni per il monitoraggio delle informazioni per gli utenti. Ogni modello include una struttura di elenco predefinita, layout di modulo e opzioni di formattazione sia in una visualizzazione elenco che in un livello di visualizzazione dettagli per consentire agli utenti di iniziare rapidamente. Dopo aver selezionato un modello, gli utenti possono visualizzare in anteprima l'aspetto dell'elenco, insieme ad alcuni dati di esempio. Ecco alcuni esempi di come i team dell'organizzazione possono usare i modelli predefiniti negli elenchi:

- Tenere traccia dei problemi e portarli alla chiusura usando il modello Tracker problema.
- Organizzare tutti i dettagli dell'evento con il modello di itinerario dell'evento.
- Usa il modello patients per registrare le esigenze e lo stato dei pazienti in modo che i team di assistenza sanitaria nell'organizzazione del settore sanitario possano monitorare e coordinare le cure.
- Tenere traccia dello stato delle applicazioni di prestito con il modello prestiti.

## <a name="example-scenario"></a>Scenario di esempio

Un ufficio postale locale è responsabile dell'ordinamento e della consegna della posta nel proprio quartiere. Ogni mattina, l'ufficio postale ha una riunione di team per esaminare gli obiettivi quotidiani, condividere annunci e discutere di eventi noti.

Dopo la calca, i vettori della posta prelevano la posta e iniziano il loro percorso di consegna. Si possono verificare incidenti lungo un percorso, ad esempio un incidente stradale, un problema legato al cane o una protesta sociale per i disordini. Quando i vettori di posta incontrano un incidente, usano team nei loro dispositivi mobili per registrare i dettagli degli incidenti, che vengono rilevati in un elenco nel canale del team. Tutti i membri del team, inclusi i vettori di posta elettronica nel campo, possono vedere queste informazioni e tenersi informati.

Prima di passare a teams, i vettori della posta devono tornare all'ufficio postale per completare una maschera cartacea per segnalare un incidente immesso in un foglio di calcolo di Excel. Teams offre ai vettori di posta un primo dispositivo mobile, esperienza in cui è possibile usare gli elenchi per segnalare gli incidenti nel campo Man mano che si verificano, condividere i dettagli degli incidenti con i membri del team, avere conversazioni su di essi sul canale e guidare gli incidenti alla risoluzione.

## <a name="what-you-need-to-know-about-lists"></a>Informazioni utili sugli elenchi

### <a name="lists-is-available-in-every-team-and-channel"></a>Gli elenchi sono disponibili in tutti i team e i canali

Gli elenchi sono preinstallati per tutti gli utenti dei team ed è disponibile direttamente nella raccolta schede di ogni team e canale. Ciò significa che gli utenti non devono andare nell'app store teams per installarlo.

### <a name="lists-and-sharepoint"></a>Elenchi e SharePoint

Elenca i dati archiviati nel sito del team di SharePoint Online. Per altre informazioni su come interagiscono con i team in SharePoint Online, vedere [come interagire con i team in SharePoint Online e OneDrive for business](SharePoint-OneDrive-interact.md).

Le autorizzazioni impostate in SharePoint si applicano agli elenchi creati nell'app elenchi. Per impostazione predefinita, gli elenchi ereditano le autorizzazioni dal sito a cui appartengono. Queste autorizzazioni regolano i tipi di azioni che gli utenti possono eseguire, ad esempio se possono creare o modificare elenchi. Per altre informazioni, vedere [livelli di autorizzazione in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) e [autorizzazioni utente e livelli di autorizzazione in SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).

In alcuni scenari potresti voler limitare le azioni che gli utenti possono eseguire negli elenchi. Ad esempio, una persona in un team modifica una visualizzazione elenco, che la modifica per tutti i membri del team e si vuole consentire solo al proprietario del team o a determinati membri del team di modificare le visualizzazioni elenco. Per altre informazioni, vedere [personalizzare le autorizzazioni per un elenco o una raccolta di SharePoint](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).

> [!NOTE]
> A questo punto, le autorizzazioni proprietario e membro in un team non sono collegate in alcun modo alle autorizzazioni nel sito del team che regolano il comportamento degli elenchi o dell'app elenchi. Tuttavia, in base al feedback dei clienti e all'uso, questo verrà considerato per un'iterazione futura del prodotto.  

### <a name="limitations"></a>Limitazioni

Con gli elenchi, gli utenti ottengono un'esperienza desktop, Web e per dispositivi mobili. È importante sapere che gli utenti non possono creare nuovi elenchi o aggiungere elenchi esistenti usando elenchi nel client per dispositivi mobili teams. Per visualizzare o modificare un elenco nel client di teams mobile, è prima necessario creare o aggiungere un elenco usando elenchi nel desktop o nel client Web teams.

Gli utenti dei [canali privati](private-channels.md) non possono creare o eliminare un elenco o iniziare una nuova conversazione su una voce di elenco. Possono aggiungere voci di elenco agli elenchi esistenti e rispondere a una conversazione esistente su una voce di elenco. Tieni presente che queste limitazioni si applicano solo ai canali privati.

### <a name="lists-and-the-sharepoint-app"></a>Elenchi e l'app SharePoint

Se gli utenti dell'organizzazione hanno creato elenchi usando l'app SharePoint, tali elenchi verranno spostati automaticamente in elenchi senza alcuna azione necessaria per l'utente. Per ottenere l'esperienza di integrazione di elenchi migliori e più ricchi in teams, usa l'app elenchi e Aggiungi gli elenchi esistenti.

## <a name="set-up-lists"></a>Configurare gli elenchi

### <a name="enable-or-disable-lists-in-your-organization"></a>Abilitare o disabilitare gli elenchi nell'organizzazione

Gli elenchi sono abilitati per impostazione predefinita per tutti gli utenti di team dell'organizzazione. Puoi disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps** .
2. Eseguire una delle operazioni seguenti:

    - Per disattivare gli elenchi per l'organizzazione, cercare l'app elenchi, selezionarla e quindi fare clic su **blocca**.
    - Per attivare gli elenchi per l'organizzazione, cercare l'app elenchi, selezionarla e quindi fare clic su **Consenti**.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Abilitare o disabilitare elenchi per utenti specifici dell'organizzazione

Per consentire o bloccare gli utenti specifici dell'organizzazione dall'uso degli elenchi, verificare che gli elenchi siano attivati per l'organizzazione nella pagina [Gestisci app](manage-apps.md) e quindi creare un criterio di autorizzazione dell'app personalizzato e assegnarlo a tali utenti. Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Eseguire una ricerca nel log di controllo per gli eventi di elenco

Gli elenchi sono abilitati con il controllo a livello aziendale in modo da cercare elenchi e gli eventi di voci di elenco nel log di controllo nel centro conformità & sicurezza. Per altre informazioni, vedere [eseguire la ricerca nel log di controllo nel centro conformità & sicurezza](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Per un elenco di eventi di controllo rilevanti per l'app elenchi in teams, Vedi [attività elenco SharePoint](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).

Prima di eseguire una ricerca nel log di controllo, è necessario attivare prima di tutto il controllo nel [centro conformità & sicurezza](https://protection.office.com). Tieni presente che i dati di controllo sono disponibili solo dal momento in cui hai attivato il controllo.

## <a name="power-automate-power-apps-and-graph-api"></a>Power automatizzate, Power Apps e Graph API

Gli elenchi supportano l' [automazione di Power](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) per i flussi di lavoro e le [app Power](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) per i moduli elenco. Gli sviluppatori possono usare l' [API elenchi](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) per connettere i dati dell'elenco come origine tramite Microsoft Graph.

## <a name="give-feedback-or-report-an-issue"></a>Inviare un feedback o segnalare un problema
  
Per inviare commenti e suggerimenti o segnalare un problema, fare clic su **Guida** nella parte inferiore della barra di spostamento sinistra in teams e quindi selezionare **segnala un problema**. Selezionare **elenchi**e quindi immettere il feedback o i dettagli sul problema che si sta verificando.
