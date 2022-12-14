---
title: Controllare chi può ignorare la sala di attesa della riunione in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come usare la sala di attesa della riunione in Microsoft Teams per consentire solo a determinati partecipanti alla riunione di partecipare direttamente alla riunione.
ms.openlocfilehash: c9073209a329c0d97c7d1951c02194d9924eea76
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392740"
---
# <a name="control-who-can-bypass-the-meeting-lobby-in-microsoft-teams"></a>Controllare chi può ignorare la sala di attesa della riunione in Microsoft Teams

La sala di attesa della riunione di Teams è un modo per impedire a determinati tipi di partecipanti alla riunione di partecipare a una riunione finché un organizzatore, un co-organizzatore o un relatore non li ammette. Quando un partecipante entra nella sala di attesa, gli organizzatori, i co-organizzatori e i relatori ricevono una notifica e possono scegliere di aggiungerli alla riunione o meno.

Usando le impostazioni della sala di attesa nell'interfaccia di amministrazione di Teams, è possibile creare impostazioni predefinite per i tipi di partecipanti alla riunione che possono evitare la sala di attesa e i partecipanti che devono attendere l'autorizzazione alla riunione. È possibile controllare in che modo i seguenti tipi di partecipanti interagiscono con la sala di attesa:

- Organizzatore e co-organizzatori della riunione
- Persone nell'organizzazione
- Utenti guest
- Persone nelle organizzazioni attendibili
- Partecipanti anonimi

Le identità delle persone che partecipano alle riunioni vengono verificate da Microsoft 365, a meno che il partecipante non sia anonimo. Non è possibile verificare i partecipanti anonimi.

## <a name="prerequisites-for-meeting-with-people-outside-your-organization"></a>Prerequisiti per una riunione con persone esterne all'organizzazione

In Teams sono disponibili diverse impostazioni che controllano se le persone esterne all'organizzazione possono interagire con Teams. Le impostazioni seguenti devono essere abilitate per consentire alle persone esterne all'organizzazione di partecipare alle riunioni:

- [L'accesso guest in Teams](guest-access.md) deve essere abilitato affinché i guest possano partecipare alle riunioni.
- [L'accesso esterno](manage-external-access.md) deve essere abilitato affinché le persone nelle organizzazioni attendibili possano partecipare alle riunioni. È necessario configurare un trust reciproco tra l'organizzazione e l'organizzazione esterna e abilitare per l'accesso esterno l'organizzatore della riunione dell'organizzazione, nonché tutti i partecipanti dell'organizzazione esterna.
- Per consentire ai partecipanti anonimi di partecipare alle riunioni, sia **gli utenti anonimi possono partecipare** all'impostazione della riunione (a livello di organizzazione) che i criteri (per l'organizzatore che sta creando la riunione) devono essere **attivati** .

Se una di queste impostazioni è disattivata, quel tipo di partecipante esterno non potrà partecipare alle riunioni indipendentemente dalle impostazioni della sala di attesa.

## <a name="overview-of-lobby-settings-and-policies"></a>Panoramica delle impostazioni e dei criteri della sala di attesa

La tabella seguente mostra i criteri delle riunioni di Teams che influiscono sul modo in cui i partecipanti alla riunione interagiscono con la sala di attesa.

|Impostazione|Descrizione|
|:------|:----------|
|**Gli utenti anonimi e i chiamanti possono avviare una riunione**|Si tratta di una politica per organizzatore che consente le riunioni senza leader. Questa impostazione controlla se i partecipanti anonimi e gli utenti connessi con accesso automatico possono partecipare alla riunione senza che un partecipante verificato partecipi. Questa impostazione si applica solo quando **l'opzione Chi può ignorare la sala di attesa** è impostata su **Tutti**. Se l'impostazione **Utenti anonimi possono partecipare a un'organizzazione o a una riunione** è **Disattivata**, questa impostazione si applica solo ai chiamanti che accedono con accesso esterno. Per impostazione predefinita, questa impostazione è disattivata per evitare potenziali abusi dei collegamenti alle riunioni da parte di utenti anonimi. <br><br> Mentre è **disattivato**, i partecipanti anonimi e gli utenti connessi con accesso esterno attenderanno nella sala di attesa finché un partecipante verificato (incluso un organizzatore per l'accesso esterno) non accede alla riunione, a quel punto verrà automaticamente ammesso. Dopo l'avvio della riunione, i partecipanti anonimi e gli utenti connessi con accesso radiale parteciperanno automaticamente alla chiamata, anche se l'organizzatore lascia l'organizzazione. <br><br> Se questa impostazione è **attivata**, i partecipanti anonimi e connessi con accesso automatico possono avviare la riunione e parteciparvi senza che sia presente un partecipante verificato.|
|**Persone chiamata in ingresso può ignorare la sala di attesa**|Questo è un criterio per organizzatore. Questa impostazione controlla se le persone che accedono tramite telefono alla riunione direttamente o in attesa nella sala d'attesa. Quando questa impostazione è **disattivata**, gli utenti con accesso esterno attenderanno nella sala d'attesa finché un organizzatore, un co-organizzatore o un relatore non accede alla riunione e non li ammette. Quando questa impostazione è **attivata**, gli utenti che accedono tramite telefono parteciperanno automaticamente alla riunione senza passare dalla sala di attesa. Se **gli utenti anonimi e i chiamanti con accesso esterno possono avviare una riunione** è **Disattivato**, attenderanno nella sala di attesa fino all'inizio della riunione.|
|**Chi può evitare la sala di attesa**|Questo è un criterio per organizzatore. Questa impostazione controlla i tipi di partecipanti (ad eccezione di quelli che accedono tramite telefono) a una riunione direttamente e i tipi di partecipanti che aspettano nella sala di attesa finché non vengono ammessi da un organizzatore, un co-organizzatore o un relatore.|

