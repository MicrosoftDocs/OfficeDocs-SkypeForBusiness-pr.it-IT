---
title: Introduzione a Microsoft Teams per l'apprendimento a distanza
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Guida per l'apprendimento a distanza con Microsoft Teams per l'istruzione.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466024"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Introduzione a Microsoft Teams per l'apprendimento a distanza

Questo articolo illustra i passaggi di amministrazione IT per configurare l'istituto di istruzione per l'apprendimento remoto tramite Microsoft Teams.

All'interno di Teams, **i docenti** possono:

- Comunicare rapidamente con gli studenti.
- Condividere file e siti Web.
- Creare blocchi appunti di OneNote per la classe.
  - Organizzare lezioni interattive.
  - Fornire feedback efficaci e tempestivi.
- Distribuire e assegnare voti agli esercizi.
- Condividere materiale informativo nelle comunità di apprendimento professionale.

**Gli amministratori dell'istruzione e il personale** didattico possono:

- Rimani aggiornato sugli eventi.
- Collaborare usando Staff Teams per gli annunci e le conversazioni in tema.

# <a name="accounts--licenses"></a>[Account & licenze](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>Account utente, licenze e sicurezza delle identità

Teams usa Microsoft 365 per autenticare gli utenti e fornire servizi. Tutti gli utenti devono stabilire identità di Microsoft 365 per facilitare la collaborazione.

Se le identità utente non esistono già, seguire questa procedura per stabilirle:

