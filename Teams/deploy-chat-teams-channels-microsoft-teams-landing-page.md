---
title: Chat, team, canali e app in Microsoft Teams
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Include istruzioni dettagliate per configurare le impostazioni per chat, team, app e canali in Microsoft Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
- seo-marvel-apr2020
- seo-marvel-may2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10063b2b6c8c0f92de8d949578133b2577ff6d9f
ms.sourcegitcommit: ed7d3b12d4bfe48863de873360c2ae90bbb15530
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69194917"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, team, canali e app in Microsoft Teams

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

Per iniziare, guardare il breve video sulle chat, i team e i canali di Teams (4:30 minuti):

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj?autoplay=false]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> È consigliabile includere nell'implementazione iniziale di Teams le app in primo piano, ad esempio Planner. Aggiungi altre [app di Teams](deploy-apps-microsoft-teams-landing-page.md) mentre guidi l'adozione di Teams.

 > [!Note]
 > Per informazioni dettagliate sulle funzionalità di Teams su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Prerequisiti per la distribuzione della chat

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|Chiedersi|Azione |
|------------|-------|
|L'organizzazione è pronta per la distribuzione di Teams?|Per rispondere a questa domanda, vedere: <ul><li>[Preparare la rete dell'organizzazione per Teams](prepare-network.md)</li><li>[URL e intervalli di indirizzi IP](office-365-urls-ip-address-ranges.md)</li><li>[Pianificare i gruppi di Microsoft 365 durante la creazione di team](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Di seguito sono illustrate le impostazioni relative a chat, team e canali che la maggior parte delle organizzazioni vorrà modificare se le impostazioni predefinite non sono adeguate.

### <a name="teams-administrators"></a>Amministratori di Teams

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| Chiedersi | Azione |
|--------------|--------|
|A chi sarà assegnato il ruolo di amministratore delle comunicazioni di Teams?|Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md).|
|A chi sarà assegnato il ruolo di tecnico del supporto delle comunicazioni di Teams?|Per assegnare i ruoli amministrativi, vedere [Assegnazione di ruoli di amministratore e senza privilegi di amministratore agli utenti con Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A chi sarà assegnato il ruolo di specialista del supporto delle comunicazioni di Teams?||

### <a name="teams-owners-and-members"></a>Proprietari e membri di Teams

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|Chiedersi|Azione |
|------------|-------|
|A chi è opportuno assegnare ogni ruolo? | Per confrontare le funzionalità di ogni ruolo, vedere [Assegnare proprietari, moderatori e membri dei team in Microsoft Teams](assign-roles-permissions.md).
|Come si assegna un ruolo utente? | Per assegnare o modificare un ruolo, vedere [Assegnare un ruolo utente](assign-roles-permissions.md).
|È necessario controllare chi può pubblicare e rispondere in un canale? | Per configurare la moderazione, vedere [Configurare e gestire la moderazione dei canali in Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Criteri di messaggistica

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.

|Chiedersi|Azione |
|------------|-------|
|Il criterio di messaggistica globale verrà personalizzato?|Per informazioni sull'uso dell'interfaccia di amministrazione di Microsoft Teams per modificare il criterio di messaggistica globale o per aggiungere nuovi criteri, vedere [Gestire i criteri di messaggistica in Teams](messaging-policies-in-teams.md).|
|Sono necessari più criteri di messaggistica?|Per creare e assegnare un criterio di messaggistica in PowerShell, vedere [Esempio di script di PowerShell - Creare e assegnare un criterio di messaggistica](scripts/powershell-script-teams-messaging-policy-edu.md).|
|Come si determina a quali gruppi di utenti sono assegnati i vari criteri di messaggistica?|Per informazioni sui cmdlet CsTeamsMessagingPolicy, vedere [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).|

### <a name="external-access"></a>Accesso esterno

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|Chiedersi|Azione |
|------------|-------|
|<ul><li>Disattivo le riunioni esterne e la chat per la mia organizzazione?</li><li>In caso affermativo, verranno poste restrizioni rispetto ai domini con cui l'organizzazione può comunicare?</li></ul> |<br>Per attivare o disattivare la riunione esterna e la chat, vedere [Gestire riunioni esterne e chat](manage-external-access.md).|

### <a name="guest-access"></a>Accesso guest

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> Per altre informazioni sull'accesso esterno e l'accesso guest, vedi [Comunicare con utenti di altre organizzazioni in Microsoft Teams](communicate-with-users-from-other-organizations.md)

|Chiedersi|Azione |
|------------|-------|
|Disattivare l'accesso guest per l'organizzazione?|Per attivare o disattivare l'accesso guest, vedere [Attivare o disattivare l'accesso guest in Teams](set-up-guests.md).|
|In caso affermativo, le funzionalità disponibili per gli utenti guest nell'organizzazione verranno personalizzate?|Per personalizzare la disponibilità delle funzionalità di accesso guest, vedere [Autorizzare l'accesso guest in Teams](teams-dependencies.md).|

