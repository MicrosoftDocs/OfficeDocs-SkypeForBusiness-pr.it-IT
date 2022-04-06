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
description: Informazioni su come gestire le impostazioni dei criteri generali per le riunioni in Teams.
ms.openlocfilehash: 2582327261e52f1d834cd3b368c79aa55ca7f103
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686343"
---
# <a name="meeting-policy-settings---general"></a>Impostazioni dei criteri di riunione - Generale

<a name="bkgeneral"> </a>

Questo articolo descrive le seguenti impostazioni dei criteri generali per le riunioni Teams:

- [Riunione immediata nei canali](#meet-now-in-channels)
- [Outlook componente aggiuntivo](#outlook-add-in)
- [Pianificazione delle riunioni di canale](#channel-meeting-scheduling)
- [Pianificazione riunione privata](#private-meeting-scheduling)
- [Riunione immediata in riunioni private](#meet-now-in-private-meetings)
- [Modalità ruolo relatore designato](#designated-presenter-role-mode)
- [Report sull'impegno](#engagement-report)
- [Registrazione riunione](#meeting-registration)
- [Who possibile registrarsi](#who-can-register)
- [Provider di riunioni per la modalità Isole](#meeting-provider-for-islands-mode)
- [Speaker Coach](#speaker-coach)

## <a name="meet-now-in-channels"></a>Riunione immediata nei canali

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se un utente può avviare una riunione ad hoc in un canale di Teams. Se si attiva questa opzione, gli utenti possono fare clic sul pulsante **Riunione** per avviare una riunione ad hoc o pianificare una riunione nel canale. Il valore predefinito è True.

[![Screenshot che mostra l'icona Riunione immediata sotto un messaggio.](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook componente aggiuntivo

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione consente di controllare se è possibile pianificare riunioni di Teams dall'interno di Outlook (Windows, Mac, Web e Mobile).

![Screenshot che mostra la possibilità di pianificare una nuova riunione.](media/meeting-policies-outlook-add-in.png)

Se si disattiva questa impostazione, gli utenti non potranno pianificare riunioni di Teams durante la creazione di una nuova riunione in Outlook. In Outlook per Windows, ad esempio, l'opzione **Nuova riunione di Teams** non comparirà sulla barra multifunzione.

## <a name="channel-meeting-scheduling"></a>Pianificazione delle riunioni di canale

Usare il criterio AllowChannelMeetingScheduling esistente per controllare i tipi di eventi che è possibile creare nei calendari del canale di un team. Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se gli utenti possono pianificare una riunione in un canale di Teams. Per impostazione predefinita, questa impostazione è attivata.

Se questo criterio è disattivato, gli utenti non potranno creare nuove riunioni di canale. Tuttavia, le riunioni di canale esistenti possono essere modificate dall'organizzatore dell'evento.

L'opzione Pianifica una riunione sarà disabilitata.

![Screenshot che mostra l'opzione Pianifica una riunione in Teams.](media/schedule-meeting-option.png)

La selezione del canale è disabilitata.

[![Screenshot che mostra l'opzione del calendario per selezionare un canale in cui pianificare una riunione.](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Nella pagina dei post del canale verranno disabilitati gli elementi seguenti:

- Pulsante **Pianifica una riunione** nella casella per comporre una risposta del canale.
  ![Screenshot che mostra l'opzione del calendario per selezionare un canale in cui si vuole pianificare una riunione.](media/schedule-meeting-disabled-in-chat2.png)
  
- Pulsante **Pianifica una riunione** nell'intestazione del canale.
  ![Screenshot che mostra l'opzione del calendario per selezionare un canale attraverso il quale si vuole pianificare una riunione.](media/schedule-now-in-header.png)

Nel calendario del canale:

- Il pulsante **Aggiungi nuovo evento** nell'intestazione del calendario del canale sarà disabilitato.
  ![Screenshot che mostra l'opzione del calendario per selezionare un canale che consente di pianificare una riunione.](media/add-new-event-disabled.png)

- Gli utenti non potranno trascinare e selezionare un intervallo di tempo nel calendario del canale per creare una riunione del canale.

- Gli utenti non possono usare le scelte rapide da tastiera per creare una riunione nel calendario del canale.

Nell'interfaccia di amministrazione:

L'app del calendario del canale sarà visualizzata nella sezione **App Microsoft** nella pagina dei criteri di autorizzazione delle app.

![Screenshot che mostra i criteri di autorizzazione dell'app nell'interfaccia di amministrazione di Teams.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Pianificazione riunione privata

Questo è un criterio per utente e si applica prima dell'inizio di una riunione. Questa impostazione controlla se gli utenti possono pianificare riunioni private in Teams. Una riunione è privata quando non viene pubblicata in un canale in un team.

Si noti che, disattivando **Consenti la pianificazione di riunioni private** e **Consenti la pianificazione delle riunioni di canale**, le opzioni **Aggiungi partecipanti obbligatori** e **Aggiungi canale** vengono disabilitate per gli utenti in Teams. Per impostazione predefinita, questa impostazione è attivata.

## <a name="meet-now-in-private-meetings"></a>Riunione immediata in riunioni private

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

## <a name="engagement-report"></a>Report sull'impegno

Questo è un criterio per utente. Questa impostazione controlla se gli organizzatori delle riunioni possono scaricare il [Rapporto partecipazione a riunione](teams-analytics-and-reports/meeting-attendance-report.md).

Questo criterio è attivato per impostazione predefinita e consente agli organizzatori di vedere chi si è registrato e ha partecipato alle riunioni e ai webinar configurati. Per disattivarlo nell'interfaccia di amministrazione di Teams, passare a **Criteri di** **RiunioniMeeting** >  e impostare l'impostazione Report **impegno** su **Disattivato**.

Puoi anche modificare un criterio di riunione Teams esistente utilizzando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per impostazione predefinita, il parametro **AllowEngagementReport** è impostato su **Abilitato** in PowerShell. Per impedire a un organizzatore della riunione di scaricare il report sulla partecipazione alla riunione, impostare il parametro **AllowEngagementReport** su **Disabled**.

Quando questo criterio è abilitato, l'opzione per scaricare il report presenze alla riunione viene visualizzata nel riquadro **Partecipanti** .

> [!NOTE]
> Gli amministratori non possono visualizzare il report presenze per le riunioni che non si organizzano. Tuttavia, è possibile visualizzare i dettagli dei partecipanti per una determinata riunione entro 24 ore dalla riunione. Nell'interfaccia di amministrazione di Teams passare a **UtentiGesti** >  utenti. Scegliere il nome visualizzato per l'organizzatore della riunione. Selezionare la scheda **Riunioni & chiamate** e quindi scegliere l'ID riunione o l'ID chiamata appropriato. Selezionare quindi **Dettagli partecipante**.

Per altre informazioni, inclusi i limiti del report sull'impegno, vedere [Visualizzare e scaricare report sulla partecipazione alle riunioni in Teams](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310).

## <a name="meeting-registration"></a>Registrazione riunione

Questo è un criterio per utente. Se si attiva questa opzione, gli utenti dell'organizzazione possono configurare webinar. Questo criterio è abilitato per impostazione predefinita.

Per modificare questo criterio nell'interfaccia di amministrazione di Teams, passare a Criteri di **RiunioniMeeting** > . Per disattivare la registrazione della riunione, impostare il criterio su **Disattivato**.

È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per attivare la registrazione della riunione, impostare il parametro  **MeetingRegistration** su **True**. Questo valore è impostato su **True** per impostazione predefinita.

Per disattivare la registrazione delle riunioni e impedire agli utenti di pianificare webinar, impostare il parametro **su False**.

## <a name="who-can-register"></a>Who possibile registrarsi

Questo criterio controlla quali utenti possono registrarsi e partecipare ai webinar. Questo criterio include due opzioni, che sono disponibili solo se la **registrazione riunione** è attivata.

- Impostare **Who possibile iscriversi** a **Tutti** se si vuole consentire a tutti, inclusi gli utenti anonimi, di registrarsi e partecipare a webinar configurati dall'utente nell'organizzazione.
- Impostare **Who possono registrarsi** **in Tutti gli utenti dell'organizzazione** se si vuole consentire solo agli utenti dell'organizzazione di registrarsi e partecipare a webinar.

Per impostazione predefinita, **Who possibile registrare** è impostato su **Tutti**. Per modificare questo criterio nell'interfaccia di amministrazione di Teams, passare a Criteri di **RiunioniMeeting** > .

È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per consentire a tutti, inclusi gli utenti anonimi, di registrarsi e partecipare ai webinar, impostare il parametro **WhoCanRegister** su **Everyone**. Questa opzione è impostata su **Tutti** per impostazione predefinita.

Per consentire solo agli utenti dell'organizzazione di registrarsi e partecipare a webinar, impostare il parametro **su EveryoneInCompany**.

## <a name="meeting-provider-for-islands-mode"></a>Provider di riunioni per la modalità Isole

Questo è un criterio per utente. Questa impostazione controlla se il componente aggiuntivo di Outlook viene usato per gli *utenti in modalità Isole*. È possibile specificare se gli utenti possono usare solo il componente aggiuntivo Riunione di Teams o sia Riunione di Teams che Riunione di Skype for Business per programmare le riunioni in Outlook.

È possibile applicare questo criterio agli utenti in modalità Isole e che hanno impostato il parametro **AllowOutlookAddIn** su **True** nel loro criterio per le riunioni di Teams.

Attualmente, è possibile usare solo PowerShell per impostare questo criterio. È possibile modificare un criterio di riunione di Teams esistente usando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy). In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Per specificare il componente aggiuntivo per le riunioni da rendere disponibile per gli utenti, impostare il parametro **PreferredMeetingProviderForIslandsMode** come indicato di seguito:

- Impostare il parametro su **TeamsAndSfB** per abilitare il componente aggiuntivo Riunione di Teams e il componente aggiuntivo Skype for Business in Outlook. Questo è il valore predefinito.
- Impostare il parametro su **Teams** per abilitare solo il componente aggiuntivo Riunione di Teams in Outlook. Questa impostazione dei criteri garantisce che tutte le riunioni future abbiano un collegamento per accedere a una riunione di Teams. Non viene eseguita la migrazione dei collegamenti di accesso alle riunioni di Skype for Business esistenti in Teams. Questa impostazione dei criteri non influisce su presenza, chat, chiamate PSTN o altre funzionalità di Skype for Business, il che significa che gli utenti continueranno a usare Skype for Business per queste funzioni.

  Se si imposta il parametro su **Teams** e poi di nuovo su **TeamsAndSfB**, entrambi i componenti aggiuntivi per le riunioni saranno abilitati. Tuttavia, i collegamenti di accesso alle riunioni di Teams esistenti non verranno migrati in Skype for Business. Solo le riunioni di Skype for Business pianificate dopo la modifica avranno un collegamento di accesso a una riunione di Skype for Business.

## <a name="meeting-reactions"></a>Reazioni delle riunioni

L'impostazione AllowMeetingReactions può essere applicata solo tramite PowerShell. Non è possibile attivare o disattivare AllowMeetingReactions nell'interfaccia di amministrazione di Teams.

Le reazioni nelle riunioni sono disattivate per impostazione predefinita. Se si disattivano le reazioni di un utente non significa che un altro utente non può usare le reazioni nelle riunioni pianificate. L'organizzatore della riunione può comunque attivare le reazioni dalla pagina delle opzioni della riunione, indipendentemente dall'impostazione predefinita.

## <a name="speaker-coach"></a>Speaker Coach

Questa impostazione consente agli utenti di attivare Speaker Coach durante una riunione Teams. Speaker Coach ascolta l'audio dell'utente durante la presentazione e fornisce feedback privati in tempo reale e suggerimenti per il miglioramento. L'utente riceve anche un riepilogo del feedback dopo la riunione.

> [!NOTE]
> L'utente che ha attivato Speaker Coach durante la riunione è l'unico che può vedere il report di riepilogo del feedback. Gli amministratori non avranno accesso a questi dati.

Attualmente, è possibile impostare e modificare questo criterio solo in PowerShell. utilizzando il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . In alternativa, è possibile creare un nuovo criterio per le riunioni di Teams usando il cmdlet [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) e assegnarlo agli utenti.

Questa impostazione è abilitata per impostazione predefinita. Per disattivarlo, impostare **AllowMeetingCoach** **su False**.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare criteri in Teams](policy-assignment-overview.md)
- [Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams](meeting-policies-restricted-anonymous-access.md)
