---
title: Domande frequenti su Microsoft Education per amministratori IT
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 6970cb95ff85ace99cc70cb81620e7a5de322496
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426853"
---
# <a name="microsoft-education-faq-for-it-admins"></a>Domande frequenti su Microsoft Education per amministratori IT

> [!Tip]
> Guarda la sessione seguente per saperne di più sulla gestione in Microsoft Teams: [Governance, gestione e ciclo di vita in Microsoft Teams](https://aka.ms/teams-governance)

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a>Ricerca per categorie la creazione di team di controllo? Temo che gli studenti creeranno team inappropriati?

Per evitare nomi inappropriati o fuorvianti o semplicemente per fornire una struttura più struttura per il nome dei team, è possibile usare i criteri di denominazione Gruppi di Microsoft 365 (attualmente in anteprima):

- **Criteri di denominazione dei prefissi e dei suffissi** È possibile usare prefissi o suffissi per definire la convenzione di denominazione dei team (gruppi), ad esempio **GRP_US_My Group_Engineering**. I prefissi e suffissi possono essere stringhe fisse o attributi utente (ad esempio **[Department]**) che vengono aggiunti al nome in base all'utente che sta creando il team.
- **Parole bloccate personalizzate** È possibile caricare un set di parole che gli utenti di un'organizzazione specifica non possono usare nei nomi dei team creati. Ad esempio, è possibile bloccare l'uso dei termini **CEO**, **Payroll** e **HR** nei nomi dei team per i gruppi a cui non si applicano.
- **Classificazione** È possibile creare classificazioni che gli utenti dell'organizzazione possono impostare quando creano un gruppo di Microsoft 365.

> [!IMPORTANT]
> L'uso dei criteri di denominazione di Gruppi di Microsoft 365 richiede licenze di Azure Active Directory Premium P1 o licenze EDU di Azure AD Basic per ogni utente univoco membro di uno o più gruppi di Microsoft 365.

Per istruzioni dettagliate, vedere [Criteri di denominazione dei gruppi di Office](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).

> [!NOTE]
> Se i team vengono creati automaticamente usando l'input da un altro sistema (ad esempio School Data Sync), verifica che i dati di input siano conformi ai criteri di denominazione configurati; in caso contrario, la creazione di team non riuscirà.

## <a name="can-i-see-who-created-a-team"></a>È possibile vedere chi ha creato un team?

Per scoprire chi ha creato un team specifico, vedere [Cercare gli eventi in Microsoft Teams nel log di controllo](audit-log-events.md).

## <a name="can-i-control-who-can-create-teams"></a>È possibile controllare chi può creare team?

In generale, è consigliabile evitare di impedire a chiunque di creare team. Se tutti possono creare team, è più probabile che Teams sia ampiamente adottato. Docenti, insegnanti o studenti possono usare Teams per creare gruppi di studio o gruppi di interesse speciali. Questa funzionalità consente di accettare Teams all'interno e all'esterno della classe.

Nella nostra esperienza, la formazione degli utenti contribuisce a garantire un utilizzo responsabile di Teams. Non appena gli utenti comprendono che la creazione di team non è anonima, comprendono le implicazioni della loro creazione noncurante e tendono a evitare di usare erroneamente lo strumento.

Se si è certi di voler controllare chi può creare team, vedere [Gestire chi può creare Gruppi di Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a>Ricerca per categorie creare automaticamente un team per ogni corso all'inizio del semestre o del trimestre?

All'inizio di ogni semestre o trimestre, sono necessari nuovi team. Può essere utile adottare un approccio automatizzato per creare automaticamente questi team, popolare i team con gli utenti giusti e impostare le autorizzazioni appropriate:

- School Data Sync può creare Gruppi di Microsoft 365 per Exchange Online e SharePoint Online, team di classe per i blocchi appunti di Microsoft Teams e OneNote per la classe, gruppi scolastici per Intune per l'istruzione e elenchi e integrazione con Single Sign-On (SSO) per molte altre applicazioni di terze parti. Per altre informazioni [, vedere Panoramica di School Data Sync](/schooldatasync/overview-of-school-data-sync).
- Con PowerShell è possibile creare team e canali e configurare automaticamente le impostazioni. Per altre informazioni, vedere [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
- È possibile usare Microsoft API Graph (attualmente in anteprima) per creare, configurare, clonare e archiviare team. Per altre informazioni, vedere [Usare Microsoft API Graph per lavorare con Microsoft Teams](/graph/api/resources/teams-api-overview).

> [!TIP]
> School Data Sync crea un gruppo di Microsoft 365 per ogni classe sincronizzata e [abilita l'appartenenza nascosta al gruppo](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) in modo che solo i docenti e gli studenti all'interno della classe possano vedere i membri del corso. Se si usa un processo diverso per creare gruppi di classi, usare il parametro HiddenGroupMembershipEnabled del cmdlet New-UnifiedGroup per soddisfare gli stessi requisiti di privacy.

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a>Ricerca per categorie gestire i team alla fine del semestre o del trimestre?

Ti consigliamo di pensare a come gestire i dati di Teams quando il semestre o il trimestre scolastico è finito: se eliminarli o mantenerli disponibili per gli studenti anche dopo aver completato il corso. È consigliabile tenere presente il calendario dell'istituto di istruzione in modo che i criteri impostati non vengano in conflitto con le festività. È possibile utilizzare gli strumenti seguenti per implementare la strategia:

- **Criteri di conservazione:** Usa questo criterio per eliminare tutti i dati più vecchi di un'età specificata per assicurarti che i vecchi dati vengano rimossi dalle chat (per tutti o alcuni utenti) e dai canali. È anche possibile configurare Teams in modo da conservare il contenuto in modo che non possa essere eliminato. Per altre informazioni, vedere [Criteri di conservazione per Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).
- **Criteri di scadenza:** Configurare i team in modo che scada dopo un determinato giorno. Trenta giorni prima della scadenza, tutti i proprietari di un team ricevono una notifica che indica che il team deve essere rinnovato, altrimenti verrà eliminato. Anche se un amministratore può recuperare i team eliminati per altri 30 giorni. Questa impostazione è utile per assicurarsi che i team inutilizzati vengano ritirati. Per altre informazioni, vedere [Criteri di scadenza dei gruppi di Microsoft 365](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).

- **Team di archiviazione:** Questa impostazione attiva la modalità di sola lettura per i team. Possono comunque essere sfogliati e cercati, ma nessuno può aggiungere nuovi post. [Archivia o ripristina un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) descrive come i proprietari del team possono archiviare un team; I proprietari dei team possono anche usare la [API Graph (anteprima)](/graph/api/resources/teams-api-overview) per archiviare o ripristinare un team.

> [!IMPORTANT]
> L'uso dei criteri di scadenza Gruppi di Microsoft 365 richiede licenze Azure Active Directory Premium P1 per ogni utente univoco membro di uno o più gruppi di Microsoft 365.

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a>Esistono modelli di team che i membri dell'istituto di istruzione possono usare per creare un team?

Sì. Gli utenti possono selezionare **Crea team da un modello esistente** quando creano un nuovo team e i proprietari di Teams possono anche usare la [API Graph (anteprima)](/graph/api/resources/teams-api-overview) per creare un nuovo team dai modelli disponibili.

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a>Quali attività è possibile automatizzare tramite PowerShell o Graph?

Il [API Graph Microsoft (anteprima)](/graph/api/resources/teams-api-overview) può eseguire le attività seguenti:

- Creare un team.
- Aggiungere membri e proprietari.
- Aggiungere canali.
- Aggiungi app.
- È possibile creare collegamenti a questi passaggi clonando un team esistente e scaricando anche le relative schede.
- Fornire all'utente un collegamento al team creato.
- Rimuovi membri, proprietari, canali e app quando non sono più necessari.
- Archiviare il team quando non è più attivo.
- Eliminare il team.
- Creare un thread di canale

[PowerShell](/powershell/module/teams/?view=teams-ps) può eseguire le attività seguenti:

- Creare un team.
- Aggiungere membri e proprietari.
- Aggiungere canali.
- Rimuovere membri, proprietari e canali quando non sono più necessari.
- Eliminare il team.

> [!TIP]
> I cmdlet API Graph e PowerShell aggiungono costantemente funzionalità. Assicurati di controllare spesso gli articoli [di Microsoft API Graph (anteprima)](/graph/api/resources/teams-api-overview) e [PowerShell](/powershell/module/teams/?view=teams-ps) per i miglioramenti delle funzionalità.  

## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a>È possibile controllare a quali funzionalità di Teams hanno accesso docenti e studenti?

Sì. È possibile usare i criteri per controllare funzionalità specifiche di messaggistica, riunioni, chiamate ed eventi live a cui gli utenti hanno accesso. È possibile usare le impostazioni a livello di tenant per applicare le stesse impostazioni a tutte o applicare criteri a livello di utente, se necessario.

Per altre informazioni sui criteri di Teams, vedere [Gestire le impostazioni di Microsoft Teams per l'organizzazione](enable-features-office-365.md).

## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a>È possibile controllare con quali parti esterne docenti e studenti collaborano?

È possibile usare l'accesso guest per invitare utenti esterni al tenant, che possono essere utili per la collaborazione di ricerca o per le lezioni guest:

- Usare un elenco di domini consentiti per consentire o bloccare i guest in base al dominio.
- Attivare e disattivare l'accesso guest per particolari Gruppi di Microsoft 365 e team, per controllare quali team possono (e non possono) invitare guest.
- Usare il log di controllo per vedere quali avvisi sono stati inviati ai guest invitati.

Per altre informazioni, vedere [Accesso guest in Gruppi di Microsoft 365](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).

## <a name="what-information-can-i-review-about-existing-teams"></a>Quali informazioni è possibile esaminare sui team esistenti?

È possibile controllare i log di controllo per visualizzare:

- Chi è stato invitato come guest a quale team.
- Chi ha creato il team.

Per altre informazioni, vedere [Cercare eventi in Microsoft Teams nel log di controllo](audit-log-events.md).

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a>Teams si evolve così rapidamente. Come posso rimanere aggiornato?

Consigliamo le risorse seguenti per ottenere gli aggiornamenti più recenti su Teams:

- [Novità di Microsoft Teams](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
- [Blog di Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
