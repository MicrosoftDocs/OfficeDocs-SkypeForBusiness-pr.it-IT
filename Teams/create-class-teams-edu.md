---
title: Metodi raccomandati e migliori pratiche per la creazione dei team di classe
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: Informazioni sui metodi raccomandati e le migliori pratiche per la creazione di team di classe per la propria scuola.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e85ef79247bdf35c3c116504af23728a0d268ca5
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429328"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>Metodi raccomandati e migliori pratiche per la creazione dei team di classe

Microsoft Teams per l’istruzione offre   [tipi di team specifici](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)  per finalità didattiche. Il [team di classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) è concepito per l'uso didattico e offre funzionalità specifiche che supportano le esigenze delle classi scolastiche, tra cui:  

- Attività
- Voti
- Blocco appunti di OneNote per la classe  
- [Cartella Materiali della classe](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  per proteggere i contenuti di sola lettura per gli studenti
- [Accesso anticipato per gli insegnanti](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) per configurare le classi prima di aggiungere gli studenti 
- La possibilità di disattivare l'audio degli studenti che disturbano, e altre autorizzazioni speciali  

Ci sono diversi modi per creare i team di classe, e Teams per l'istruzione offre una serie unica di strumenti di distribuzione per semplificare al massimo il processo. Di seguito sono descritte alcune opzioni, per aiutare a scegliere il percorso di distribuzione migliore per le proprie esigenze.  

## <a name="automatic-team-creation-using-sds"></a>Creazione automatica dei team con SDS

**Questa caratteristica sarà disponibile a breve, entro la fine di luglio 2020.**

L'automazione della creazione del team consente ad amministratori IT e insegnanti di risparmiare tempo. Assicura agli insegnanti che tutti i team di classe siano stati creati e pronti per la configurazione al momento dell'accesso. [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) è uno strumento gratuito di Office 365 Education che leggi i dati dei sistemi di documentazione degli istituti, come un Sistema di gestione dei dati degli studenti (SIS) o un Sistema di gestione dell'apprendimento (LMS). SDS usa i dati per arricchire la configurazione di Office 365 in molti modi, tra cui la creazione di team di classe in blocco e la sincronizzazione con il sistema informativo per tenere aggiornati insegnanti e studenti quando l'iscrizione viene modificata. SDS può importare i dati da qualsiasi sistema di documentazione e ha connettori integrati per molti dei [fornitori SIS](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support) esistenti nel mondo. Raccomandiamo fortemente l'uso di SDS, in quanto offre i seguenti vantaggi.  

### <a name="benefits"></a>Vantaggi

- Creazione e manutenzione automatica dei team di classe. Gli insegnanti possono accedere ai team e iniziare subito a insegnare.
- L'iscrizione viene sincronizzata con il sistema SIS/LMS per gestire le modifiche dell'iscrizione degli studenti.
- Team di customer success EDU disponibile per assistenza gratuita per la distribuzione.
- [Accesso anticipato degli insegnanti](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): i docenti hanno il tempo di preparare i loro team prima di ricevere gli studenti.  
- È possibile creare facoltativamente utenti e applicare le licenze di Office 365.
- Crea gruppi di sicurezza per l'uso in Office 365, inclusi i criteri di Teams.
- Crea unità amministrative per la delega amministrativa con ambito e la [reimpostazione della password degli insegnanti](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset). 
- Gestione integrata di errori e nuovi tentativi, limitazione del backoff, e stabilizzazione della sessione per elaborazioni di larga portata al fine di ridurre il carico di lavoro degli amministratori.  
- Funzionalità integrate di pulizia per rinominare e archiviare i gruppi e i team che sono obsoleti.
- [Sincronizzazione dei voti](https://docs.microsoft.com/schooldatasync/grade-sync): i docenti possono eseguire tutte le valutazioni in Teams, e i voti sono trascritti automaticamente sul registro SIS. 
- [Protezione dei dati degli studenti](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): impedisce agli studenti di usare app non sviluppate da Microsoft e di tracciare e gestire il consenso dei genitori. 
- I dati importati sono usati per arricchire i dati analitici con ruoli utente, organizzazioni (scuole) e altri dati importanti.  

### <a name="considerations"></a>Considerazioni

SDS crea i team in due passaggi. Nel primo passaggio, un gruppo di Microsoft 365 viene creato in Azure Active Directory (Azure AD), e nel secondo il gruppo viene convertito automaticamente in un team.  Il secondo passaggio per la creazione di team è facoltativo in SDS. Un amministratore potrebbe voler evitare di creare automaticamente i team, in base al tempo di distribuzione e al numero di team inutilizzati che potrebbero derivarne. Raccomandiamo alle istituzioni con oltre 500.000 team di disattivare la creazione automatica dei team in SDS, e di seguire il [metodo di creazione dei team con docente](#educator-led-team-creation-from-office-365-class-groups).  

### <a name="get-started"></a>Per iniziare

Per iniziare, andare a [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) e contattare [https://aka.ms/sdssupport](https://aka.ms/sdssupport) l'assistenza distribuzione.  

## <a name="educator-led-team-creation-from-office-365-class-groups"></a>Creazione dei team con docente dai gruppi di classe di Office 365

**Questa caratteristica sarà disponibile a breve, entro la metà di agosto 2020.**

La creazione di team con docente è un'ottima opzione per la distribuzione, se si vuole semplificare ai docenti la creazione delle le classi necessarie. Raccomandiamo agli istututi con 500.000 o più team di usare questo metodo per minimizzare il numero di team creati esternamente.  

Questo approccio ibrido consente di usare SDS per creare i gruppi di ciascuna classe (raccomandato), oppure di usare la [API di Graph](https://docs.microsoft.com/graph/api/educationroot-post-classes) per crearli autonomamente. Dopo aver preparato i gruppi di classe, gli educatori possono convertirli in team usando l'icona **Classi suggerite**.

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="Schermata che mostra l'icona Classi suggerite":::

### <a name="benefits"></a>Vantaggi

- [Accesso anticipato degli insegnanti](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): i docenti hanno il tempo di preparare i loro team prima di ricevere gli studenti.  
- Riduce il numero di Team inutilizzati e non necessari. Le classi sono preparate e suggerite, ma non vengono create fino a quando il docente intende usarle.  Questa opzione è consigliata agli istituti di grandi dimensioni che hanno più di 500.000 team per ridurre gli ingombri.
- SDS
    - L'iscrizione viene sincronizzata con il sistema SIS/LMS per gestire le modifiche dell'iscrizione degli studenti.
    - Team di customer success EDU disponibile per assistenza gratuita per la distribuzione.
    - È possibile creare facoltativamente utenti e applicare le licenze di Office 365.
    - Crea gruppi di sicurezza per l'uso in Office 365, inclusi i criteri di Teams.
    - Crea unità amministrative per la delega amministrativa con ambito e la [reimpostazione della password degli insegnanti](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset).
    - Gestione integrata di errori e nuovi tentativi, limitazione del backoff, e stabilizzazione della sessione per elaborazioni di larga portata al fine di ridurre il carico di lavoro degli amministratori. 
    - Funzionalità integrate di pulizia per rinominare e archiviare i gruppi e i team che sono obsoleti. 
    - [Sincronizzazione dei voti](https://docs.microsoft.com/schooldatasync/grade-sync): i docenti possono eseguire tutte le valutazioni in Teams, e i voti sono trascritti automaticamente sul registro SIS. 
    - [Protezione dei dati degli studenti](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): impedisce agli studenti di usare app non sviluppate da Microsoft e di tracciare e gestire il consenso dei genitori. 
    - I dati importati sono usati per arricchire i dati analitici con ruoli utente, organizzazioni (scuole) e altri dati importanti.
- API di Microsoft Graph
    - Flessibilità e controllo in più.
    - Non richiede integrazione con SDS.

### <a name="considerations"></a>Considerazioni

- Non completamente automatico, richiede alcune azioni da parte del docente.
- Gli insegnanti che non sono autorizzati a creare i team possono comunque crearli dai gruppi esistenti, come mostrato [qui](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- La API di Microsoft Graph richiede un alto livello di competenza tecnica e più tempo per creare ed eseguire gli script e per correggere eventuali problemi insorti durante la creazione dei gruppi di classe.

### <a name="get-started"></a>Per iniziare

Per iniziare con il metodo SDS, andare a [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) e contattare [https://aka.ms/sdssupport](https://aka.ms/sdssupport) l'assistenza distribuzione. 

Per usare il metodo con la API di Graph, vedere [API di Microsoft Graph](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http) e [Creare un team di classe](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http).  

> [!NOTE]
> Per usare questo metodo con SDS, è necessario disattivare la creazione automatica dei team nel proprio profilo SDS. È anche possibile usare una combinazione di creazione di team automatica e con docente per i team di classe obbligatori e facoltativi usando due profili SDS.

## <a name="powershell-script-using-graph-apis"></a>Script di PowerShell con le API di Microsoft Graph

Con PowerShell, è possibile scrivere uno script per creare team e canali e configurare automaticamente le impostazioni. Richiede all'amministratore di creare prima di tutto il gruppo, aggiungere docenti e studenti e quindi creare il team come descritto [qui](https://docs.microsoft.com/graph/teams-create-group-and-team). È anche possibile usare l'API di Microsoft Graph per creare, configurare, duplicare e archiviare i team. Per altre informazioni, vedere [Usare la API di Microsoft Graph per lavorare con Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview), [PowerShell di Microsoft Teams](https://docs.microsoft.com/powershell/module/teams) e [Creare un team di classe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type). L'uso delle API di Graph è un ottimo modo per avere più controllo e flessibilità, ma richiede un livello elevato di competenza tecnica e richiede più tempo per la configurazione iniziale.  

### <a name="benefits"></a>Vantaggi

- Flessibilità e controllo in più.
- Possibilità di abilitare l'accesso anticipato degli insegnanti o l'accesso immediato degli studenti ai team.  
- Se si [creano team dai gruppi](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group), gli insegnanti potranno accedere anticipatamente e le modifiche dell'iscrizione degli studenti al gruppo Azure AD saranno sincronizzate.

### <a name="considerations"></a>Considerazioni

- Richiede un alto livello di competenza tecnica e più tempo per creare ed eseguire gli script e per correggere eventuali problemi insorti durante la creazione dei gruppi di classe.
- Nessuna logica nativa di gestione degli errori o dei nuovi tentativi.
- Le modifiche dell'iscrizione non sono sincronizzate con SIS. 

> [!NOTE]
> I team di classe richiedono l'iscrizione di gruppi nascosti, in modo che i docenti e gli studenti possano vedere i membri della classe. Per creare un gruppo di classe in Office 365, vedere [Creare un team di classe](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http) per soddisfare gli stessi requisiti di privacy.

## <a name="manual-team-creation"></a>Creazione manuale del team

Gli studenti e gli insegnanti otterranno il massimo da Teams quando potranno usarlo con meno limitazioni possibili e personalizzarlo in base alle proprie necessità. In Teams, gli utenti possono personalizzare la loro esperienza d'uso creando i team. Gli insegnanti impostano il tipo di team di classe e invitano gli studenti, come mostrato [qui](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch). Gli insegnanti possono invitare gli studenti [aggiungendo studenti al proprio team](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), [condividendo un codice di accesso](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f), o [condividendo un collegamento al team](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Se possibile, è consigliabile che siano i docenti ad aggiungere gli studenti al team per assicurarsi che ricevano l'accesso e vengano informati di essere stati aggiunti a un team.

### <a name="benefits"></a>Vantaggi

- Flessibilità e controllo in più per gli insegnanti.
- Creazione e accesso immediato al team.  

### <a name="considerations"></a>Considerazioni

- Richiede l'azione e il tempo dell'insegnante.
- L'iscrizione degli studenti non viene sincronizzata con SIS e richiede la gestione manuale.
- Gli insegnanti non possono accedere in anticipo ai propri team. Gli studenti otterranno accesso immediato.

## <a name="recommended-best-practices"></a>Buone pratiche consigliate

- Distribuisci subito! Si consiglia effettuare prontamente la distribuzione per garantire che tutto funzioni correttamente e sia pronto per il primo giorno di scuola. Se si usa SDS, non è necessaria l'iscrizione completa degli studenti per avviare la distribuzione di SDS. Gli studenti verranno sincronizzati quando queste informazioni saranno disponibili in SIS.
- Se si hanno più di 500.000 team, è consigliabile usare il [metodo di creazione dei team con docente](#educator-led-team-creation-from-office-365-class-groups). Riduce i team inutilizzati e gli ingombri creando solo team di classe rilevanti e necessari.  
- Se si verificano problemi con la creazione automatica di team con SDS, ad esempio i corsi sono mancanti, e ai docenti servono subito, è possibile usare il [metodo di creazione dei team con docente](#educator-led-team-creation-from-office-365-class-groups). La [Creazione manuale del team](#manual-team-creation) è un'altra soluzione, ma non tiene aggiornata l'iscrizione del proprio team.  
- Il tenant prevede un limite di 500.000 team. Di conseguenza, gli amministratori devono cercare in modo proattivo di ridurre il numero di team inutilizzati per evitare di superare questi limiti ed estendere il tempo di configurazione. Per altre informazioni sui limiti, vedere [Limiti e specifiche di Microsoft Teams](limits-specifications-teams.md).  
