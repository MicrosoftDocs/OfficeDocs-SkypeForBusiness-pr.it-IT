---
title: Domande frequenti su Microsoft Education Governance per professionisti IT-Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Risposte alle domande frequenti degli amministratori di Microsoft Education groups che usano teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0faa5f24ea64ae0fcfc967281126a4852dd139cf
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "36184966"
---
# <a name="microsoft-education-governance-faq-for-admins"></a>Domande frequenti su Microsoft Education Governance per gli amministratori

> [!Tip]
> Per ulteriori informazioni sulla gestione in Microsoft teams, vedere la sessione seguente: [governance, gestione e ciclo di vita in Microsoft teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Come si controlla la creazione del team? Sono preoccupato che gli studenti creino team inappropriati.

Per evitare nomi inappropriati o fuorvianti oppure solo per ottenere una struttura più appropriata per il nome del team, è possibile usare i criteri di denominazione dei gruppi di Office 365 (attualmente in anteprima):

-   **Criteri di denominazione suffisso-prefisso** È possibile usare i prefissi o i suffissi per definire la convenzione di denominazione dei team (gruppi), ad esempio **GRP_US_My Group_Engineering**. I prefissi e i suffissi possono essere stringhe fisse o attributi utente, ad esempio **[reparto]**, che vengono aggiunti al nome in base all'utente che sta creando il team.
-   **Parole bloccate personalizzate** È possibile caricare un set di parole che gli utenti di un'organizzazione specifica sono bloccati dall'uso nei nomi dei team creati. Ad esempio, è possibile bloccare i termini **amministratore delegato**, **libro paga**e **risorse umane** da usare in nomi di team per i gruppi a cui non si applicano.
-   **Classificazione** È possibile creare classificazioni che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Office 365. 

> [!IMPORTANT]
> L'uso dei criteri di denominazione dei gruppi di Office 365 richiede le licenze di Azure Active Directory Premium P1 o le licenze di Azure AD Basic EDU per ogni utente univoco che fa parte di uno o più gruppi di Office 365.

Per istruzioni dettagliate, vedere [criteri di denominazione dei gruppi di Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!Note]
> Se i team vengono creati automaticamente usando l'input di un altro sistema, ad esempio School Data Sync, verificare che i dati di input siano conformi ai criteri di denominazione configurati; in caso contrario, la creazione del team non riuscirà.

## <a name="can-i-see-who-created-a-team"></a>È possibile vedere chi ha creato un team?

Per scoprire chi ha creato un team specifico, vedere [eseguire una ricerca nel log di controllo per gli eventi in Microsoft teams](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>È possibile controllare chi può creare Teams?

In generale, è consigliabile impedire a chiunque di creare teams. Se tutti possono creare teams, è più probabile che i team siano ampiamente adottati. Facoltà, insegnanti o studenti possono usare team per creare gruppi di studio o gruppi di interesse speciale. In questo modo i team verranno accettati all'interno e all'esterno dell'aula.

In questa esperienza, la formazione degli utenti aiuta a garantire l'utilizzo dei team responsabili. Non appena gli utenti capiscono che la creazione di team non è anonima, essi comprendono le implicazioni della loro creazione con noncuranza e tendono a rifuggire dall'uso indesiderato dello strumento.

Se si è certi di voler controllare chi può creare team, vedere [gestire chi può creare gruppi di Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Come si crea automaticamente un team per ogni corso all'inizio del semestre o del trimestre?

All'inizio di ogni semestre o trimestre è necessario un numero di nuovi team. Potrebbe essere utile adottare un approccio automatizzato per creare automaticamente questi team, popolarli con gli utenti giusti e impostare le autorizzazioni appropriate:

-   School Data Sync può creare gruppi di Office 365 per Exchange Online e SharePoint Online, team di classe per Microsoft teams e blocchi appunti per la classe di OneNote, gruppi scolastici per Intune per l'istruzione e integrazione di roster e Single Sign-on (SSO) per molti altri applicazioni di terze parti. Per altre informazioni, vedere [Panoramica di School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).
-   Con PowerShell è possibile creare team e canali e configurare le impostazioni automaticamente. Per altre informazioni, vedere [Microsoft teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
-   Puoi usare l'API Microsoft Graph (attualmente in versione beta) per creare, configurare, clonare ed archiviare team. Per altre informazioni, vedere [usare l'API Microsoft Graph per collaborare con Microsoft teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) .

> [!TIP]
> School Data Sync crea un gruppo di Office 365 per ogni classe sincronizzata e [Abilita l'appartenenza a gruppi nascosti](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) in modo che solo gli insegnanti e gli studenti della classe possano vedere i membri della classe. Se si usa un processo diverso per creare gruppi di classi, usare il parametro HiddenGroupMembershipEnabled del cmdlet New-UnifiedGroup per soddisfare gli stessi requisiti di privacy.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Come si gestiscono i team quando il semestre o il trimestre termina?

Ti consigliamo di pensare prima di tutto a come gestire i dati dei team quando il semestre scolastico o il trimestre è terminato: se eliminarlo o mantenerlo disponibile per gli studenti anche dopo aver completato il corso. È consigliabile tener presente il calendario scolastico in modo che i criteri impostati non siano in conflitto con le festività. Per implementare la strategia, è possibile usare gli strumenti seguenti:

-   **Criteri di conservazione:** Usare questo pulsante per eliminare tutti i dati antecedenti all'età specificata per verificare che i vecchi dati vengano rimossi dalle chat (per tutti o alcuni utenti) e canali. Puoi anche configurare teams per mantenere il contenuto in modo che non possa essere eliminato. Per altre informazioni, vedere [criteri di conservazione per Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
-   **Criteri di scadenza:** Configurare i team in scadenza dopo un determinato numero di giorni. Trenta giorni prima della scadenza, tutti i proprietari di un team ricevono una notifica che il loro team deve essere rinnovato, altrimenti verrà eliminato (anche se un amministratore può recuperare i team eliminati per altri 30 giorni). Questa impostazione è molto utile per verificare che i team inutilizzati siano sunsetted. Leggi altre informazioni sui [criteri di scadenza del gruppo di Office 365](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

-   **Team di archiviazione:** Questa impostazione inserisce i team in modalità di sola lettura. Possono comunque essere visualizzati e cercati, ma nessuno può aggiungere nuovi post. [Archiviare o ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) descrive in che modo i proprietari del team possono archiviare un team. I proprietari del team possono anche usare l' [API del grafico (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) per archiviare o ripristinare un team.
 
> [!IMPORTANT]
> L'uso dei criteri di scadenza di Office 365 groups richiede le licenze di Azure Active Directory Premium P1 per ogni utente univoco che fa parte di uno o più gruppi di Office 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>I modelli di team per i membri della facoltà possono essere usati durante la creazione di un team?

Sì. Gli utenti possono selezionare **Crea team da modello esistente** durante la creazione di un nuovo team e i proprietari dei team possono anche usare l' [API del grafico (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) per creare un nuovo team dai modelli disponibili.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quali attività è possibile automatizzare tramite PowerShell o Graph?

L' [API Microsoft Graph (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) può eseguire le operazioni seguenti:

-   Creare un team.
-   Aggiungere membri e proprietari.
-   Aggiungere canali.
-   Aggiungere app.
-   Fare il collegamento a questi passaggi clonando un team esistente e ottenere anche le sue linguette.
-   Assegna all'utente un collegamento al team appena creato.
-   Quando non sono più necessari, rimuovere membri, proprietari, canali e app.
-   Archiviare il team quando non è più attivo. 
-   Eliminare il team.
-   Creare un thread di canale

[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) può eseguire le operazioni seguenti:

-   Creare un team.
-   Aggiungere membri e proprietari.
-   Aggiungere canali.
-   Quando non sono più necessari, rimuovere membri, proprietari e canali.
-   Eliminare il team.

> [!TIP]
> L'API del grafico e i cmdlet di PowerShell aggiungono costantemente funzionalità. Verificare che gli articoli di [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) e [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) vengano spesso ottimizzati per le funzionalità.  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>È possibile controllare a quali team sono consentite le funzionalità di docenti e studenti?

Sì. Puoi usare i criteri per controllare le caratteristiche di messaggistica, riunioni, chiamate e eventi live specifici che gli utenti hanno accesso. Se necessario, è possibile usare le impostazioni a livello di tenant per applicare le stesse impostazioni a tutte o per applicare criteri a livelli utente. 

Per altre informazioni sui criteri per i team, vedere [gestire le impostazioni di Microsoft teams per l'organizzazione](enable-features-office-365.md).
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>È possibile controllare quali parti esterne collaborare con i docenti e gli studenti?

Puoi usare l'accesso guest per invitare utenti esterni al tenant, che possono essere utili per la collaborazione alla ricerca o per le conferenze degli ospiti:

-   Usa la whitelist dei domini per consentire o bloccare gli utenti in base al loro dominio.
-   Attivare e disattivare l'accesso guest per particolari gruppi e team di Office 365, per controllare quali team possono (e non possono) invitare gli ospiti.
-   Usare il log di controllo per visualizzare gli avvisi inviati agli utenti invitati.

Per altre informazioni, vedere [accesso guest nei gruppi di Office 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Quali informazioni si possono rivedere sui team esistenti?

È possibile controllare i log di controllo per vedere:

-   Che è stato invitato come Guest al team.
-   Chi ha creato il team.

Per altre informazioni, vedere [eseguire una ricerca nel log di controllo per gli eventi in Microsoft teams](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams si evolve così rapidamente. Come è possibile tenersi aggiornati?

Per ottenere gli aggiornamenti più recenti sui team, è consigliabile eseguire le seguenti risorse:

-   [Novità di Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [Blog di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