### <a name="private-channels"></a>Canali privati

I canali privati consentono a un sottoinsieme di membri del team di collaborare in uno spazio privato non visibile o accessibile agli altri membri del team. Tutti gli utenti, inclusi gli utenti guest, possono essere aggiunti come membri a un canale privato, purché siano già membri del team.

|Chiedersi|Azione |
|------------|-------|
|Consentire ai proprietari e ai membri del team di creare canali privati?|Per impostare i criteri dei canali privati per l'organizzazione, vedere [Gestire i criteri dei canali in Microsoft Teams](teams-policies.md)|

### <a name="shared-channels"></a>Canali condivisi

I canali condivisi consentono di aggiungere a un canale, le persone che non sono membri di un team. Sono incluse le persone esterne all'organizzazione. I canali condivisi offrono vantaggi rispetto all'accesso guest in quanto le persone esterne all'organizzazione non necessitano di un account guest nella directory.

|Chiedersi|Azione |
|------------|-------|
|Quando si usano i canali condivisi rispetto all'accesso guest?|Vedere [Canali condivisi in Microsoft Teams](shared-channels.md).|
|<ul><li>Consentire ai proprietari del team di creare canali condivisi?</li><li>Consentire ai proprietari del team di condividere canali con persone esterne all'organizzazione?</li><li>Consentirò agli utenti di partecipare a canali condivisi esterni all'organizzazione?</li></ul> |<br>Per impostare i criteri dei canali condivisi per l'organizzazione, vedere [Gestire i criteri dei canali in Microsoft Teams](teams-policies.md).|

### <a name="teams-settings"></a>Impostazioni di Teams

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|Chiedersi|Azione |
|------------|-------|
|Le impostazioni di Teams dell'organizzazione verranno personalizzate? | Per informazioni sulle impostazioni di Teams e su come personalizzarle, vedere [Impostazioni di Teams](enable-features-office-365.md#teams-settings).|

### <a name="teams-clients"></a>Client di Teams

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|Chiedersi|Azione |
|------------|-------|
|La disponibilità di client di Teams per l'organizzazione verrà personalizzata?|Vedere [Requisiti hardware per l'app Teams](hardware-requirements-for-the-teams-app.md). |
|Le impostazioni dei client di Teams per l'organizzazione verranno personalizzate?|Vedere [Installare Teams con MSI](msi-deployment.md).|

### <a name="teams-usage-reporting"></a>Report sull'utilizzo di Teams

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|Chiedersi|Azione |
|------------|-------|
|<br> Chi ha bisogno di vedere i report sull'utilizzo di Teams? L'utente dispone del ruolo corretto per farlo? |<ul><li>Se l'utente non è un amministratore, [assegnare il ruolo Lettore di report](teams-activity-reports.md#reports-reader-role).</li><li>Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere [Ruoli e autorizzazioni](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Visualizzare e assegnare i ruoli](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).|

### <a name="teams-default-apps"></a>App predefinite di Teams

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.

Per altre informazioni sulla distribuzione e la gestione delle app in Teams, vedere le linee guida dettagliate per [la gestione delle app](deploy-apps-microsoft-teams-landing-page.md) .

## <a name="additional-deployment-decisions"></a>Ulteriori decisioni per la distribuzione

Può essere utile modificare queste impostazioni in base alle esigenze e alla configurazione dell'organizzazione.

### <a name="teams-licensing"></a>Licenze di Teams

Teams è incluso in molte licenze di Microsoft 365.

|Chiedersi|Azione |
|------------|-------|
|Gli utenti hanno le licenze necessarie per usare tutte le funzionalità di Teams che si intende implementare? | Per altre informazioni sui requisiti di licenza, vedere [Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description).|