La tabella seguente mostra in che modo ogni opzione per **Gli utenti autorizzati a ignorare i criteri della sala di attesa** influisce su ogni *tipo di partecipante alla riunione*.

|Valore del criterio:|Tutti|Utenti dell'organizzazione, organizzazioni attendibili e guest|Utenti dell’organizzazione e guest|Utenti dell’organizzazione|Solo le persone invitate|Solo organizzatori e co-organizzatori|
|:--------|:------|:-----|:-----|:------|:-------|:---------------|
|*Organizzatori e co-organizzatori*|Bypass|Bypass|Bypass|Bypass|Bypass|Bypass|
|*Persone nell'organizzazione*|Bypass|Bypass|Bypass|Bypass|Persone che sono stati inviati o inoltrati un invito verranno ignorati; gli altri aspettano nella sala di attesa|Lobby|
|*Utenti guest*|Bypass|Bypass|Bypass|Lobby|Persone che sono stati inviati o inoltrati un invito verranno ignorati; gli altri aspettano nella sala di attesa|Lobby|
|*Persone nelle organizzazioni attendibili*|Bypass|Bypass|Lobby|Lobby|Persone che sono stati inviati o inoltrati un invito verranno ignorati; gli altri aspettano nella sala di attesa|Lobby|
|*Partecipanti anonimi*|Bypass|Lobby|Lobby|Lobby|Lobby|Lobby|

**Solo le persone invitate si** applicano solo ai partecipanti verificati a cui è stato inviato un invito o a cui è stato inoltrato un invito. Gli utenti aggiunti come parte di un gruppo di distribuzione attenderanno nella sala di attesa.

## <a name="choose-who-can-bypass-the-lobby-in-meetings-hosted-by-your-organization"></a>Scegliere chi può ignorare la sala di attesa nelle riunioni ospitate dall'organizzazione

È possibile configurare le impostazioni e i criteri descritti in precedenza nell'interfaccia di amministrazione di Teams. Vedere le sezioni seguenti per indicazioni sulle impostazioni da scegliere per circostanze diverse. Per informazioni sul funzionamento dei criteri delle riunioni, vedere [Gestire i criteri delle riunioni in Microsoft Teams](/microsoftteams/meeting-policies-overview).

> [!Important]
> Gli organizzatori della riunione possono modificare i valori predefiniti scelti per l'Persone l'accesso in **ingresso può ignorare la sala di attesa** e **Chi può ignorare le impostazioni della sala di attesa**. Se è necessario applicare queste impostazioni a un valore specifico, è possibile usare un modello di riunione o un'etichetta di riservatezza (è richiesto Teams Premium).  Per altre informazioni, vedere [Configurare la sala di attesa delle riunioni di Microsoft Teams per le riunioni sensibili](configure-lobby-sensitive-meetings.md).

