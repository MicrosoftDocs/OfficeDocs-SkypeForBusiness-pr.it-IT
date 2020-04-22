---
title: Registrazione delle riunioni di Teams nel cloud
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Come attivare e gestire la registrazione delle riunioni in Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f358a0099da3f759e50f02b7bb7a5226069fcd28
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780335"
---
# <a name="teams-cloud-meeting-recording"></a>Registrazione delle riunioni di Teams nel cloud

In Microsoft Teams, gli utenti possono registrare le riunioni e le chiamate di gruppo per acquisire audio, video e attività di condivisione dello schermo. È anche disponibile un'opzione per la trascrizione automatica delle registrazioni, che consente agli utenti di riprodurre le registrazioni delle riunioni con sottotitoli e cercare gli elementi di discussione importanti nella trascrizione. La registrazione avviene nel cloud e viene salvata in [Microsoft Stream](https://docs.microsoft.com/stream/), in modo che gli utenti possano condividerla in tutta sicurezza nell'organizzazione.

Argomenti correlati: [documentazione per gli utenti finali sulla registrazione delle riunioni di Teams](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Prerequisiti per la registrazione delle riunioni di Teams nel cloud

Per registrare le riunioni di un utente di Teams, è necessario che Microsoft Stream sia abilitato per il tenant. Sono inoltre necessari i prerequisiti seguenti sia per l'organizzatore della riunione che per la persona che avvia la registrazione:

- L'utente ha un abbonamento a Office 365 E1, E3, E5, A1, A3, A5, M365 Business, Business Premium o Business Essentials
- L'utente ha una licenza di Microsoft Stream<sup>1</sup> 
- L'utente ha autorizzazioni per il caricamento di video in Microsoft Stream
- L'utente ha accettato le linee guida dell'azienda, se sono state configurate dall'amministratore
- L'utente ha spazio di archiviazione sufficiente in Microsoft Stream per salvare le registrazioni
- L'utente ha l'impostazione TeamsMeetingPolicy-AllowCloudRecording configurata su True
- L'utente non è un utente anonimo, guest o federato nella riunione

> [!NOTE]
> Inoltre, per consentire alla persona che avvia la registrazione di scegliere se trascriverla automaticamente, è necessario che l'impostazione di TeamsMeetingPolicy-AllowTranscription dell'utente sia impostata su True

<sup>1</sup>L'utente deve avere una licenza che consenta di caricare/scaricare riunioni in/da Microsoft Stream, ma non ha bisogno della licenza per registrare una riunione. Se si vuole impedire a un utente di registrare una riunione di Microsoft Teams, è necessario assegnargli un criterio TeamsMeetingPolicy con AllowCloudRecording impostato su $False.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurare la registrazione di riunioni di Teams nel cloud per gli utenti dell'organizzazione

In questa sezione viene descritto come configurare e pianificare la registrazione delle riunioni di Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Attivare Microsoft Stream per gli utenti dell'organizzazione

Microsoft Stream è disponibile come parte degli abbonamenti Microsoft 365 e Office 365 idonei o come servizio autonomo.  Per altre informazioni, vedere la [panoramica sulle licenze di Stream](https://docs.microsoft.com/stream/license-overview).  Microsoft Stream è ora incluso in Microsoft 365 business, Microsoft 365 business standard e Microsoft 365 Business Basic.

Leggere altre informazioni su come [assegnare licenze agli utenti in Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) in modo che gli utenti possano accedere a Microsoft Stream. Assicurarsi che Microsoft Stream non sia bloccato per gli utenti, come illustrato in [questo articolo](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Assicurarsi che gli utenti dispongano delle autorizzazioni di caricamento video in Microsoft Stream

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono creare contenuto in Stream, dopo l'abilitazione di Stream e l'assegnazione della licenza all'utente. Un amministratore di Microsoft Stream può [limitare i dipendenti dalla creazione di contenuto in Stream](https://docs.microsoft.com/stream/restrict-uploaders). Gli utenti inclusi in questo elenco con restrizioni non saranno in grado di registrare le riunioni.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Avvisare i dipendenti che devono acconsentire alle linee guida aziendali in Microsoft Stream

Se un amministratore di Microsoft Stream ha [configurato norme di utilizzo aziendali](https://docs.microsoft.com/stream/company-policy-and-consent) e richiede ai dipendenti di accettarle prima di poter salvare contenuto, gli utenti devono farlo prima della registrazione in Microsoft Teams. Prima di implementare la funzionalità di registrazione nell'organizzazione, assicurarsi che gli utenti abbiano accettato le norme aziendali.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Attivare o disattivare la registrazione nel cloud

È possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare un criterio per le riunioni di Teams con cui controllare se le riunioni degli utenti possono essere registrate.

Nell'interfaccia di amministrazione di Microsoft Teams attivare o disattivare l'impostazione **Consenti registrazione cloud** nel criterio di riunione. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md#allow-cloud-recording).

Con PowerShell, configurare l'opzione AllowCloudRecording in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Tenere presente che sia l'organizzatore della riunione che la persona che avvia la registrazione devono avere autorizzazioni di registrazione per registrare la riunione. A meno che non siano stati assegnati criteri personalizzati, gli utenti ottengono il criterio globale, che ha AllowCloudRecording disabilitato per impostazione predefinita.

Affinché un utente rientri nel criterio globale, usare il cmdlet seguente per rimuovere l'assegnazione di un criterio specifico per un utente:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Per modificare il valore di AllowCloudRecording nel criterio globale, usare il cmdlet seguente:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Scenario                                                                 |                                                                                                                                                                         Passaggi                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Voglio che tutti gli utenti dell'azienda possano registrare le loro riunioni                                    |                                                                     <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = True<li>Tutti gli utenti hanno il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True </ol>                                                                     |
| Voglio che la maggior parte degli utenti possa registrare le riunioni, ma disabilitare selettivamente la registrazione per utenti specifici |        <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = True<li>La maggior parte degli utenti ha il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True<li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False</ol>         |
|                                                   Voglio che la registrazione sia completamente disabilitata                                                   |                                                                <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = False<li>A tutti gli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False                                                                 |
|      Voglio che la registrazione sia disattivata per la maggior parte degli utenti, ma in modo selettivo consente agli utenti specifici autorizzati a registrare       | <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = False<li>Alla maggior parte degli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False<li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Dove vengono archiviate le registrazioni delle riunioni

Le registrazioni delle riunioni vengono archiviate nello spazio di archiviazione cloud di Microsoft Stream. Dopo aver registrato una riunione, Microsoft Stream la mantiene per sempre (o finché il proprietario della registrazione non la Elimina). Se la registrazione non viene caricata in stream, viene archiviata in teams cloud storage, dove è disponibile per il download per 20 giorni. Attualmente, la funzionalità di registrazione delle riunioni è disattivata per i clienti che archiviano i dati di Teams all'interno del proprio paese se Microsoft Stream non è disponibile nell'area di residenza dei dati corrispondente al paese in cui vengono archiviati i dati.

Per trovare l'area in cui sono archiviati i dati di Microsoft Stream, in Microsoft Stream fare clic su **?** nell'angolo in alto a destra fare clic su **Informazioni su Microsoft Stream**e quindi fare clic su **I dati sono archiviati in**.  Per altre informazioni sulle aree in cui Microsoft Stream archivia i dati, vedere [Domande frequenti su Microsoft Stream](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Per altre informazioni sulla posizione di archiviazione dei dati tra i vari servizi di Office 365, vedere [Dove si trovano i dati?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Attivare o disattivare la trascrizione delle registrazioni

Quando gli utenti registrano le riunioni di Teams, possono confermare se vogliono che dopo la registrazione della riunione venga generata automaticamente una trascrizione. Se l’amministratore ha disabilitato la funzionalità di trascrizione per l'organizzatore della riunione e l'utente che avvia la registrazione, quest'ultimo non potrà scegliere se trascrivere le registrazioni delle riunioni.

È possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare un criterio per le riunioni di Teams con cui controllare se chi avvia la registrazione riceve l'opzione per trascriverne la registrazione.

Nell'interfaccia di amministrazione di Microsoft Teams attivare o disattivare l'impostazione **Consenti la trascrizione** nel criterio di riunione. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md#allow-transcription).

Con PowerShell, configurare l'opzione AllowTranscription in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

A meno che non siano stati assegnati criteri personalizzati, gli utenti ottengono il criterio globale, che ha AllowTranscription disabilitato per impostazione predefinita.

Affinché un utente rientri nel criterio globale, usare il cmdlet seguente per rimuovere l'assegnazione di un criterio specifico a un utente:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Per modificare il valore di AllowCloudRecording nel criterio globale, usare il cmdlet seguente:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Scenario|Passaggi |
|---|---|
|Voglio che tutti gli utenti dell'azienda possano generare la trascrizione quando avviano la registrazione di una riunione |<ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowTranscription = True <li>Tutti gli utenti hanno il criterio csTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = True. </ol>|
|Voglio che la maggior parte degli utenti possa trascrivere le registrazioni di riunioni, ma disabilitare selettivamente la trascrizione per utenti specifici |<ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowTranscription = True <li>La maggior parte degli utenti ha il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = True <li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = False </ol>|
|Voglio disabilitare completamente la trascrizione delle registrazioni |<ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowTranscription = False <li>A tutti gli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = False </ol>|
|Voglio disabilitare la trascrizione per la maggior parte degli utenti, ma abilitare in modo selettivo la trascrizione per utenti specifici |<ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = False <li>Alla maggior parte degli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False <li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Pianificazione dell'archiviazione

Le dimensioni di una registrazione di 1 ora sono pari a 400 MB. Assicurarsi di aver compreso la capacità necessaria per i file registrati e di disporre di spazio di archiviazione sufficiente in Microsoft Stream.  Leggere [questo articolo](https://docs.microsoft.com/stream/license-overview) per informazioni sullo spazio di archiviazione di base incluso nell'abbonamento e su come acquistare spazio di archiviazione aggiuntivo.

## <a name="manage-meeting-recordings"></a>Gestire le registrazioni delle riunioni

Le registrazioni delle riunioni sono considerate contenuto di proprietà del tenant. Se il proprietario della registrazione lascia la società, l'amministratore può aprire l'URL del video della registrazione in Microsoft Stream in modalità amministratore. L'amministratore può eliminare la registrazione, aggiornare i metadati della registrazione o modificare le autorizzazioni per il video della registrazione. Leggere altre informazioni sulle [funzionalità di amministrazione di Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Per altre informazioni sulla gestione delle registrazioni e dell'accesso degli utenti, vedere [Gestire i dati degli utenti in Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) e [Autorizzazioni e privacy in Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions).


## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformità ed eDiscovery per le registrazioni delle riunioni

Le registrazioni delle riunioni sono archiviate in Microsoft Stream, che è conforme a Office 365 Tier C. Per supportare le richieste di e-Discovery per gli amministratori di conformità interessati alle registrazioni delle riunioni o delle chiamate di Microsoft Stream, il messaggio di registrazione completata è disponibile nella funzionalità di ricerca contenuto per la conformità per Microsoft Teams. Gli amministratori di conformità possono cercare la parola chiave "registrazione" nella riga dell'oggetto dell'elemento nell'anteprima della ricerca di contenuto per la conformità e individuare le registrazioni di riunioni e chiamate nell'organizzazione. Un prerequisito per visualizzare tutte le registrazioni è che dovranno essere configurati in Microsoft Stream con l'accesso di amministratore. Leggere altre informazioni su come [assegnare le autorizzazioni di amministrazione in Teams](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
