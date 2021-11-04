---
title: Domande frequenti sulla governance di Microsoft Education per amministratori
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Risposte alle domande frequenti degli amministratori dei gruppi di Microsoft Education che usano Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1e9af313bc24919f96008d7f1ff5bf7383df3260
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774446"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Domande frequenti sulla governance di Microsoft Education per amministratori

> [!Tip]
> Guardare la sessione seguente per altre informazioni sulla gestione in Microsoft Teams: [Governance, gestione e ciclo](https://aka.ms/teams-governance) di vita in Microsoft Teams

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Come si controlla la creazione di team? Sono preoccupata che gli studenti creino team inappropriati.

Per evitare nomi inappropriati o fuorvianti o semplicemente per fornire una maggiore struttura per la denominazione dei team, è possibile usare il criterio di denominazione gruppi di Microsoft 365 (attualmente in anteprima):

-   **Criteri di denominazione prefisso-suffisso** È possibile usare prefissi o suffissi per definire la convenzione di denominazione dei team (gruppi), ad esempio **GRP_US_My Group_Engineering**. I prefissi e i suffissi possono essere stringhe fisse o attributi utente ( ad esempio **[Reparto]**) che vengono aggiunti al nome in base all'utente che crea il team.
-   **Parole bloccate personalizzate** È possibile caricare un set di parole che gli utenti di un'organizzazione specifica non possono usare nei nomi dei team creati. Ad esempio, è possibile bloccare l'uso  dei termini **CEO,** **Retribuzioni** e Risorse umane nei nomi dei team per i gruppi a cui non sono applicabili.
-   **Classificazione** È possibile creare classificazioni che gli utenti dell'organizzazione possono impostare quando creano un Microsoft 365 gruppo. 

> [!IMPORTANT]
> L'uso Microsoft 365 criteri di denominazione dei gruppi di Azure Active Directory Premium P1 richiede licenze Azure Active Directory Premium P1 o licenze EDU di base Azure AD per ogni utente univoco membro di uno o più gruppi Microsoft 365 utenti.

Per istruzioni dettagliate, vedere criteri di denominazione [Office gruppi.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

> [!Note]
> Se i team vengono creati automaticamente usando l'input di un altro sistema, ad esempio School Data Sync, verificare che i dati di input siano conforme ai criteri di denominazione configurati. in caso contrario, la creazione del team avrà esito negativo.

## <a name="can-i-see-who-created-a-team"></a>È possibile vedere chi ha creato un team?

Per scoprire chi ha creato un team specifico, vedere Cercare gli eventi nel log di [controllo in Microsoft Teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>È possibile controllare chi può creare team?

In generale, è consigliabile evitare che chiunque crei team. Se tutti possono creare team, Teams è più probabile che siano ampiamente adottati. Docenti, docenti o studenti possono usare i Teams per creare gruppi di studio o gruppi di interesse speciali. In questo modo Teams accettati all'interno e all'esterno della classe.

Nella nostra esperienza, l'istruzione degli utenti contribuisce a garantire un utilizzo Teams responsabile. Non appena gli utenti comprendono che la creazione di team non è anonima, comprendono le implicazioni di crearli con disaffezioni e tendono a non utilizzare in modo utilmente lo strumento.

Se si è certi di voler controllare chi può creare team, vedere Gestire chi può creare Microsoft 365 [gruppi](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Come si crea automaticamente un team per ogni corso all'inizio del semestre o del trimestre?

All'inizio di ogni semestre o trimestre, sono necessari diversi nuovi team. Può essere opportuno adottare un approccio automatizzato per creare automaticamente questi team, popolarli con gli utenti giuste e impostare le autorizzazioni appropriate:

-   School Data Sync può creare gruppi di Microsoft 365 per Exchange Online e SharePoint Online, team di classe per blocchi appunti di Microsoft Teams e OneNote per la classe, gruppi scolastici per Intune per l'istruzione e elenco e single sign-on (SSO ) per molte altre applicazioni di terze parti. Per altre informazioni, [vedere Panoramica di School Data Sync](/schooldatasync/overview-of-school-data-sync).
-   Con PowerShell è possibile creare team e canali e configurare automaticamente le impostazioni. Per altre Microsoft Teams, vedere [PowerShell.](/powershell/module/teams/?view=teams-ps)
-   È possibile usare l'API microsoft Graph (attualmente in versione beta) per creare, configurare, clonare e archiviare team. Per [altre informazioni, vedere Usare l'API](/graph/api/resources/teams-api-overview) Graph Microsoft Microsoft Teams per altre informazioni.

> [!TIP]
> School Data Sync crea un gruppo di Microsoft 365 per ogni classe [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) sincronizzata e abilita l'appartenenza ai gruppi nascosti in modo che solo gli insegnanti e gli studenti all'interno della classe possano vedere i membri della classe. Se si usa un processo diverso per creare gruppi di classi, usare il parametro HiddenGroupMembershipEnabled del cmdlet New-UnifiedGroup per soddisfare gli stessi requisiti di privacy.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Come posso gestire i team al termine del semestre o del trimestre?

È consigliabile prima di tutto pensare Teams come gestire i dati quando il semestre o il trimestre scolastico è terminato: se eliminarli o tenerli disponibili per gli studenti anche dopo aver completato il corso. È necessario tenere presente il calendario dell'istituto di istruzione in modo che i criteri impostati non in conflitto con le festività. Per implementare la strategia, è possibile usare gli strumenti seguenti:

-   **Criteri di conservazione:** Usa questa opzione per eliminare tutti i dati più vecchi di un'età specificata per assicurarti che i vecchi dati siano rimossi dalle chat (per tutti o per alcuni utenti) e dai canali. È anche possibile configurare Teams per conservare il contenuto in modo che non possa essere eliminato. Per altre informazioni, vedere [Criteri di conservazione per Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Criteri di scadenza:** Configurare i team in modo che scada dopo un determinato numero di giorni. Trenta giorni prima della scadenza, a tutti i proprietari di un team viene notificato che il team deve essere rinnovato, altrimenti verrà eliminato (anche se un amministratore può recuperare i team eliminati per altri 30 giorni). Questa impostazione è molto utile per assicurarsi che i team inutilizzati siano al tramonto. Per altre informazioni, [vedere Microsoft 365 criteri di scadenza del gruppo.](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)

-   **Team di archiviazione:** Questa impostazione attiva la modalità di sola lettura per i team. Possono comunque essere esplorati e cercati, ma nessuno può aggiungere nuovi post. [L'opzione Archivia o ripristina un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) descrive in che modo i proprietari del team possono archiviare un team. I proprietari del team possono anche usare [l'API Graph (beta)](/graph/api/resources/teams-api-overview) per archiviare o ripristinare un team.
 
> [!IMPORTANT]
> L'uso Microsoft 365 criteri di scadenza Azure Active Directory Premium P1 per ogni utente univoco membro di uno o più gruppi Microsoft 365 utenti.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Sono disponibili modelli di team da usare per i docenti durante la creazione di un team?

Sì. Gli utenti possono selezionare Crea **team** da un modello esistente durante la creazione di un nuovo team e i proprietari di Teams possono anche usare l'API [di Graph (beta)](/graph/api/resources/teams-api-overview) per creare un nuovo team dai modelli disponibili.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quali attività è possibile automatizzare tramite PowerShell o Graph?

Microsoft [Graph API (beta)](/graph/api/resources/teams-api-overview) può eseguire le operazioni seguenti:

-   Creare un team.
-   Aggiungere membri e proprietari.
-   Aggiungere canali.
-   Aggiungere app.
-   Per creare un collegamento a questi passaggi, clona un team esistente e ottieni anche le relative schede.
-   Assegnare all'utente un collegamento al team appena creato.
-   Rimuovere membri, proprietari, canali e app quando non sono più necessari.
-   Archiviare il team quando non è più attivo. 
-   Eliminare il team.
-   Creare un thread di canale

[PowerShell](/powershell/module/teams/?view=teams-ps) può eseguire le operazioni seguenti:

-   Creare un team.
-   Aggiungere membri e proprietari.
-   Aggiungere canali.
-   Rimuovere membri, proprietari e canali quando non sono più necessari.
-   Eliminare il team.

> [!TIP]
> I cmdlet Graph API e PowerShell aggiungono continuamente funzionalità. Assicurarsi di controllare spesso gli [articoli microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) e [PowerShell](/powershell/module/teams/?view=teams-ps) per i miglioramenti apportati alle funzionalità.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>È possibile controllare a quali Teams a cui i docenti e gli studenti hanno accesso?

Sì. È possibile usare i criteri per controllare specifiche funzionalità di messaggistica, riunione, chiamata ed evento live a cui gli utenti hanno accesso. È possibile usare le impostazioni a livello di tenant per applicare le stesse impostazioni a tutti o, se necessario, applicare criteri a livello di utente. 

Per altre informazioni sui criteri Teams, vedere Gestire le Microsoft Teams [per l'organizzazione.](enable-features-office-365.md)
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>È possibile controllare con quali parti esterne collaborano docenti e studenti?

È possibile usare l'accesso guest per invitare utenti esterni al tenant, che possono essere utili per la collaborazione alla ricerca o per le lezioni guest:

-   Usare un elenco di domini consentiti per consentire o bloccare guest in base al dominio.
-   Attivare e disattivare l'accesso guest per Microsoft 365 gruppi e team specifici, per controllare quali team possono (e non possono) invitare guest.
-   Usare il log di controllo per vedere quali avvisi sono stati inviati ai guest invitati.

Per altre informazioni, vedere [Accesso guest in Microsoft 365 gruppi](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Quali informazioni è possibile esaminare sui team esistenti?

È possibile controllare i log di controllo per visualizzare:

-   Who stato invitato come guest a quale team.
-   Who creato il team.

Per altre informazioni, vedere [Cercare eventi nel log](audit-log-events.md)di controllo in Microsoft Teams .

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams si evolve così rapidamente. Come si può rimanere aggiornati?

È consigliabile usare le risorse seguenti per ottenere gli aggiornamenti più recenti Teams:

-   [Novità di Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)