Per impostare i criteri di partecipazione alle riunioni e di sala di attesa
1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e quindi selezionare **Criteri riunione**.
1. Selezionare il criterio da aggiornare.
1. Nelle sezioni **Partecipanti & guest** aggiornare le impostazioni da modificare:
   - **Consentire a persone anonime di partecipare a una riunione**
   - **Consenti alle persone anonime di avviare una riunione**
   - **Ammettere automaticamente le persone** (chi può ignorare la sala di attesa)
   - **Gli utenti che accedono con chiamata in ingresso possono evitare la sala di attesa**

    ![Screenshot che mostra i criteri di partecipazione alla riunione e di sala di attesa nell'interfaccia di amministrazione di Teams.](media/meeting-join-and-lobby-tac-settings.png)
1. Selezionare **Salva**.

Si noti che l'applicazione delle modifiche può richiedere fino a ventiquattro ore.

Se si vuole consentire l'accesso anonimo alla riunione, verificare che sia attivata anche l'impostazione **Utenti anonimi che possono partecipare a una riunione** .

Per impostare l'impostazione della riunione a livello di organizzazione per l'accesso anonimo alla riunione
1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e quindi selezionare **Impostazioni riunione**.
1. Nella sezione **Partecipanti** impostare **Utenti anonimi che possono partecipare a una riunione** su **Attivato** o **Disattivato**.
    ![Screenshot che mostra le impostazioni di partecipazione alla riunione e sala di attesa nell'interfaccia di amministrazione di Teams.](media/anonymous-users-can-join-meetings-org-setting.png)
1. Selezionare **Salva**.

## <a name="control-access-to-meetings-by-anonymous-participants"></a>Controllare l'accesso alle riunioni da parte di partecipanti anonimi

I partecipanti anonimi sono anonimi perché non hanno eseguito l'accesso a un account che può essere verificato da Microsoft 365. Ad esempio:

- Persone che non hanno effettuato l'accesso a Microsoft 365 con un account aziendale o dell'istituto di istruzione 
- Persone da organizzazioni non attendibili, configurate in [accesso esterno](manage-external-access.md).
- Persone da organizzazioni attendibili ma non attendibili

Se si vuole impedire ai partecipanti anonimi di partecipare completamente alla riunione, è possibile disattivare l'impostazione **Gli utenti anonimi possono partecipare a una riunione** a livello di organizzazione della riunione. È anche possibile disabilitare l'accesso anonimo per specifici organizzatori di riunioni usando i criteri **Per partecipare a una riunione, gli utenti anonimi possono partecipare a una riunione** .

Se si vuole che le persone che partecipano in modalità anonima attendano nella sala di attesa, è possibile impostare **l'impostazione Chi può ignorare i criteri della riunione di sala d'attesa** su qualsiasi impostazione tranne **Tutti**. Questa impostazione non influisce sulle persone che accedono tramite telefono.

Per impostazione predefinita, **gli utenti anonimi e i chiamanti che accedono tramite telefono possono avviare un criterio riunione** è **Disattivato**. Questo significa che i partecipanti anonimi e le persone che chiamano telefonicamente aspetteranno sempre nella sala di attesa se un partecipante verificato non ha ancora avviato la riunione. Anche se è possibile attivare questa impostazione se in alcune circostanze si vuole consentire ai partecipanti anonimi e alle persone che chiamano telefonicamente di avviare le riunioni, è consigliabile lasciarla disattivata.  Quando l'impostazione è attivata, le persone con account non verificati possono avviare le riunioni, incluso l'uso del collegamento alla riunione per tenere riunioni in orari non pianificati.

## <a name="control-access-to-meetings-by-people-dialing-in-by-phone"></a>Controllare l'accesso alle riunioni tramite telefono

Per impostazione predefinita, il Persone accesso esterno **può ignorare il criterio della sala di attesa** è **Disattivato**, ma gli organizzatori della riunione possono modificare questa impostazione quando configurano la riunione. È possibile modificare l'impostazione predefinita aggiornando il Persone l'accesso tramite telefono **può ignorare i criteri della sala di attesa** oppure è possibile applicare un valore specifico usando un modello di riunione.

## <a name="control-access-to-meetings-by-guests-and-people-from-trusted-organizations"></a>Controllare l'accesso alle riunioni da parte di guest e persone di organizzazioni attendibili

Esistono due tipi di persone esterne all'organizzazione che possono partecipare alle riunioni come partecipanti verificati:

- Guest : persone che hanno un [account di collaborazione B2B di Azure Active Directory (Azure AD)](/azure/active-directory/external-identities/what-is-b2b) nell'organizzazione
- Utenti con accesso esterno : persone che dispongono di account Azure AD in un'organizzazione attendibile definita in [Accesso esterno](manage-external-access.md) di Teams

Se si vuole che tutti i partecipanti verificati alla riunione dall'esterno dell'organizzazione aspettino nella sala di attesa, è possibile impostare l'opzione Chi può ignorare i criteri della sala di attesa **su Persone nell'organizzazione** o **Solo organizzatori e co-organizzatori** (purché un guest non sia l'organizzatore o il co-organizzatore). Se si vuole che solo le persone provenienti da organizzazioni attendibili (utenti con accesso esterno) attendano nella sala di attesa, è possibile scegliere **Persone nell'organizzazione e negli utenti guest**.

## <a name="control-access-to-meetings-by-people-without-invitations"></a>Controllare l'accesso alle riunioni da parte di persone senza inviti

Se si vuole consentire solo alle persone che hanno inviti di partecipare direttamente alle riunioni e che tutti gli altri partecipanti devono attendere nella sala di attesa, impostare **Chi può ignorare la sala di attesa** su **Solo le persone invitate**. Persone invitati tramite lista di distribuzione non sono inclusi.

L'impostazione **Solo le persone invitate** include i partecipanti verificati a cui è stato inoltrato l'invito, non solo quelli invitati direttamente dall'organizzatore. Non include le persone che hanno il collegamento per partecipare alla riunione, ma non l'invito stesso e i partecipanti non verificati (anonimi). Devono aspettare nella sala d'attesa.

Si noti che gli organizzatori della riunione possono disabilitare l'inoltro dell'invito alla riunione se vogliono che partecipino alla riunione solo le persone direttamente invitate.

## <a name="control-access-to-meetings-by-non-organizers"></a>Controllare l'accesso alle riunioni da parte di utenti non organizzatori

Se si hanno riunioni in cui vengono condivise informazioni riservate o che sono soggette a requisiti normativi, è consigliabile fare in modo che tutti i partecipanti aspettino nella sala di attesa finché non vengono ammessi da un organizzatore della riunione o da un co-organizzatore. In questo caso, è possibile impostare **Chi può ignorare la sala di attesa** **su Solo organizzatori e co-organizzatori**.

Poiché **Chi può ignorare la sala di attesa** imposta solo un valore predefinito che gli organizzatori della riunione possono modificare, è consigliabile applicare il valore con un'etichetta di riservatezza o un modello di riunione se in quest'area sono previsti requisiti di conformità. Per altre informazioni, vedere [Configurare la sala di attesa delle riunioni di Microsoft Teams per le riunioni sensibili](configure-lobby-sensitive-meetings.md).

## <a name="set-meeting-policies-by-using-powershell"></a>Impostare i criteri delle riunioni con PowerShell

Puoi impostare i criteri di riunione descritti in questo articolo utilizzando il cmdlet [PowerShell Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) con i seguenti parametri:

- [-AllowAnonymousUsersToJoinMeeting](/powershell/module/skype/set-csteamsmeetingpolicy?#-allowanonymoususerstojoinmeeting) per controllare se gli utenti anonimi possono partecipare alle riunioni
- [-AllowPSTNUsersToBypassLobby](/powershell/module/skype/set-csteamsmeetingpolicy#-allowpstnuserstobypasslobby) per controllare se le persone che accedono tramite telefono possono bypassare la sala di attesa
- [-AutoAdmittedUsers](/powershell/module/skype/set-csteamsmeetingpolicy?#-autoadmittedusers) per controllare chi può ignorare la sala di attesa

## <a name="related-topics"></a>Argomenti correlati

[Partecipare a una riunione senza un account di Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Uso dell'interfaccia di amministrazione di Microsoft Teams per configurare i criteri a livello di organizzazione](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[I partecipanti esterni ricevono "Accedi a Teams per partecipare o contattare l'organizzatore della riunione"](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)
