---
title: Registrazione delle riunioni cloud Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: Linee guida pratiche per la distribuzione di funzionalità cloud Voice in Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbb2d8ed9895044dd1cdb52e57663162def6e24b
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "36182203"
---
# <a name="teams-cloud-meeting-recording"></a>Registrazione delle riunioni cloud Teams

In Microsoft teams gli utenti possono registrare le riunioni del team e le chiamate di gruppo per acquisire attività audio, video e condivisione dello schermo. Esiste anche un'opzione per le registrazioni per la trascrizione automatica, in modo che gli utenti possano riprodurre le registrazioni delle riunioni con sottotitoli chiusi e cercare elementi di discussione importanti nella trascrizione. La registrazione si verifica nel cloud e viene salvata in [Microsoft Stream](https://docs.microsoft.com/stream/), in modo che gli utenti possano condividerla in tutta sicurezza nell'organizzazione.

Correlato: [documentazione dell'utente finale di teams Meeting recording](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Prerequisiti per la registrazione di teams Cloud Meeting

Per registrare le riunioni di un utente di teams, Microsoft stream deve essere abilitato per il tenant. Inoltre, sono necessari i prerequisiti seguenti sia per l'organizzatore della riunione che per la persona che avvia la registrazione:

- L'utente ha un Office 365 E1, E3, E5, a1, a3, a5, M365 business, Business Premium o Business Essentials
- L'utente deve essere concesso in licenza per Microsoft Stream
- L'utente ha le autorizzazioni di Microsoft Stream upload video
- L'utente ha acconsentito alle linee guida della società, se è stato configurato dall'amministratore
- L'utente dispone di spazio di archiviazione sufficiente in Microsoft Stream per le registrazioni da salvare
- L'impostazione TeamsMeetingPolicy-AllowCloudRecording dell'utente è impostata su true
- L'utente non è un utente anonimo, Guest o federato nella riunione

> [!NOTE]
> Inoltre, per consentire alla persona che avvia la registrazione di scegliere se trascrivere automaticamente la registrazione, l'impostazione TeamsMeetingPolicy-AllowTranscription dell'utente deve essere impostata su true

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurare la registrazione di teams Cloud Meeting per gli utenti dell'organizzazione

Questa sezione spiega come configurare e pianificare le riunioni di team di registrazione.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Abilitare Microsoft Stream per gli utenti dell'organizzazione

Microsoft Stream è disponibile come parte delle sottoscrizioni di Office 365 idonee o come servizio autonomo.  Per altri dettagli, vedere la [panoramica sulla gestione delle licenze Stream](https://docs.microsoft.com/stream/license-overview) .  Microsoft Stream è ora incluso in Microsoft 365 business, Office 365 Business Premium e Office 365 Business Essentials.

Leggi altre informazioni su come [assegnare licenze agli utenti in Office 365 in](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) modo che gli utenti possano accedere a Microsoft Stream. Verificare che Microsoft Stream non sia bloccato per gli utenti, come definito in [questo articolo](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Verificare che gli utenti dispongano delle autorizzazioni di caricamento video in Microsoft Stream

Per impostazione predefinita, tutti gli utenti della società possono creare contenuto in stream, quando il flusso è abilitato e la licenza viene assegnata all'utente. Un amministratore di Microsoft Stream può [limitare i dipendenti per la creazione di contenuto](https://docs.microsoft.com/stream/restrict-uploaders) in Stream. Gli utenti che si trovano in questo elenco con restrizioni non saranno in grado di registrare le riunioni.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Informare i dipendenti sul consenso alle linee guida aziendali in Microsoft Stream

Se un amministratore di Microsoft Stream ha configurato i criteri per le [linee guida della società](https://docs.microsoft.com/stream/company-policy-and-consent) e richiede ai dipendenti di accettare questo criterio prima di salvare il contenuto, gli utenti devono farlo prima della registrazione in Microsoft teams. Prima di implementare la funzionalità di registrazione nell'organizzazione, assicurati che gli utenti abbiano acconsentito al criterio.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Attivare o disattivare la registrazione cloud

Usare l'impostazione AllowCloudRecording in TeamsMeetingPolicy in teams PowerShell per controllare se le riunioni di un utente possono essere registrate o meno. Per ulteriori informazioni sulla gestione di TeamsMeetingPolicy con Office 365 PowerShell, vedere [qui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Tieni presente che sia l'organizzatore della riunione che l'iniziatore della registrazione devono avere le autorizzazioni di registrazione per registrare la riunione. A meno che non siano stati assegnati criteri personalizzati agli utenti, gli utenti ottengono un criterio globale, che ha AllowTranscription disabilitato per impostazione predefinita.

Affinché un utente rientri nei criteri globali, usare il cmdlet seguente per rimuovere una specifica assegnazione di criteri per un utente:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Per modificare il valore di AllowCloudRecording nei criteri globali, usare il cmdlet seguente:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Scenario                                                                 |                                                                                                                                                                         Passaggi                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Voglio che tutti gli utenti della mia azienda possano registrare le loro riunioni                                    |                                                                     <ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowCloudRecording = true<li>Tutti gli utenti hanno il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = true </ol>                                                                     |
| Voglio che la maggior parte degli utenti sia in grado di registrare le proprie riunioni, ma disabilitare selettivamente utenti specifici che non sono autorizzati a registrare |        <ol><li>Conferma GlobalCsTeamsMeetingPolicy ha AllowCloudRecording = true<li>La maggior parte degli utenti ha il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = true<li>A tutti gli altri utenti è stato concesso uno dei criteri di CsTeamsMeetingPolicy con AllowCloudRecording = false</ol>         |
|                                                   Voglio che la registrazione sia disattivata per 100%                                                   |                                                                <ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowCloudRecording = false<li>A tutti gli utenti è stato concesso il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = false                                                                 |
|      Voglio che la registrazione venga disabilitata per la maggior parte degli utenti, ma in modo selettivo consente agli utenti specifici autorizzati a registrare       | <ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowCloudRecording = false<li>Alla maggior parte degli utenti è stato concesso il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = false<li>A tutti gli altri utenti è stato concesso uno dei criteri di CsTeamsMeetingPolicy con AllowCloudRecording = true <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="turn-on-or-turn-off-recording-transcription"></a>Attivare o disattivare la trascrizione della registrazione

Quando gli utenti registrano le riunioni dei team, possono verificare se una trascrizione deve essere generata automaticamente dopo la registrazione della riunione. Se gli amministratori hanno disabilitato la funzionalità di trascrizione per l'organizzatore della riunione e l'iniziatore della registrazione, l'iniziatore della registrazione non otterrà una scelta per trascrivere le registrazioni delle riunioni.

Usare l'impostazione AllowTranscription in TeamsMeetingPolicy in teams PowerShell per controllare se un iniziatore di registrazione può scegliere di trascrivere la registrazione della riunione. Per ulteriori informazioni sulla gestione di TeamsMeetingPolicy con Office 365 PowerShell, vedere [qui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

A meno che non siano stati assegnati criteri personalizzati agli utenti, ottengono criteri globali, con AllowTranscription disabilitato per impostazione predefinita.

Affinché un utente rientri nei criteri globali, usare il cmdlet seguente per rimuovere una specifica assegnazione di criteri per un utente:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Per modificare il valore di AllowCloudRecording nei criteri globali, usare il cmdlet seguente:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Scenario|Passaggi |
|---|---|
|Voglio che tutti gli utenti della mia azienda possano trascrivere durante l'avvio della registrazione di una riunione |<ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowTranscription = true <li>Tutti gli utenti hanno il csTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = true. </ol>|
|Voglio che la maggior parte dei miei utenti sia in grado di trascrivere le registrazioni delle riunioni, ma disabilitare selettivamente utenti specifici che non sono autorizzati a trascrivere |<ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowTranscription = true <li>La maggior parte degli utenti ha il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = true <li>A tutti gli altri utenti è stato concesso uno dei criteri di CsTeamsMeetingPolicy con AllowTranscription = false </ol>|
|Voglio che la trascrizione della registrazione sia 100% disabilitata |<ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowTranscription = false <li>A tutti gli utenti è stato concesso il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = false </ol>|
|Voglio che la trascrizione venga disabilitata per la maggior parte degli utenti, ma in modo selettivo consente agli utenti specifici autorizzati a trascrivere |<ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowCloudRecording = false <li>Alla maggior parte degli utenti è stato concesso il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = false <li>A tutti gli altri utenti è stato concesso uno dei criteri di CsTeamsMeetingPolicy con AllowCloudRecording = true </ol>|
|||

### <a name="planning-for-storage"></a>Pianificazione dello spazio di archiviazione

Le dimensioni di una registrazione di 1 ora sono di 400 MB. Verificare di aver compreso la capacità necessaria per i file registrati e di avere sufficiente spazio di archiviazione disponibile in Microsoft Stream.  Leggere [questo articolo](https://docs.microsoft.com/stream/license-overview) per comprendere lo spazio di archiviazione di base incluso nell'abbonamento e come acquistare ulteriore spazio di archiviazione.

## <a name="manage-meeting-recordings"></a>Gestire le registrazioni delle riunioni
Le registrazioni delle riunioni sono considerate contenuto di proprietà del tenant. Se il proprietario della registrazione lascia la società, l'amministratore può aprire l'URL del video di registrazione in Microsoft Stream in modalità amministratore. L'amministratore può eliminare la registrazione, aggiornare i metadati della registrazione o modificare le autorizzazioni per il video di registrazione. Leggi altre informazioni sulle [funzionalità di amministrazione in Stream](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformità e eDiscovery per le registrazioni delle riunioni
Le registrazioni delle riunioni sono archiviate in Microsoft Stream, che è conforme a Office 365 Tier-C. Per supportare le richieste di rilevamento e-individuazione per gli amministratori di conformità che sono interessati alle registrazioni delle riunioni o delle chiamate per i flussi Microsoft, il messaggio di registrazione completata è disponibile nella funzionalità di ricerca del contenuto per Microsoft teams. Gli amministratori della conformità possono cercare la parola chiave "registrazione" nella riga dell'oggetto dell'elemento nell'anteprima della ricerca di contenuto di conformità e individuare le registrazioni delle riunioni e delle chiamate nell'organizzazione. Un prerequisito per consentire loro di visualizzare tutte le registrazioni è che dovranno essere configurate in Microsoft Stream con l'accesso tramite amministratore. Leggi altre informazioni sull' [assegnazione di autorizzazioni di amministratore in Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Configurare il computer per Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

