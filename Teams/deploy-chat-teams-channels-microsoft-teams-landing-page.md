---
title: Chat, team, canali e app in Microsoft Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Include istruzioni dettagliate per configurare le impostazioni per chat, team, app e canali in Microsoft Teams.
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: cefcb240e27f5934538c88f5316181be25f24a60
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031232"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, team, canali e app in Microsoft Teams

Teams offre un'esperienza di collaborazione predefinita che la maggior parte delle organizzazioni trova perfetta per le proprie esigenze. Questo articolo è utile per decidere se modificare una o più impostazioni predefinite in base al profilo o ai requisiti dell'organizzazione e illustra la procedura per ogni modifica. Le impostazioni sono state suddivise in due gruppi, a partire dal set di base di [modifiche più probabili](#core-deployment-decisions). Il secondo gruppo include le [impostazioni aggiuntive](#additional-deployment-decisions)che si vuole configurare in base alle esigenze dell’organizzazione.

Per iniziare, guardare il breve video sulle chat, i team e i canali di Teams (4:30 minuti):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

*Novità di novembre 2019*
 - È ora possibile [usare Advisor per Teams (anteprima) per distribuire Microsoft Teams](use-advisor-teams-roll-out.md). Advisor per Teams (anteprima) guida l'implementazione di Teams. Valuta l'ambiente di Microsoft 365 o Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams.
 - [Canale YouTube dedicato a Microsoft Teams Essentials for IT](https://aka.ms/MicrosoftTeamsforIT), che include brevi video (8-10 minuti) per illustrare come distribuire, configurare e gestire Teams.

> [!TIP]
> È consigliabile includere nell'implementazione iniziale di Teams le app in primo piano, ad esempio Planner. Aggiungere ulteriori [app, bot e connettori](deploy-apps-microsoft-teams-landing-page.md) per incentivare l'adozione di Teams.

 > [!Note]
 > Per informazioni dettagliate sulle funzionalità di Teams su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Prerequisiti per la distribuzione della chat

Prima di implementare Teams nell'organizzazione, è necessario verificare che l'ambiente sia pronto. Consultare [Preparare la rete dell'organizzazione per Teams](prepare-network.md) e apportare le modifiche necessarie per l'ambiente.

|Chiedersi|Azione |
|------------|-------|
|L'organizzazione è pronta per la distribuzione di Teams?|Per rispondere a questa domanda, vedere: <ul><li>[Preparare la rete dell'organizzazione per Teams](prepare-network.md)</li><li>[URL e intervalli di indirizzi IP](office-365-urls-ip-address-ranges.md)</li><li>[Pianificare i gruppi di Microsoft 365 durante la creazione di team](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Di seguito sono illustrate le impostazioni relative a chat, team e canali che la maggior parte delle organizzazioni vorrà modificare se le impostazioni predefinite non sono adeguate.

### <a name="teams-administrators"></a>Amministratori di Teams

Teams include un set di ruoli di amministratore personalizzati che è possibile usare per gestire Teams per l'organizzazione. I ruoli forniscono varie funzionalità agli amministratori.

| Chiedersi | Azione |
|--------------|--------|
|A chi sarà assegnato il ruolo di amministratore delle comunicazioni di Teams?|Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md).|
|A chi sarà assegnato il ruolo di tecnico del supporto delle comunicazioni di Teams?|Per assegnare i ruoli amministrativi, vedere [Assegnazione di ruoli di amministratore e senza privilegi di amministratore agli utenti con Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A chi sarà assegnato il ruolo di specialista del supporto delle comunicazioni di Teams?||
|||

### <a name="teams-owners-and-members"></a>Proprietari e membri di Teams

Oltre ai ruoli di amministratore, Teams consente di assegnare ruoli utente di proprietario e membro e di concedere, in modo selettivo, a questi ruoli capacità di moderatore (se è stata configurata la moderazione) per controllare chi può eseguire determinate azioni all'interno di un canale. La moderazione permette di controllare chi può iniziare nuovi post in un canale, aggiungere e rimuovere membri del team come moderatori e controllare se i membri del team possono rispondere ai messaggi esistenti nel canale.

|Chiedersi|Azione |
|------------|-------|
|A chi è opportuno assegnare ogni ruolo? | Per confrontare le funzionalità di ogni ruolo, vedere [Assegnare proprietari, moderatori e membri dei team in Microsoft Teams](assign-roles-permissions.md).
|Come si assegna un ruolo utente? | Per assegnare o modificare un ruolo, vedere [Assegnare un ruolo utente](assign-roles-permissions.md#assign-a-user-role).
|È necessario controllare chi può pubblicare e rispondere in un canale? | Per configurare la moderazione, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Criteri di messaggistica

I criteri di messaggistica controllano le funzionalità di messaggistica disponibili in chat e canali per gli utenti di Teams. Ad esempio, chi può modificare ed eliminare i messaggi inviati, chi può usare la chat, chi può usare i meme nelle conversazioni e altro ancora. Per impostazione predefinita, agli utenti è assegnato il criterio di messaggistica globale e tutte le funzionalità sono **attivate**. È possibile usare il criterio globale predefinito o creare uno o più criteri di messaggistica personalizzati per gli utenti dell'organizzazione. 

|Chiedersi|Azione |
|------------|-------|
|Il criterio di messaggistica globale verrà personalizzato?|Per informazioni sull'uso dell'interfaccia di amministrazione di Microsoft Teams per modificare il criterio di messaggistica globale o per aggiungere nuovi criteri, vedere [Gestire i criteri di messaggistica in Teams](messaging-policies-in-teams.md).|
|Sono necessari più criteri di messaggistica?|Per creare e assegnare un criterio di messaggistica in PowerShell, vedere [Esempio di script di PowerShell - Creare e assegnare un criterio di messaggistica](scripts/powershell-script-teams-messaging-policy-edu.md).|
|Come si determina a quali gruppi di utenti sono assegnati i vari criteri di messaggistica?|Per informazioni sui cmdlet CsTeamsMessagingPolicy, vedere [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).|
||| 

### <a name="external-access"></a>Accesso esterno

L'accesso esterno, in precedenza noto come federazione, consente agli utenti di Teams e Skype for Business di comunicare con utenti esterni all'organizzazione. Attivando questa impostazione e aggiungendo domini all'elenco di quelli consentiti, gli utenti potranno comunicare con utenti di altri domini e organizzazioni. L'accesso esterno è diverso dall'accesso guest per il fatto che le autorizzazioni di accesso vengono assegnate a un intero dominio, non a un singolo utente. L'accesso esterno è disattivato per impostazione predefinita.

|Chiedersi|Azione |
|------------|-------|
|<ul><li>L'accesso esterno per l'organizzazione verrà attivato?</li><li>In caso affermativo, verranno poste restrizioni rispetto ai domini con cui l'organizzazione può comunicare?</li></ul> |<br>Per attivare l'accesso esterno, vedere [Pianificare l'accesso esterno](manage-external-access.md#plan-for-external-access).|
|||

### <a name="guest-access"></a>Accesso guest

L'accesso guest in Teams consente a utenti esterni all'organizzazione di accedere a team e canali. Le impostazioni di accesso guest consentono di controllare quali funzionalità possono essere usate o meno dagli utenti guest. Per altre informazioni, vedere [Accesso guest in Teams](https://docs.microsoft.com/microsoftteams/guest-access).

> [!NOTE]
> Per altre informazioni sull'accesso esterno e l'accesso guest, vedere [Comunicare con utenti di altre organizzazioni in Microsoft Teams](communicate-with-users-from-other-organizations.md)


|Chiedersi|Azione |
|------------|-------|
|L'accesso guest per l'organizzazione verrà attivato?|Per attivare l'accesso guest, vedere [Attivare o disattivare l'accesso guest in Teams](set-up-guests.md).|
|In caso affermativo, le funzionalità disponibili per gli utenti guest nell'organizzazione verranno personalizzate?|Per personalizzare la disponibilità delle funzionalità di accesso guest, vedere [Autorizzare l'accesso guest in Teams](teams-dependencies.md).|
|||

### <a name="teams-settings"></a>Impostazioni di Teams

Le impostazioni di Teams consentono di configurare i team per funzionalità come l'integrazione della posta elettronica, le opzioni di archiviazione nel cloud, la scheda Organizzazione, la configurazione dei dispositivi della sala riunioni e l'ambito di ricerca. Le modifiche apportate a queste impostazioni si applicano a tutti i team dell'organizzazione. Per altre informazioni, vedere [Impostazioni di Teams](enable-features-office-365.md#teams-settings).

|Chiedersi|Azione |
|------------|-------|
|Le impostazioni di Teams dell'organizzazione verranno personalizzate? | Per informazioni sulle impostazioni di Teams e su come personalizzarle, vedere [Impostazioni di Teams](enable-features-office-365.md#teams-settings).|
|||

### <a name="teams-clients"></a>Client di Teams

Teams supporta numerosi client Web, desktop e per dispositivi mobili e la configurazione predefinita consente agli utenti di scegliere i client che preferiscono. Per altre informazioni, vedere [Ottenere client per Teams](get-clients.md).

|Chiedersi|Azione |
|------------|-------|
|La disponibilità di client di Teams per l'organizzazione verrà personalizzata?|Vedere [Requisiti hardware per l'app Teams](hardware-requirements-for-the-teams-app.md). |
|Le impostazioni dei client di Teams per l'organizzazione verranno personalizzate?|Vedere [Installare Teams con MSI](msi-deployment.md).|
|||

### <a name="teams-usage-reporting"></a>Report sull'utilizzo di Teams

I ruoli Amministratore globale, Amministratore del servizio Teams e Lettore di report possono visualizzare i report sull'utilizzo di Teams. Per altre informazioni, vedere [Analisi di utilizzo di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics).

|Chiedersi|Azione |
|------------|-------|
|<br> Chi ha bisogno di vedere i report sull'utilizzo di Teams? L'utente dispone del ruolo corretto per farlo? |<ul><li>Se l'utente non è un amministratore, [assegnare il ruolo Lettore di report](teams-activity-reports.md#reports-reader-role).</li><li>Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere [Ruoli e autorizzazioni](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Visualizzare e assegnare i ruoli](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal). |
|||

### <a name="teams-default-apps"></a>App predefinite di Teams 

Teams offre diverse app prodotte direttamente da Microsoft e di terze parti per coinvolgere gli utenti, supportare la produttività e integrare i servizi commerciali di uso comune in Teams. Le app si possono scaricare dallo Store di Teams. 

Per altre informazioni su come implementare e gestire le app in Teams, vedere le linee guida dettagliate per [app, bot e connettori](deploy-apps-microsoft-teams-landing-page.md).

## <a name="additional-deployment-decisions"></a>Ulteriori decisioni per la distribuzione

Può essere utile modificare queste impostazioni in base alle esigenze e alla configurazione dell'organizzazione.

### <a name="teams-licensing"></a>Licenze di Teams

Teams è incluso in molte licenze di Microsoft 365 o Office 365. Per altre informazioni sulle licenze di Teams, vedere [Descrizione del servizio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

|Chiedersi|Azione |
|------------|-------|
|Gli utenti hanno le licenze necessarie per usare tutte le funzionalità di Teams che si intende implementare? | Per altre informazioni sui requisiti di licenza, vedere [Descrizione del servizio Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).|
|||

### <a name="exchange-and-sharepoint-interoperability"></a>Interoperabilità tra Exchange e SharePoint

Per usufruire dell'esperienza completa di Teams, è necessario che ogni utente sia abilitato per la creazione di gruppi di Microsoft 365, Exchange Online e SharePoint Online. Gli articoli seguenti contengono informazioni sulle cassette postali di Exchange ospitate in vari ambienti, sull'interazione tra Exchange e Teams e considerazioni analoghe per SharePoint e OneDrive for Business.

|Chiedersi|Azione |
|------------|-------|
| Sarà possibile distribuire le funzionalità di Teams necessarie con le distribuzioni correnti di Exchange e SharePoint? |Per altre informazioni su Exchange e SharePoint in Teams, vedere:<ul><li> [Modalità di interazione tra Exchange e Teams](exchange-teams-interact.md)</li><li>[Modalità di interazione di SharePoint Online e OneDrive for Business con Teams](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a>Limiti e specifiche per Teams 

Quando si pianifica una distribuzione aziendale di Teams, è necessario tenere conto di eventuali limitazioni e specifiche pertinenti, ad esempio il numero massimo di membri di un team, il numero massimo di team che un utente può creare e così via.

|Chiedersi|Azione |
|------------|-------|
| Quali limiti sono probabili limiti di cui si dovrà tenere conto nell'implementazione di Teams? | Per altre informazioni, vedere [Limiti e specifiche per Teams](limits-specifications-teams.md). |
|||

### <a name="urls-and-ports"></a>URL e porte

Le organizzazioni che mantengono un controllo granulare sul traffico Internet devono leggere [URL e intervalli di indirizzi IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) per un elenco aggiornato degli URL, degli indirizzi IP, delle porte e dei protocolli che occorre configurare correttamente per Teams. Microsoft migliora costantemente i servizi di Office 365 e Microsoft 365 e aggiunge continuamente nuove funzionalità, pertanto le porte, gli URL e gli indirizzi IP necessari potrebbero cambiare nel corso del tempo. È consigliabile sottoscrivere la pagina tramite RSS per ricevere notifiche quando queste informazioni vengono aggiornate o modificate. Assicurarsi almeno di aver aperto le porte elencate in precedenza in [Prerequisiti per la distribuzione della chat](#chat-deployment-prerequisites).

|Chiedersi|Azione |
|------------|-------|
| È necessario usare regole di accesso a Internet per consentire agli utenti di usare Teams o è sufficiente aprire le porte obbligatorie minime? | Per altre informazioni, vedere [URL e intervalli di indirizzi IP](office-365-urls-ip-address-ranges.md).|
|||

### <a name="governance-naming-conventions-who-can-create-teams"></a>Governance (convenzioni di denominazione, utenti autorizzati a creare team)

L'organizzazione potrebbe richiedere l'implementazione di controlli sulle modalità di denominazione e classificazione dei team, sugli utenti che possono creare team e sulla scadenza, la conservazione e l'archiviazione dei team. La gestione di questi aspetti è detta governance. È possibile usare Azure Active Directory (Azure AD) per configurare ognuna di queste aree.


| Chiedersi | Azione |
|--------------|--------|
|Sarà necessario implementare controlli su chi può creare team?| Vedere [Pianificare la governance in Teams](plan-teams-governance.md).|
|Sarà necessario implementare controlli sulla denominazione dei team?|Vedere [Applicare criteri di denominazione per i gruppi di Microsoft 365 in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).|
|||

### <a name="teams-application-policy-side-rail-control"></a>Criteri per le applicazioni di Teams (controllo della barra laterale)

Un'app ancorata compare nella barra laterale di Teams. Creando criteri per le applicazioni di Teams, è possibile preconfigurare set di app di Teams aggiunte per personalizzare Teams per gruppi di utenti selezionati. L'opzione **Consenti app esterne in Microsoft Teams** è attivata per impostazione predefinita.

| Chiedersi | Azione |
|--------------|--------|
|È opportuno creare set preconfigurati di applicazioni di Team aggiunte? | Vedere [Impostazioni di amministrazione per le app in Teams](admin-settings.md).|
|Come si decide a quali gruppi assegnare questi set di app?|Vedere [Autorizzazioni e considerazioni sulle app](app-permissions.md).|
|||

### <a name="archiving-and-compliance"></a>Archiviazione e conformità 

L'organizzazione potrebbe richiedere l'implementazione di controlli sul modo in cui vengono archiviati i team e sui tipi di dati conservati in determinati tipi di team. Vedere [Panoramica sulla sicurezza e conformità in Teams](security-compliance-overview.md) per informazioni sulle impostazioni di Teams attivate per impostazione predefinita.

| Chiedersi | Azione |
|--------------|--------|
|Sarà necessario configurare la conservazione dei team?|Per configurare i criteri di conservazione, vedere [Criteri di conservazione in Teams](retention-policies.md).|
|Sarà necessario configurare l'archiviazione dei team?|Per archiviare o ripristinare un team, vedere [Archiviare o ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Sarà necessario configurare ulteriori impostazioni di conformità?|Per altre informazioni in proposito, vedere [Panoramica sulla sicurezza e conformità in Teams](security-compliance-overview.md).|
|||

### <a name="conditional-access"></a>Accesso condizionale 

Teams si basa principalmente su Exchange Online, SharePoint Online e Skype for Business Online per gli scenari di produttività di base, tra cui riunioni, calendari, chat di interoperabilità e condivisione di file. I criteri di accesso condizionale impostati per queste app cloud si applicano a Teams quando un utente esegue direttamente l'accesso a Teams in qualsiasi client. I criteri di accesso condizionale impostati per l'app Teams cloud controllano aspetti come ad esempio se gli utenti possono accedere ai servizi di Teams da determinate reti.

| Chiedersi | Azione |
|--------------|--------|
|<br>Sarà necessario configurare l'accesso condizionale per Teams?|<ul><li>Per informazioni sul funzionamento dei criteri di accesso, vedere [Come funzionano i criteri di accesso condizionale per Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>Per configurare l'autenticazione a più fattori (MFA) per Teams, vedere:<ul><li>[Guida introduttiva: Richiedere MFA per app specifiche con l'accesso condizionale di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Informazioni di riferimento sulle impostazioni di accesso condizionale di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a>Education (EDU) 

I professionisti IT che lavorano nel settore dell'istruzione possono usufruire di Teams for Education, che include numerose funzionalità personalizzate per soddisfare scenari specifici per studenti, istituti di istruzione e il settore nel suo complesso.

| Chiedersi | Azione |
|--------------|--------|
|Si useranno modelli di Teams specifici per il settore istruzione? |Per altre informazioni su Teams for Education, vedere [Domande frequenti sulla governance di Microsoft Education per amministratori](plan-teams-governance-edu.md).|
|Verrà distribuita la ricerca per ambito?|Per configurare Teams for Education, vedere [Guida introduttiva - Amministratori di Teams for Education](teams-quick-start-edu.yml).|
|Teams verrà integrato con il servizio School Data Sync per eseguire il provisioning degli account utente?|[Risorse di Teams per l'istruzione per amministratori](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a>Considerazioni su Government - GCC

L'uso di Office 365 for Government - GCC (Government Community Cloud) è appropriato per le esigenze dei professionisti IT che si occupano di distribuzioni di Office 365 in entità governative federali, statali, locali, comunali e territoriali degli Stati Uniti o altre entità che gestiscono dati soggetti a requisiti e normative.

| Chiedersi | Azione |
|--------------|--------|
| Sarà necessario distribuire Teams in un ambiente Office 365 Government - GCC? | Per considerazioni sulla distribuzione, vedere [Pianificare le distribuzioni di Office 365 Government - GCC](plan-for-government-gcc.md).|
|||

## <a name="next-steps"></a>Passaggi successivi
- [Favorire l'adozione](adopt-microsoft-teams-landing-page.md) di chat, team, canali e app.
- Includere nell'implementazione iniziale di Teams le app in primo piano, ad esempio Planner. Aggiungere ulteriori [app, bot e connettori](deploy-apps-microsoft-teams-landing-page.md) per incentivare l'adozione di Teams.
- [Implementare riunioni e conferenze](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementare Cloud Voice](cloud-voice-landing-page.md)