### <a name="exchange-and-sharepoint-interoperability"></a>Interoperabilità con Exchange e SharePoint

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|Chiedersi|Azione |
|------------|-------|
| Sarà possibile distribuire le funzionalità di Teams necessarie con le distribuzioni correnti di Exchange e SharePoint? |Per altre informazioni su Exchange e SharePoint in Teams, vedere:<ul><li> [Modalità di interazione tra Exchange e Teams](exchange-teams-interact.md)</li><li>[In che modo SharePoint Online e OneDrive interagiscono con Teams](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Limiti e specifiche per Teams

Quando si pianifica una distribuzione aziendale di Teams, è necessario tenere conto di eventuali limitazioni e specifiche pertinenti, ad esempio il numero massimo di membri di un team, il numero massimo di team che un utente può creare e così via.

|Chiedersi|Azione |
|------------|-------|
| Quali limiti sono probabili limiti di cui si dovrà tenere conto nell'implementazione di Teams? | Per altre informazioni, vedere [Limiti e specifiche per Teams](limits-specifications-teams.md). |

### <a name="urls-and-ports"></a>URL e porte

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|Chiedersi|Azione |
|------------|-------|
| È necessario usare regole di accesso a Internet per consentire agli utenti di usare Teams o è sufficiente aprire le porte obbligatorie minime? | Per altre informazioni, vedere [URL e intervalli di indirizzi IP](office-365-urls-ip-address-ranges.md).|

### <a name="governance-naming-conventions-who-can-create-teams"></a>Governance (convenzioni di denominazione, utenti autorizzati a creare team)

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.

| Chiedersi | Azione |
|--------------|--------|
|Sarà necessario implementare controlli su chi può creare team?| Vedere [Pianificare la governance in Teams](plan-teams-governance.md).|
|Sarà necessario implementare controlli sulla denominazione dei team?|Vedere [Applicare criteri di denominazione per i gruppi di Microsoft 365 in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy).|

### <a name="teams-application-policy-side-rail-control"></a>Criteri per le applicazioni di Teams (controllo della barra laterale)

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| Chiedersi | Azione |
|--------------|--------|
|È opportuno creare set preconfigurati di applicazioni di Team aggiunte? | Vedere [Impostazioni di amministrazione per le app in Teams](admin-settings.md).|
|Come si decide a quali gruppi assegnare questi set di app?|Vedere [Autorizzazioni e considerazioni sulle app](app-permissions.md).|

### <a name="archiving-and-compliance"></a>Archiviazione e conformità

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| Chiedersi | Azione |
|--------------|--------|
|Sarà necessario configurare la conservazione dei team?|Per configurare i criteri di conservazione, vedere [Criteri di conservazione in Teams](retention-policies.md).|
|Sarà necessario configurare l'archiviazione dei team?|Per archiviare o ripristinare un team, vedere [Archiviare o ripristinare un team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Sarà necessario configurare ulteriori impostazioni di conformità?|Per altre informazioni in proposito, vedere [Panoramica sulla sicurezza e conformità in Teams](security-compliance-overview.md).|

### <a name="conditional-access"></a>Accesso condizionale

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| Chiedersi | Azione |
|--------------|--------|
|<br>Sarà necessario configurare l'accesso condizionale per Teams?|<ul><li>Per informazioni sul funzionamento dei criteri di accesso, vedere [Come funzionano i criteri di accesso condizionale per Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>Per configurare l'autenticazione a più fattori (MFA) per Teams, vedere:<ul><li>[Guida introduttiva: Richiedere MFA per app specifiche con l'accesso condizionale di Azure Active Directory](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Informazioni di riferimento sulle impostazioni di accesso condizionale di Azure Active Directory](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>Education (EDU)

I professionisti IT che lavorano nel settore dell'istruzione possono usufruire di Teams for Education, che include numerose funzionalità personalizzate per soddisfare scenari specifici per studenti, istituti di istruzione e il settore nel suo complesso.

| Chiedersi | Azione |
|--------------|--------|
|Si useranno modelli di Teams specifici per il settore istruzione? |Per altre informazioni su Teams for Education, vedere [Domande frequenti sulla governance di Microsoft Education per amministratori](plan-teams-governance-edu.md).|
|Verrà distribuita la ricerca per ambito?|Per configurare Teams for Education, vedere [Guida introduttiva - Amministratori di Teams for Education](teams-quick-start-edu.yml).|
|Teams verrà integrato con il servizio School Data Sync per eseguire il provisioning degli account utente?|[Risorse di Teams per l'istruzione per amministratori](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>Considerazioni su Government - GCC

L'uso di Office 365 for Government - GCC (Government Community Cloud) è appropriato per le esigenze dei professionisti IT che si occupano di distribuzioni di Office 365 in entità governative federali, statali, locali, comunali e territoriali degli Stati Uniti o altre entità che gestiscono dati soggetti a requisiti e normative.

| Chiedersi | Azione |
|--------------|--------|
| Sarà necessario distribuire Teams in un ambiente Office 365 Government - GCC? | Per considerazioni sulla distribuzione, vedere [Pianificare le distribuzioni di Office 365 Government - GCC](plan-for-government-gcc.md).|

## <a name="next-steps"></a>Passaggi successivi

- [Favorire l'adozione](adopt-microsoft-teams-landing-page.md) di chat, team, canali e app.
- Includere nell'implementazione iniziale di Teams le app in primo piano, ad esempio Planner. Aggiungi [un'altra app Teams](deploy-apps-microsoft-teams-landing-page.md) mentre guidi l'adozione di Teams.
- [Implementare riunioni e conferenze](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementare Cloud Voice](cloud-voice-landing-page.md)
