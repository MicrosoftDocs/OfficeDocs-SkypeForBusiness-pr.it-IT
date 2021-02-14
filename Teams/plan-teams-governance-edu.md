---
title: Domande frequenti sulla governance di Microsoft Education per amministratori
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Risposte alle domande frequenti degli amministratori di gruppi di Microsoft Education che usano Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f8f8593d598901c71590cc395eb45b0bac7cf4f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812906"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Domande frequenti sulla governance di Microsoft Education per amministratori

> [!Tip]
> Guardare la sessione seguente per saperne di più sulla gestione in Microsoft Teams: [Governance, gestione e ciclo di vita in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Come si controlla la creazione di team? Temevo che gli studenti creino team inappropriati.

Per evitare nomi inappropriati o fuorvianti o semplicemente per fornire una maggiore struttura per la modalità di denominazione dei team, è possibile usare i criteri di denominazione dei gruppi di Microsoft 365 (attualmente in anteprima):

-   **Criteri di denominazione prefisso-suffisso** È possibile usare prefissi o suffissi per definire la convenzione di denominazione dei team (gruppi), ad esempio **GRP_US_My Group_Engineering.** I prefissi e suffissi possono essere stringhe fisse o attributi utente (ad esempio **[Department]**) che vengono aggiunti al nome in base all'utente che crea il team.
-   **Parole bloccate personalizzate** È possibile caricare un set di parole che gli utenti di un'organizzazione specifica non possono usare nei nomi dei team che creano. Ad esempio, è possibile bloccare l'uso dei termini **CEO,** Retribuzioni e **Risorse** umane nei nomi dei team per i gruppi a cui non si applicano.
-   **Classificazione** È possibile creare classificazioni che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Microsoft 365. 

> [!IMPORTANT]
> L'uso dei criteri di denominazione dei gruppi di Microsoft 365 richiede licenze di Azure Active Directory Premium P1 o di Azure AD Basic EDU per ogni utente univoco membro di uno o più gruppi di Microsoft 365.

Per istruzioni dettagliate, vedere Criteri di denominazione [dei gruppi di Office.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Se i team vengono creati automaticamente usando l'input di un altro sistema, ad esempio School Data Sync, verificare che i dati di input siano conforme ai criteri di denominazione configurati; in caso contrario, la creazione del team non riuscirà.

## <a name="can-i-see-who-created-a-team"></a>È possibile vedere chi ha creato un team?

Per scoprire chi ha creato un team specifico, vedere Cercare gli eventi nel log di controllo [in Microsoft Teams.](audit-log-events.md)

## <a name="can-i-control-who-can-create-teams"></a>È possibile controllare chi può creare team?

In generale, si sconsiglia di impedire a chiunque di creare team. Se tutti gli utenti possono creare team, è più probabile che Teams sia ampiamente adottato. Facoltà, docenti o studenti possono usare Teams per creare gruppi di studio o gruppi di interesse speciale. Ciò aiuterà Teams a essere accettato all'interno e all'esterno della classe.

Nella nostra esperienza, l'istruzione degli utenti contribuisce a garantire un utilizzo responsabile di Teams. Non appena gli utenti comprendono che la creazione di team non è anonima, comprendono le implicazioni derivanti dalla loro creazione inaffidabile e tendono a non riutilizzare lo strumento in modo ileggibile.

Se si è certi di voler controllare chi può creare team, vedere Gestire chi può creare gruppi di [Microsoft 365.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Come si crea automaticamente un team per ogni corso all'inizio del semestre o trimestre?

All'inizio di ogni semestre o trimestre saranno necessari diversi nuovi team. Può essere opportuno adottare un approccio automatizzato per creare questi team automaticamente, popolarli con gli utenti giuste e impostare le autorizzazioni appropriate:

-   School Data Sync può creare gruppi di Microsoft 365 per Exchange Online e SharePoint Online, team di classe per i blocchi appunti della classe di Microsoft Teams e OneNote, gruppi scolastici per Intune per Education e integrazione dell'elenco e del Single #A0 (SSO) per molte altre applicazioni di terze parti. Per altre informazioni, [vedere Panoramica di School Data Sync.](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)
-   Con PowerShell puoi creare team e canali e configurare le impostazioni automaticamente. Per [altre informazioni, vedere Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
-   È possibile usare l'API Microsoft Graph (attualmente in versione beta) per creare, configurare, clonare e archiviare team. Per altre informazioni, vedere Usare [l'API Microsoft Graph per lavorare con Microsoft Teams.](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)

> [!TIP]
> School Data Sync crea un gruppo di Microsoft 365 per ogni classe sincronizzata e abilita l'appartenenza ai gruppi nascosti in modo che solo i docenti e gli studenti della classe possano vedere i membri della classe. [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) Se si usa un processo diverso per creare gruppi di classi, usare il parametro HiddenGroupMembershipEnabled del cmdlet New-UnifiedGroup per soddisfare gli stessi requisiti di privacy.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Come si fa a gestire le squadre al termine del semestre o del trimestre?

È consigliabile prima di tutto decidere come gestire i dati di Teams al termine del semestre o del trimestre scolastico: se eliminarli o tenerli disponibili per gli studenti anche dopo aver completato il corso. È bene tenere presente il calendario scolastico in modo che tutti i criteri impostati non sia in conflitto con le festività. Per implementare la strategia, è possibile usare gli strumenti seguenti:

-   **Criteri di conservazione:** Utilizza questa opzione per eliminare tutti i dati più vecchi di un'età specificata per assicurarti che i vecchi dati siano rimossi dalle chat (per tutti o per alcuni utenti) e canali. È anche possibile configurare Teams in modo da conservare il contenuto in modo che non possa essere eliminato. Per altre informazioni, vedere [Criteri di conservazione per Microsoft Teams.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)
-   **Criteri di scadenza:** Configurare i team in modo che scadono dopo un determinato numero di giorni. Trenta giorni prima della scadenza, a tutti i proprietari di un team viene notificato che il proprio team deve essere rinnovato, altrimenti viene eliminato (anche se un amministratore può recuperare i team eliminati per altri 30 giorni). Questa impostazione è molto utile per assicurarsi che i team inutilizzati siano al tramonto. Per altre informazioni, vedere Criteri di scadenza dei gruppi [di Microsoft 365.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Team di archiviazione:** Questa impostazione imposta i team in modalità di sola lettura. Possono ancora essere visualizzate e cercate, ma nessuno può aggiungere nuovi post. [Archiviare o ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) descrive in che modo i proprietari dei team possono archiviare un team; I proprietari dei team possono anche usare [l'API Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) per archiviare o ripristinare un team.
 
> [!IMPORTANT]
> L'uso dei criteri di scadenza dei gruppi di Microsoft 365 richiede licenze di Azure Active Directory Premium P1 per ogni utente univoco membro di uno o più gruppi di Microsoft 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Ci sono modelli di team che i membri della facoltà possono usare durante la creazione di un team?

Sì. Gli utenti possono selezionare Crea **team** da un modello esistente durante la creazione di un nuovo team e i proprietari di Teams possono anche usare l'API [Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) per creare un nuovo team dai modelli disponibili.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quali attività è possibile automatizzare tramite PowerShell o Graph?

[L'API Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) può eseguire le operazioni seguenti:

-   Creare un team.
-   Aggiungere membri e proprietari.
-   Aggiungere canali.
-   Aggiungi app.
-   Per creare un collegamento a questi passaggi clonando un team esistente, è possibile accedere anche alle relative schede.
-   Fornire all'utente un collegamento al team appena creato.
-   Rimuovi membri, proprietari, canali e app quando non sono più necessari.
-   Archivia il team quando non è più attivo. 
-   Eliminare il team.
-   Creare un thread di canale

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) può eseguire le operazioni seguenti:

-   Creare un team.
-   Aggiungere membri e proprietari.
-   Aggiungere canali.
-   Rimuovere membri, proprietari e canali quando non sono più necessari.
-   Eliminare il team.

> [!TIP]
> L'API Graph e i cmdlet di PowerShell aggiungono continuamente funzionalità. Assicurarsi di consultare spesso gli [articoli sull'API di Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) e [su PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per miglioramenti delle funzionalità.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>È possibile controllare a quali funzionalità di Teams hanno accesso docenti e studenti?

Sì. È possibile usare i criteri per controllare caratteristiche specifiche di messaggistica, riunioni, chiamate ed eventi live a cui hanno accesso gli utenti. È possibile usare le impostazioni a livello di tenant per applicare le stesse impostazioni a tutte o applicare criteri a livello di utente, se necessario. 

Per maggiori dettagli sui criteri di Teams, vedere [Gestire le impostazioni di Microsoft Teams per l'organizzazione.](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>È possibile controllare le parti esterne con cui docenti e studenti collaborano?

È possibile usare l'accesso guest per invitare utenti esterni al tenant, un'opzione utile per la collaborazione di ricerca o per le lezioni guest:

-   Usare l'elenco dei domini consentiti per consentire o bloccare i guest in base al dominio.
-   Attivare e disattivare l'accesso guest per determinati gruppi e team di Microsoft 365, per controllare quali team possono (e non possono) invitare guest.
-   Usare il log di controllo per vedere quali avvisi sono stati inviati ai guest invitati.

Per altre informazioni, vedere [Accesso guest nei gruppi di Microsoft 365.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)

## <a name="what-information-can-i-review-about-existing-teams"></a>Quali informazioni è possibile esaminare sui team esistenti?

È possibile controllare i log di controllo per visualizzare:

-   Chi è stato invitato come guest in ogni team.
-   Chi ha creato il team.

Per altre informazioni, vedere [Cercare eventi nel log di controllo in Microsoft Teams.](audit-log-events.md)

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams si evolve in modo così rapido. Come si può essere sempre aggiornati?

Per ottenere gli aggiornamenti più recenti su Teams, è consigliabile usare le risorse seguenti:

-   [Novità di Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
