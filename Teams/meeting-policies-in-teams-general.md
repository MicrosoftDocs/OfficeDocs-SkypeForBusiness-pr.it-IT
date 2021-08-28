---
title: Gestire i criteri delle riunioni generali
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni generali dei criteri delle riunioni in Teams.
ms.openlocfilehash: 72cfbc77b6abcf264ddf96f66d3726031a2e31cb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589678"
---
# <a name="meeting-policy-settings---general"></a>Impostazioni dei criteri di riunione - Generale

<a name="bkgeneral"> </a>

Questo articolo descrive le impostazioni dei criteri generali seguenti per Teams riunioni:

- [Consenti l'uso di Riunione immediata nei canali](#allow-meet-now-in-channels)
- [Consenti il componente aggiuntivo per Outlook](#allow-the-outlook-add-in)
- [Consenti la pianificazione delle riunioni di canale](#allow-channel-meeting-scheduling)
- [Consenti la pianificazione di riunioni private](#allow-scheduling-private-meetings)
- [Consenti l'uso di Riunione immediata nelle riunioni private](#allow-meet-now-in-private-meetings)
- [Modalità ruolo relatore designato](#designated-presenter-role-mode)
- [Consenti report impegno](#allow-engagement-report)
- [Consentire la registrazione alla riunione](#allow-meeting-registration)
- [Who possibile registrare](#who-can-register)
- [Provider di riunioni per la modalità Isole](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a>Consenti l'uso di Riunione immediata nei canali

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se un utente può avviare una riunione ad hoc in un canale di Teams. Se si attiva questa opzione,  gli utenti possono fare clic sul pulsante Riunione per avviare una riunione ad hoc o pianificare una riunione nel canale. Il valore predefinito è True.

[![Screenshot che mostra l'icona di Meet now sotto un messaggio ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="allow-the-outlook-add-in"></a>Consenti il componente aggiuntivo per Outlook

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione consente di controllare se è possibile pianificare riunioni di Teams dall'interno di Outlook (Windows, Mac, Web e Mobile).

![Screenshot che mostra la possibilità di pianificare una nuova riunione](media/meeting-policies-outlook-add-in.png)

Se si disattiva questa impostazione, gli utenti non potranno pianificare riunioni di Teams durante la creazione di una nuova riunione in Outlook. In Outlook per Windows, ad esempio, l'opzione **Nuova riunione di Teams** non comparirà sulla barra multifunzione.

## <a name="allow-channel-meeting-scheduling"></a>Consenti la pianificazione delle riunioni di canale

Usare il criterio AllowChannelMeetingScheduling esistente per controllare i tipi di eventi che è possibile creare nei calendari del canale di un team. Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se gli utenti possono pianificare una riunione in un canale di Teams. Per impostazione predefinita, questa impostazione è attivata. 

Se questo criterio è disattivato, gli utenti non potranno creare nuove riunioni del canale. Tuttavia, le riunioni di canale esistenti possono essere modificate dall'organizzatore dell'evento.

L'opzione Pianifica una riunione sarà disabilitata.

![Screenshot che mostra l'opzione Pianifica una riunione in Teams](media/schedule-meeting-option.png)

La selezione del canale è disabilitata.

[![Screenshot che mostra l'opzione del calendario per la selezione del canale in cui si vuole pianificare una riunione. ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Nella pagina dei post del canale, gli elementi seguenti verranno disabilitati:

- Pulsante **Pianifica una riunione** nella casella per comporre una risposta del canale.
  ![Screenshot che mostra l'opzione del calendario per selezionare un canale in cui si vuole pianificare una riunione.](media/schedule-meeting-disabled-in-chat2.png)
  
- Pulsante **Pianifica una riunione** nell'intestazione del canale.
  ![Screenshot che mostra l'opzione del calendario per selezionare un canale tramite il quale si vuole pianificare una riunione.](media/schedule-now-in-header.png)

Nel calendario del canale:

- Il pulsante **Aggiungi nuovo evento** nell'intestazione del calendario del canale sarà disabilitato.
  ![Screenshot che mostra l'opzione del calendario per la selezione di un canale che consente di pianificare una riunione.](media/add-new-event-disabled.png)

- Gli utenti non potranno trascinare e selezionare un blocco di tempo nel calendario del canale per creare una riunione del canale.

- Gli utenti non possono usare le scelte rapide da tastiera per creare una riunione nel calendario del canale.

Nell'interfaccia di amministrazione:

L'app del calendario del canale sarà visualizzata nella sezione **App Microsoft** nella pagina dei criteri di autorizzazione delle app.

![Screenshot che mostra i criteri di autorizzazione dell'app nell'Teams di amministrazione.](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a>Consenti la pianificazione di riunioni private

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se gli utenti possono pianificare riunioni private in Teams. Una riunione è privata quando non viene pubblicata in un canale in un team.

Si noti che, disattivando **Consenti la pianificazione di riunioni private** e **Consenti la pianificazione delle riunioni di canale**, le opzioni **Aggiungi partecipanti obbligatori** e **Aggiungi canale** vengono disabilitate per gli utenti in Teams. Per impostazione predefinita, questa impostazione è attivata.

## <a name="allow-meet-now-in-private-meetings"></a>Consenti l'uso di Riunione immediata nelle riunioni private

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se un utente può avviare una riunione privata ad hoc.  Per impostazione predefinita, questa impostazione è attivata.

## <a name="designated-presenter-role-mode"></a>Modalità ruolo relatore designato

Questo è un criterio per utente. Questa impostazione consente di modificare il valore predefinito dell'impostazione **Chi può essere un relatore?** in **Opzioni riunione** nel client di Teams. Questa impostazione di criteri influisce su tutte le riunioni, incluse quelle immediate.

L'impostazione **Chi può essere un relatore?** consente agli organizzatori di scegliere chi può essere un relatore in una riunione. Per altre informazioni, vedere [Modificare le impostazioni dei partecipanti per una riunione Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) e [Ruoli in una riunione di Teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Attualmente, è possibile usare solo PowerShell per configurare questa impostazione di criteri. È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per specificare il valore predefinito dell'impostazione **Chi può essere un relatore?** in Teams, impostare il parametro **DesignatedPresenterRoleMode** su uno dei parametri seguenti:

- **EveryoneUserOverride**: tutti i partecipanti alla riunione possono essere relatori. Questo è il valore predefinito. Questo parametro corrisponde all'impostazione **Tutti** in Teams.
- **EveryoneInCompanyUserOverride**: gli utenti autenticati nell'organizzazione, inclusi gli utenti guest, possono essere relatori. Questo parametro corrisponde all'impostazione **Persone dell'organizzazione** in Teams.
- **OrganizerOnlyUserOverride**: solo l'organizzatore della riunione può essere un relatore, mentre tutti gli altri partecipanti alla riunione sono designati come partecipanti. Questo parametro corrisponde all'impostazione **Solo io** in Teams.

Dopo aver impostato il valore predefinito, gli organizzatori delle riunioni possono ancora modificare questa impostazione in Teams e scegliere chi può essere un relatore nelle riunioni pianificate.

## <a name="allow-engagement-report"></a>Consenti report impegno

Questo è un criterio per utente. Questa impostazione controlla se gli organizzatori delle riunioni possono scaricare il [Rapporto partecipazione a riunione](teams-analytics-and-reports/meeting-attendance-report.md).

Questo criterio è disattivato per impostazione predefinita e consente agli organizzatori di vedere chi ha registrato e partecipato alle riunioni e ai webinar che hanno configurato. Per attivare questa opzione nell'interfaccia Teams di amministrazione, passare a Criteri riunione riunioni e impostare  >  il criterio su **Abilitato.**

È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per consentire a un organizzatore della riunione di scaricare il report sulla partecipazione alla riunione, impostare il **parametro AllowEngagementReport** su **Enabled**. Se abilitata, l'opzione per scaricare il rapporto viene visualizzata nel riquadro **Partecipanti**. Per impostazione predefinita, questa impostazione non è abilitata.

Per evitare che un organizzatore della riunione scarichi il rapporto, impostare il parametro su **Disabilitato**.

## <a name="allow-meeting-registration"></a>Consentire la registrazione alla riunione

Questo è un criterio per utente. Se si attiva questa opzione, gli utenti dell'organizzazione possono configurare webinar. Questo criterio è abilitato per impostazione predefinita.

Per modificare questo criterio nell'interfaccia Teams di amministrazione, passare **a Criteri riunione**  >  **riunioni**. Per disattivare la registrazione alla riunione, impostare il criterio su **Disattivato.**

È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per attivare la registrazione della riunione, impostare il  **parametro AllowMeetingRegistration** su **True**. Questa opzione è impostata **su True** per impostazione predefinita.

Per disattivare la registrazione della riunione e impedire agli utenti di pianificare webinar, impostare il parametro su **False**.

## <a name="who-can-register"></a>Who possibile registrare

Questo criterio controlla quali utenti possono registrarsi e partecipare ai webinar. Questo criterio include due opzioni, disponibili solo se l'opzione Consenti **registrazione riunione** è attivata.

- Impostare **Who** registrarsi su **Tutti** se si vuole consentire a tutti, inclusi gli utenti anonimi, di registrarsi e partecipare ai webinar impostati dagli utenti dell'organizzazione.
- Impostare **Who** possibile registrarsi a **Tutti** nell'organizzazione se si vuole consentire solo agli utenti dell'organizzazione di registrarsi e partecipare ai webinar.

Per impostazione predefinita, **Who registrazione è** impostato su **Tutti**. Per modificare questo criterio nell'interfaccia Teams di amministrazione, passare **a Criteri riunione**  >  **riunioni**.

È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per consentire a tutti, inclusi gli utenti anonimi, di registrarsi e partecipare ai webinar, impostare il **parametro WhoCanRegister** su **Everyone**. Questa opzione è impostata **su Tutti** per impostazione predefinita.

Per consentire solo agli utenti dell'organizzazione di registrarsi e partecipare ai webinar, impostare il parametro su **EveryoneInCompany**.

## <a name="meeting-provider-for-islands-mode"></a>Provider di riunioni per la modalità Isole

Questo è un criterio per utente. Questa impostazione controlla se il componente aggiuntivo di Outlook viene usato per gli *utenti in modalità Isole*. È possibile specificare se gli utenti possono usare solo il componente aggiuntivo Riunione di Teams o sia Riunione di Teams che Riunione di Skype for Business per programmare le riunioni in Outlook.

È possibile applicare questo criterio agli utenti in modalità Isole e che hanno impostato il parametro **AllowOutlookAddIn** su **True** nel loro criterio per le riunioni di Teams.

Attualmente, è possibile usare solo PowerShell per impostare questo criterio. È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per specificare il componente aggiuntivo per le riunioni da rendere disponibile per gli utenti, impostare il parametro **PreferredMeetingProviderForIslandsMode** come indicato di seguito:

- Impostare il parametro su **TeamsAndSfB** per abilitare il componente aggiuntivo Riunione di Teams e il componente aggiuntivo Skype for Business in Outlook. Questo è il valore predefinito.
- Impostare il parametro su **Teams** per abilitare solo il componente aggiuntivo Riunione di Teams in Outlook. Questa impostazione dei criteri garantisce che tutte le riunioni future abbiano un collegamento per accedere a una riunione di Teams. Non viene eseguita la migrazione dei collegamenti di accesso alle riunioni di Skype for Business esistenti in Teams. Questa impostazione dei criteri non influisce su presenza, chat, chiamate PSTN o altre funzionalità di Skype for Business, il che significa che gli utenti continueranno a usare Skype for Business per queste funzioni.

  Se si imposta il parametro su **Teams** e poi di nuovo su **TeamsAndSfB**, entrambi i componenti aggiuntivi per le riunioni saranno abilitati. Tuttavia, i collegamenti di accesso alle riunioni di Teams esistenti non verranno migrati in Skype for Business. Solo le riunioni di Skype for Business pianificate dopo la modifica avranno un collegamento di accesso a una riunione di Skype for Business.

## <a name="meeting-reactions"></a>Reazioni alle riunioni

L'impostazione AllowMeetingReactions può essere applicata solo tramite PowerShell. Non è possibile attivare o disattivare AllowMeetingReactions nell'interfaccia di amministrazione di Teams.

Le reazioni nelle riunioni sono disattivate per impostazione predefinita. Se si disattivano le reazioni di un utente non significa che un altro utente non può usare le reazioni nelle riunioni pianificate. L'organizzatore della riunione può comunque attivare le reazioni dalla pagina delle opzioni della riunione, indipendentemente dall'impostazione predefinita.


## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare criteri in Teams](policy-assignment-overview.md)
- [Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams](meeting-policies-restricted-anonymous-access.md)