1. [Creare utenti con School Data Sync](/microsoft-365/education/deploy/school-data-sync).
2. [Assegnare licenze agli utenti](teams-edu-licensing.md).
3. [Creare gruppi di Microsoft 365](Office-365-groups.md).
4. [Configurare Exchange](Exchange-Teams-interact.md).
5. [Configurare SharePoint e OneDrive](SharePoint-OneDrive-interact.md).
6. [Configurare gli utenti che hanno la posta elettronica di Google](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

Microsoft Teams è incluso in tutti i piani di Microsoft 365, incluso il piano gratuito A1 Education.

Per indicazioni sulla distribuzione di Microsoft 365 e sulla configurazione di Teams, vedere [Creare il tenant di Microsoft 365](/microsoft-365/education/deploy/create-your-office-365-tenant).

# <a name="set-up-teams"></a>[Configurare Teams](#tab/setup)

## <a name="easily-set-up-teams"></a>Configurare facilmente Teams

Ecco le due cose che devi fare per essere subito operativo con Teams:

### <a name="1-allow-users-to-create-teams"></a>1. Consentire agli utenti di creare team

**Per impostazione predefinita, tutti possono creare gruppi di Microsoft 365 e Teams**, ma questa capacità potrebbe non essere sempre appropriata.

Ad esempio, alcuni istituti potrebbero voler impedire agli studenti di creare Teams senza supervisione. La creazione di gruppi e team di Microsoft 365 può essere [limitata a determinati gruppi di sicurezza](/microsoft-365/admin/create-groups/manage-creation-of-groups).

Per gli istituti di istruzione superiore, è consigliabile consentire a tutti, inclusi gli studenti, di creare team per classi, ricerche, progetti di gruppo e gruppi di studio.

Per una procedura dettagliata su come creare Teams, vedere [Creare un team di classe in Microsoft Teams](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).

### <a name="2-configure-user-experiences-using-policies"></a>2. Configurare le esperienze utente con i criteri

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Vedere [Proteggere gli studenti in Teams per l'apprendimento a distanza](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8).
>
> Se si vogliono visualizzare i suggerimenti per i criteri EDU, vedere [Criteri e pacchetti di criteri di Teams per l'istruzione](policy-packages-edu.md).

I criteri di Teams controllano le funzionalità disponibili per utenti o gruppi specifici. I criteri possono definire chi deve essere autorizzato a usare chat private, chiamate private, pianificazione delle riunioni, tipi di contenuto condivisibili e altro ancora.

**Il personale dell'istruzione superiore, i docenti e gli studenti** possono usare i criteri predefiniti (globali). È possibile modificare i criteri per aggiungere altre funzionalità a Teams, incluse [le funzionalità di traduzione](messaging-policies-in-teams.md#messaging-policy-settings) e [la trascrizione automatica delle riunioni](meetings-policies-recording-and-transcription.md#transcription).

**Gli studenti della scuola primaria e secondaria** potrebbero aver bisogno di funzionalità limitate. È consigliabile apportare modifiche ai criteri degli studenti al criterio "Globale (impostazione predefinita a livello di organizzazione)".

**Al personale della scuola primaria-secondaria e ai docenti** devono essere assegnati criteri che concedono funzionalità chiave, ad esempio consentire la chat privata e la pianificazione delle riunioni. [Assegnare questi criteri in blocco al personale e ai docenti](batch-group-policy-assignment-edu.md).

> [!IMPORTANT]
> Per i criteri delle riunioni assegnati a qualsiasi utente, è consigliabile impostare l'impostazione **Ammetti automaticamente persone** **su Tutti gli utenti dell'organizzazione**. In questo modo gli utenti non autenticati devono essere ammessi dalla sala di attesa prima di poter partecipare alle riunioni di Teams.
>
> Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](meeting-policies-participants-and-guests.md#automatically-admit-people).

# <a name="class-teams"></a>[Team di classe](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>Creare team di classe per un uso sicuro delle classi

Microsoft Teams per l'istruzione offre [tipi di team specifici](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) per finalità didattiche. Il [team di classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) è concepito per l'uso didattico e offre funzionalità specifiche che supportano le esigenze delle classi scolastiche, tra cui:

- Assegnazioni.
- Gradi.
- Blocco appunti di OneNote per la classe.
- [Cartella Materiale del corso](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  per proteggere il contenuto di sola lettura per gli studenti.
- [Insights](./class-insights.md) fornisce dati in tempo reale riguardanti il coinvolgimento, gli esercizi e il benessere degli studenti per ogni aula.
- [Accesso dei docenti precoci](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) per configurare il corso prima dell'aggiunta degli studenti.
- La possibilità di disattivare l'audio degli studenti che disturbano e altre autorizzazioni speciali.

I team di classe possono essere creati tramite:

- [School Data Sync (SDS)](#automatic-team-creation-using-sds).
- [Creazione guidata da docenti con i gruppi di classe di Microsoft 365](#educator-led-team-creation-from-microsoft-365-class-groups).
- [Script di PowerShell con API Graph](#powershell-script-using-graph-apis).
- [Creazione manuale del team](#manual-team-creation).

Di seguito sono descritte alcune opzioni, per aiutare a scegliere il percorso di distribuzione migliore per le proprie esigenze.

### <a name="automatic-team-creation-using-sds"></a>Creazione automatica dei team con SDS

[School Data Sync (SDS)](/SchoolDataSync) legge i dati dal sistema di registrazione di un istituto, come sis (Student Information System) o sistema LMS (Learning Management System).

SDS può importare dati da qualsiasi sistema di record e ha connettori incorporati a molti [fornitori DIS](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support).  

#### <a name="benefits-of-sds"></a>Vantaggi di SDS

- Crea automaticamente gli utenti e applica le licenze.
- Crea e gestisce automaticamente i team di classe.
- Viene sincronizzato con SIS/LMS per mantenere le modifiche all'appartenenza degli studenti.
- [Consente ai docenti di preparare i corsi prima di aggiungere gli studenti](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).
- Può creare automaticamente gruppi di sicurezza.
- Crea unità amministrative per la delega amministrativa con ambito.
- [Consente la reimpostazione della password dei docenti](/schooldatasync/how-to-enable-teacher-password-reset).
- Include funzionalità di pulizia integrate per rinominare e archiviare gruppi e team.
- [Sincronizza i voti da Teams a SIS](/schooldatasync/grade-sync).
- [Protegge i dati personali degli studenti](/schooldatasync/protecting-student-personal-data).
- Monitora e gestisce il consenso dei tutori.
- Fornisce dati di Insights per l'istruzione migliori.

#### <a name="considerations-for-sds"></a>Considerazioni per SDS

SDS crea team in due passaggi:

1. SDS crea un gruppo di Microsoft 365 in Azure Active Directory (Azure AD).
2. SDS trasforma automaticamente il gruppo in un team.

Il secondo passaggio per la creazione di team è facoltativo in SDS. Un amministratore potrebbe voler evitare di creare automaticamente i team, in base al tempo di distribuzione e al numero di team inutilizzati che potrebbero derivarne. Vedere invece il [metodo di creazione del team guidato da Educator](#educator-led-team-creation-from-microsoft-365-class-groups).  

#### <a name="get-started-with-sds"></a>Introduzione a SDS

Per iniziare, passare a [School Data Sync (SDS)](/SchoolDataSync) e contattare [https://aka.ms/sdssupport](https://aka.ms/sdssupport) per ottenere assistenza gratuita per la distribuzione.  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>Creazione di team guidati da docenti da gruppi di classe di Microsoft 365

La creazione di team basata su educatori consente ai docenti di creare facilmente le classi di cui hanno bisogno.  

Questo approccio consente di usare SDS per creare gruppi per ogni classe (scelta consigliata) o di usare [API Graph](/graph/api/educationroot-post-classes) per crearli autonomamente.

Dopo aver preparato i gruppi di classe, i docenti possono convertire i gruppi in team:

1. Selezionare la scheda Teams in Teams.
2. Nella parte superiore del client selezionare l'icona **Classi suggerite** .

#### <a name="benefits-of-educator-led-team-creation"></a>Vantaggi della creazione di team guidati da docenti

- I corsi vengono preparati e suggeriti, ma non creati a meno che il docente non li usi.
- Per le istituzioni con più di 500.000 team, questo metodo riduce il numero di team non necessari.
- [Vantaggi di SDS](#benefits-of-sds).
- API Graph benefici.
  - Consente ai docenti di controllare quali classi vengono create.
  - Non richiede integrazione con SDS.

#### <a name="considerations-for-educator-led-team-creation"></a>Considerazioni per la creazione di team guidati da docenti

- Non completamente automatizzato e richiede alcune azioni da parte del docente.
- I docenti che non hanno l'autorizzazione per creare team possono comunque [creare team dai gruppi esistenti](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- API Graph richiede un elevato livello di competenze tecniche, il tempo per creare ed eseguire lo script e il tempo per risolvere eventuali problemi.

#### <a name="get-started-with-educator-led-team-creation"></a>Introduzione alla creazione di team guidata da docenti

Per iniziare a usare il metodo SDS, passare a [School Data Sync (SDS)](/SchoolDataSync) e contattare [https://aka.ms/sdssupport](https://aka.ms/sdssupport) per ottenere assistenza gratuita per la distribuzione.

- Dovrai disattivare la creazione automatica del team nel tuo profilo SDS.
- È possibile usare una combinazione di creazione automatica e guidata da docenti per i team di classe usando due profili SDS.

Per usare il metodo con la API di Graph, vedere [API di Microsoft Graph](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) e [Creare un team di classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true).  

### <a name="powershell-script-using-graph-apis"></a>Script di PowerShell con le API di Microsoft Graph

Con PowerShell è possibile scrivere uno script per creare team e canali e configurare automaticamente le impostazioni.

Questo metodo richiede all'amministratore [di creare prima il gruppo, aggiungere docenti e studenti e quindi creare il team](/graph/teams-create-group-and-team).

È anche possibile usare [microsoft API Graph per creare, configurare, clonare e archiviare team](/graph/api/resources/teams-api-overview).

#### <a name="benefits-of-powershell-scripts"></a>Vantaggi degli script di PowerShell

- Consente agli amministratori IT di controllare la creazione di classi.
- Possibilità di abilitare l'accesso anticipato dei docenti o l'accesso immediato degli studenti ai team.
- [Sincronizza le modifiche apportate all'appartenenza degli studenti al gruppo Azure AD](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

#### <a name="considerations-for-powershell-scripts"></a>Considerazioni per gli script di PowerShell

- Richiede un alto livello di competenza tecnica e più tempo per creare ed eseguire gli script e per correggere eventuali problemi insorti durante la creazione dei gruppi di classe.
- Nessuna logica nativa di gestione degli errori o dei nuovi tentativi.
- Le modifiche all'appartenenza non vengono sincronizzate con SIS.

> [!NOTE]
> I team di classe richiedono l'iscrizione di gruppi nascosti, in modo che i docenti e gli studenti possano vedere i membri della classe. Per creare un gruppo di classe di Microsoft 365, vedere [Creare un team di classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) per soddisfare i requisiti di privacy.

### <a name="manual-team-creation"></a>Creazione manuale del team

Gli utenti possono personalizzare l'esperienza di Teams con la possibilità di creare i propri team.

A seconda delle autorizzazioni di un utente, può:

- [Configurare i propri team e invitare utenti, inclusi gli studenti](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch).
- [Aggiungere manualmente utenti al team](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954).
- [Condividi un codice di partecipazione](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).
- [Condividere un collegamento al team](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

È consigliabile fare in modo che i docenti aggiurino i loro studenti al team per assicurarsi che gli studenti possano accedervi e ricevere una notifica che li informa che sono stati aggiunti.

#### <a name="benefits-of-manual-team-creation"></a>Vantaggi della creazione manuale del team

- Offre ai docenti il pieno controllo della creazione della classe.
- I team di classe vengono creati immediatamente.

#### <a name="considerations-for-manual-team-creation"></a>Considerazioni per la creazione manuale di team

- Richiede l'azione e il tempo del docente.
- L'appartenenza degli studenti non viene sincronizzata con SIS e richiede la gestione manuale.
- Gli studenti avranno accesso immediato ai team di classe.

### <a name="recommended-best-practices"></a>Buone pratiche consigliate

- Si consiglia effettuare prontamente la distribuzione per garantire che tutto funzioni correttamente e sia pronto per il primo giorno di scuola.

- Per problemi con la creazione automatica del team SDS, i docenti possono usare il [metodo di creazione del team guidato dai docenti](#educator-led-team-creation-from-microsoft-365-class-groups) per riprovare. [La creazione manuale del team](#manual-team-creation) è un'altra soluzione, ma le classi non si sincronizzano con SIS.

- Il tenant prevede un limite di 500.000 team. Pertanto, gli amministratori devono ridurre il numero di team inutilizzati per evitare di raggiungere questi limiti. Per altre informazioni, vedere [Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md).  

# <a name="educator-early-access"></a>[Accesso anticipato dei docenti](#tab/early-access)

## <a name="early-access-to-class-teams"></a>Accesso anticipato ai team di classe

I team di classe ad accesso anticipato consentono ai docenti di accedere ai team di classe prima che gli studenti possano visualizzarli. I docenti avranno il tempo di configurare, aggiungere file e organizzarsi prima di concedere l'accesso agli studenti.

Quando gli studenti sono pronti ad accedere al team, possono [attivare la classe](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>Come si creano i team di classe che forniscono ai docenti l'accesso anticipato alla configurazione di un team prima di ammettere gli studenti?

Per impostazione predefinita, i team creati da gruppi (con SDS, con docenti o API Graph) creano automaticamente team con accesso anticipato.

Per creare i propri team con accesso anticipato con l'API Graph, è necessario [creare una classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) e [creare il team da un gruppo](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

### <a name="how-do-i-check-if-a-class-is-activated"></a>Come si verifica l'attivazione di una classe?

Nel [tipo di risorsa team](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true), visualizzare la proprietà [èMembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true), per vedere se una classe è attivata.

Usare [Get Team API](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) per eseguire una query relativa alla ```isMembershipLimitedToOwners``` proprietà di una classe specifica. Se il team è disattivato, verrà restituito il valore false. Se il team non è stato attivato, restituirà un valore true.

### <a name="how-do-i-activate-a-class-for-an-educator"></a>Come si attiva un corso per un docente?

Usare [l'API Aggiorna team](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true) e impostare la ```isMembershipLimitedToOwners``` proprietà su false per attivare il team per conto del docente. Dopo l'attivazione, un team non può essere annullato.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Creare team del personale per la comunicazione e la collaborazione

[I team di tipo personale](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) sono destinati agli amministratori dell'istruzione e al personale per condividere informazioni e collaborare alle iniziative a livello di istituto.

Gli amministratori dell'istruzione possono aggiungere personale al team con la creazione guidata del team, [aggiungendo membri dopo la creazione del team](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9) o [condividendo un codice di partecipazione o un collegamento al team](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

# <a name="meeting-scenarios"></a>[Scenari di riunione](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Possibilità delle riunioni di Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Riunioni collaborative per le lezioni virtuali

Le [riunioni di Microsoft Teams](./tutorial-meetings-in-teams.yml) supportano fino a 250 partecipanti simultanei, con la possibilità di utilizzare audio, video, [condivisione di contenuti](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), lavagne e note condivise.

Le riunioni possono essere:

- [Pianificata all'interno del client di Teams](./tutorial-meetings-in-teams.yml).
- Registrati e salvati per consentire ai partecipanti di rivederla in un secondo momento.
- [Trascritto per trovare facilmente contenuti](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308).
- Accesso tramite webcam, microfono e altoparlante di un portatile o di un telefono cellulare.
- [Ottimizzato per dispositivi specifici](https://products.office.com/microsoft-teams/across-devices/devices).
- Terminata per tutti i partecipanti per assicurarsi che gli studenti non partecipi a una riunione senza supervisione.

### <a name="districtuniversity-events-or-updates"></a>Eventi o aggiornamenti distrettuali/universitari

Alcune riunioni hanno un ampio pubblico e esigenze di produzione aggiuntive. In queste riunioni intervengono relatori, produttori e moderatori delle sessioni di domande e risposte.

Teams supporta queste sessioni con [eventi live di Microsoft Teams](teams-live-events/what-are-teams-live-events.md).

Gli eventi live possono essere usati per scenari come:

- Aggiornamenti del distretto o dell'università.
- La leadership si rivolge.
- Istruzioni per classi di grandi dimensioni o gruppi di studenti.
- Estensione alla tua community.

Scopri come condurre sessioni live all'indirizzo:

- [Pianificare e pianificare un evento live](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).
- [Produrre un evento live](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb).
- [Partecipa a un evento live](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac).
- [Moderare una Q&A](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

# <a name="resources"></a>[Risorse](#tab/resources)

## <a name="support-resources"></a>Risorse di supporto

Per una panoramica generica della transizione all'apprendimento remoto, [inizia qui](https://www.microsoft.com/education/remote-learning)

Se sei un amministratore IT, un docente, uno studente o un tutore, queste risorse possono aiutarti a usare Teams:

- **Amministratori IT**
  - [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).
  - [Scaricare e distribuire client di Teams](get-clients.md).
  - [Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams).
  - [Teams per l'infrastruttura desktop virtualizzata](./teams-for-vdi.md).
  - [Monitorare e gestire la qualità delle chiamate](monitor-call-quality-qos.md).
  - [Verificare l'integrità dei servizi per Teams](service-health.md).
  - [Ottimizza il traffico di Microsoft 365 per il personale remoto](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).
  - [Contatti di supporto per Teams](/microsoft-365/admin/contact-support-for-business-products).
  - [Teams per l'istruzione webinar](https://aka.ms/TeamsEDUWebinars).

- **Docenti**
  - [Centro assistenza per docenti](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).
  - [Guida all'apprendimento remoto](https://aka.ms/RemoteLearningHelp).
  - [Scarica Teams](get-clients.md).
  - [Teams per l'istruzione webinar](https://aka.ms/TeamsEDUWebinars).
  - [Corso online per docenti che usano Teams](https://education.microsoft.com/course/9c9f5c11/overview).
  - [Corso online per creare ambienti di apprendimento collaborativi con Teams](https://education.microsoft.com/course/b1e15cfc/overview).
  - [Invia un ticket di supporto](https://www.microsoft.com/microsoft-teams/download-app).

- **Studenti**
  - [Centro assistenza per studenti](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694).
  - [Guida all'apprendimento remoto](https://aka.ms/RemoteLearningHelp).
  - [Scarica Teams](https://www.microsoft.com/microsoft-teams/download-app).

- **Guardiani**
  - [Guida all'apprendimento remoto](https://aka.ms/RemoteLearningHelp).
  - [Scarica Teams](https://www.microsoft.com/microsoft-teams/download-app).

---
