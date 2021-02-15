---
title: Registrazione delle riunioni di Teams nel cloud
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Suggerimenti pratici per la distribuzione delle funzionalità Cloud Voice in Teams per registrare riunioni e chiamate di gruppo in Teams e acquisire le attività audio, video e di condivisione dello schermo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dba51380f2c82e55c23f9667641ddb0ea9373f06
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196190"
---
# <a name="teams-cloud-meeting-recording"></a>Registrazione delle riunioni di Teams nel cloud

In Microsoft Teams, gli utenti possono registrare le riunioni e le chiamate di gruppo per acquisire audio, video e attività di condivisione dello schermo. È anche disponibile un'opzione per la trascrizione automatica delle registrazioni, che consente agli utenti di riprodurre le registrazioni delle riunioni con sottotitoli e cercare gli elementi di discussione importanti nella trascrizione. La registrazione avviene nel cloud e viene salvata in [Microsoft Stream](https://docs.microsoft.com/stream/), in modo che gli utenti possano condividerla in tutta sicurezza nell'organizzazione.

Argomenti correlati: [documentazione per gli utenti finali sulla registrazione delle riunioni di Teams](https://aka.ms/recordmeeting)

>[!Note]
> Il passaggio dall’uso di Microsoft Stream all’uso di OneDrive for Business e SharePoint per le registrazioni delle riunioni avverrà in modo graduale. Per informazioni dettagliate su ogni fase, vedere Usare [OneDrive for Business e SharePoint o Stream per le registrazioni delle riunioni.](tmr-meeting-recording-change.md)

> [!NOTE]
> Per informazioni sull'uso dei ruoli nelle riunioni di Teams, e su come modificare i ruoli degli utenti, vedere [Ruoli nelle riunioni di Teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Prerequisiti per la registrazione delle riunioni di Teams nel cloud

Per registrare le riunioni di un utente di Teams, è necessario che Microsoft Stream sia abilitato per il tenant. Sono inoltre necessari i prerequisiti seguenti sia per l'organizzatore della riunione che per la persona che avvia la registrazione:

- L'utente deve avere un abbonamento Office 365 E1, E3, E5, A1, A3, A5, Microsoft 365 Business Premium, Business Standard, o Business Basic<sup>1</sup>
- L'utente ha accettato le linee guida dell'azienda, se sono state configurate dall'amministratore
- L'utente ha spazio di archiviazione sufficiente in Microsoft Stream per salvare le registrazioni
- L'utente ha impostato CsTeamsMeetingPolicy -AllowCloudRecording su true per registrare riunioni e chiamate di gruppo
- L'utente ha impostato CsTeamsCallingPolicy -AllowCloudRecordingForCalls su true per registrare le chiamate 1:1
- L'utente non è un utente anonimo, guest o federato nella riunione
- Per abilitare la trascrizione per una riunione di un utente, è necessario che l'impostazione -AllowTranscription sia impostata sul valore "true".

<sup>1</sup> A partire dal 20 agosto 2020, l'accesso al file della registrazione della riunione scadrà dopo 21 giorni per gli utenti A1. Per altre informazioni, vedere [Caricare registrazioni delle riunioni di Microsoft Teams su Stream](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording).

> [!IMPORTANT] 
> Gli utenti non hanno bisogno di una licenza di Microsoft Stream se saranno autorizzati soltanto a registrare e scaricare le registrazioni. Questo significa che le registrazioni non vengono archiviate in Microsoft Stream ma vengono invece archiviate in Servizi multimediali di Async (AMS) con un limite di 21 giorni prima dell'eliminazione. Al momento l'amministratore non può controllare o gestire questo aspetto, inclusa la capacità di eliminazione.

> [!IMPORTANT]
> Si noti inoltre che per le registrazioni in modalità AMS, la conservazione della registrazione è interessata dal messaggio di chat stesso. Di conseguenza, qualsiasi eliminazione del messaggio di chat originale della registrazione AMS impedirà agli utenti di accedere alla registrazione. Esistono due scenari che possono influire su questo problema. 1) L'utente elimina manualmente il messaggio di chat- In questo scenario, quando il messaggio originale non è più disponibile, gli utenti non saranno più in grado di accedere alla registrazione e non sarà possibile eseguire altri download. Tuttavia, la registrazione stessa può comunque essere conservata all'interno dei sistemi interni Microsoft per un periodo di tempo, senza superare il periodo originale di 21 giorni. 2) La registrazione del messaggio di chat viene eliminata dai criteri di conservazione della chat. Le registrazioni AMS sono direttamente collegate ai criteri di conservazione della chat. Di conseguenza, anche se le registrazioni in AMS verranno conservate per impostazione predefinita per 21 giorni prima dell'eliminazione, se il messaggio di chat viene eliminato prima del periodo di tempo di 21 giorni, a causa dei criteri di conservazione dei messaggi di chat, anche la registrazione verrà eliminata. Dopo questa operazione, non è possibile recuperare la registrazione.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurare la registrazione di riunioni di Teams nel cloud per gli utenti dell'organizzazione

In questa sezione viene descritto come configurare e pianificare la registrazione delle riunioni di Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Attivare Microsoft Stream per gli utenti dell'organizzazione

Microsoft Stream è disponibile come parte degli abbonamenti a Microsoft 365 e Office 365 idonei o come servizio autonomo.  Per altre informazioni, vedere la [Panoramica sulle licenze di Stream](https://docs.microsoft.com/stream/license-overview).  Microsoft Stream è ora incluso in Microsoft 365 Business, Microsoft 365 Business Standard e Microsoft 365 Business Basic.

Leggere altre informazioni su come [assegnare licenze agli utenti in Microsoft 365 o Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) in modo che gli utenti possano accedere a Microsoft Stream. Assicurarsi che Microsoft Stream non sia bloccato per gli utenti, come illustrato nell'articolo [Bloccare le registrazioni a Microsoft Stream](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Assicurarsi che gli utenti dispongano delle autorizzazioni per caricare video in Microsoft Stream

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono creare contenuto in Stream, dopo l'abilitazione di Stream e l'assegnazione della licenza all'utente. Un amministratore di Microsoft Stream può [limitare i dipendenti dalla creazione di contenuto in Stream](https://docs.microsoft.com/stream/restrict-uploaders). Gli utenti inclusi in questo elenco con restrizioni non saranno in grado di registrare le riunioni.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Avvisare i dipendenti che devono acconsentire alle linee guida aziendali in Microsoft Stream

Se un amministratore di Microsoft Stream ha [configurato norme di utilizzo aziendali](https://docs.microsoft.com/stream/company-policy-and-consent) e richiede ai dipendenti di accettarle prima di poter salvare contenuto, gli utenti devono farlo prima della registrazione in Microsoft Teams. Prima di implementare la funzionalità di registrazione nell'organizzazione, assicurarsi che gli utenti abbiano accettato le norme aziendali.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Attivare o disattivare la registrazione nel cloud

È possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare un criterio per le riunioni di Teams con cui controllare se le riunioni degli utenti possono essere registrate.

Nell'interfaccia di amministrazione di Microsoft Teams attivare o disattivare l'impostazione **Consenti registrazione cloud** nel criterio di riunione. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md#allow-cloud-recording).

Con PowerShell, configurare l'opzione AllowCloudRecording in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Tenere presente che sia l'organizzatore della riunione che la persona che avvia la registrazione devono avere autorizzazioni di registrazione per registrare la riunione. A meno che non siano stati assegnati criteri personalizzati, gli utenti ottengono il criterio globale, che ha AllowCloudRecording disabilitato per impostazione predefinita.

> [!NOTE]
> Per altre informazioni sull'uso dei ruoli di Teams per configurare chi è autorizzato a registrare le riunioni, vedere [Ruoli nelle riunione di Teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Affinché un utente rientri nel criterio globale, usare il cmdlet seguente per rimuovere l'assegnazione di un criterio specifico per un utente:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Per modificare il valore di AllowCloudRecording nel criterio globale, usare il cmdlet seguente:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```
</br>
</br>


|                                                                 Scenario                                                                 |                                                                                                                                                                         Passaggi                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Voglio che tutti gli utenti dell'azienda possano registrare le loro riunioni                                    |                                                                     <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = True<li>Tutti gli utenti hanno il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True </ol>                                                                     |
| Voglio che la maggior parte degli utenti possa registrare le riunioni, ma disabilitare selettivamente la registrazione per utenti specifici |        <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = True<li>La maggior parte degli utenti ha il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True<li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False</ol>         |
|                                                   Voglio che la registrazione sia completamente disabilitata                                                   |                                                                <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = False<li>A tutti gli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False                                                                 |
|      Voglio disattivare la registrazione per la maggior parte degli utenti, ma abilitare in modo selettivo la registrazione per utenti specifici       | <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = False<li>Alla maggior parte degli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False<li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Dove vengono archiviate le registrazioni delle riunioni

Le registrazioni delle riunioni vengono archiviate nello spazio di archiviazione cloud di Microsoft Stream. Attualmente, la funzionalità di registrazione delle riunioni è disattivata per i clienti che archiviano i dati di Teams all'interno del proprio paese se Microsoft Stream non è disponibile nell'area di residenza dei dati corrispondente al paese in cui vengono archiviati i dati. La funzionalità di registrazione della riunione può essere attivata per i clienti i cui dati devono essere archiviati nel paese di residenza, anche se Microsoft Stream non è disponibile nell'area geografica di residenza dei dati del paese. Questa operazione può essere eseguita consentendo l'archiviazione delle registrazioni nell'area geografica più vicina per Microsoft Stream. 

Se si archiviano i dati di Teams all'interno del paese e si preferisce archiviare anche le registrazioni delle riunioni nel paese, è consigliabile disattivare la funzionalità e riattivarla dopo la distribuzione di Microsoft Stream nell'area di residenza dei dati corrispondente al paese. Per disattivare la funzionalità per tutti gli utenti dell'organizzazione, disattivare l'impostazione **Consenti registrazione cloud** nel criterio globale delle riunioni di Teams all'interno dell'interfaccia di amministrazione di Microsoft Teams di Microsoft Teams. Se, tuttavia, si vuole consentire l'archiviazione delle registrazioni nella regione geografica più vicina per Microsoft Stream, bisogna attivare sia **Consenti registrazione cloud** che **Consenti archiviazione registrazione fuori dalla regione** affinché la modifica abbia effetto.

Per abilitare le registrazioni nella regione nel criterio globale, usare il cmdlet seguente:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```

Ecco un riepilogo di quanto accade attivando la registrazione delle riunioni dopo l'applicazione di questa modifica:

|Se si attiva la registrazione delle riunioni...|Le registrazioni delle riunioni vengono archiviate... |
|---|---|
|Prima che Microsoft Stream sia disponibile nell'area di residenza dei dati interna al paese |Nell'area di Microsoft Stream più vicina|
|Quando Microsoft Stream è disponibile nell'area di residenza dei dati interna al paese |Nell'area di residenza dei dati interna al paese|

Per i tenant nuovi ed esistenti che non hanno ancora attivato la registrazione delle riunioni, le nuove registrazioni verranno archiviate all'interno del paese dopo che Microsoft Stream sarà reso disponibile nell'area di residenza dei dati corrispondente al paese. Tuttavia, qualsiasi tenant che abiliti la registrazione delle riunioni prima che Microsoft Stream sia disponibile nell'area di residenza dei dati interna al paese continuerà a usare lo spazio di archiviazione di Microsoft Stream per le registrazioni nuove ed esistenti, anche dopo che Microsoft Stream sarà reso disponibile nell'area di residenza dei dati corrispondente al paese.

Per trovare l'area in cui sono archiviati i dati di Microsoft Stream, in Microsoft Stream fare clic su **?** nell'angolo in alto a destra fare clic su **Informazioni su Microsoft Stream** e quindi fare clic su **I dati sono archiviati in**.  Per altre informazioni sulle aree in cui Microsoft Stream archivia i dati, vedere [Domande frequenti su Microsoft Stream](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Per altre informazioni sulla posizione di archiviazione dei dati tra i vari servizi di Microsoft 365 o Office 365, vedere [Dove si trovano i dati?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Attivare o disattivare la trascrizione delle registrazioni

Questa impostazione controlla la disponibilità di didascalie e funzionalità di trascrizione durante la riproduzione di registrazioni delle riunioni. Se si disattiva questa opzione, durante la riproduzione di una registrazione di riunione non saranno disponibili le opzioni **Cerca** e **Cc**. La persona che ha avviato la registrazione ha bisogno che questa impostazione sia attivata perché la registrazione includa anche una trascrizione.

> [!NOTE]
> Si noti che la trascrizione per le riunioni registrate è attualmente supportata solo per gli utenti che hanno la lingua di Teams impostata sull'inglese, e quando durante la riunione si parla inglese. Viene archiviata, insieme alle registrazioni della riunione, nello spazio di archiviazione nel cloud di Microsoft Stream.

È possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare un criterio per le riunioni di Teams con cui controllare se chi avvia la registrazione riceve l'opzione per trascriverne la registrazione.

Nell'interfaccia di amministrazione di Microsoft Teams attivare o disattivare l'impostazione **Consenti la trascrizione** nel criterio di riunione. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md#allow-transcription).

Con PowerShell, configurare l'opzione AllowTranscription in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

A meno che non siano stati assegnati criteri personalizzati, gli utenti ottengono il criterio globale, che ha AllowTranscription disabilitato per impostazione predefinita.

Affinché un utente rientri nel criterio globale, usare il cmdlet seguente per rimuovere l'assegnazione di un criterio specifico a un utente:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Per modificare il valore di AllowCloudRecording nel criterio globale, usare il cmdlet seguente:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```
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

Le dimensioni di una registrazione di 1 ora sono pari a 400 MB. Assicurarsi di aver compreso la capacità necessaria per i file registrati e di disporre di spazio di archiviazione sufficiente in Microsoft Stream.  Leggere la [Panoramica sulle licenze di Microsoft Stream](https://docs.microsoft.com/stream/license-overview) per informazioni sullo spazio di archiviazione di base incluso nell'abbonamento, e su come acquistare spazio di archiviazione aggiuntivo.

## <a name="manage-meeting-recordings"></a>Gestire le registrazioni delle riunioni

Le registrazioni delle riunioni sono considerate contenuto di proprietà del tenant. Se il proprietario della registrazione lascia la società, l'amministratore può aprire l'URL del video della registrazione in Microsoft Stream in modalità amministratore. L'amministratore può eliminare la registrazione, aggiornare i metadati della registrazione o modificare le autorizzazioni per il video della registrazione. Leggere altre informazioni sulle [funzionalità di amministrazione di Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Per altre informazioni sulla gestione delle registrazioni e dell'accesso degli utenti, vedere [Gestire i dati degli utenti in Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) e [Autorizzazioni e privacy in Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformità ed eDiscovery per le registrazioni delle riunioni

Le registrazioni delle riunioni sono archiviate in Microsoft Stream, che è conforme a Microsoft 365 e Office 365 Tier C. Per supportare le richieste di e-Discovery per gli amministratori di conformità interessati alle registrazioni delle riunioni o delle chiamate di Microsoft Stream, il messaggio di registrazione completata è disponibile nella funzionalità di ricerca contenuto per la conformità per Microsoft Teams. Gli amministratori di conformità possono cercare la parola chiave "registrazione" nella riga dell'oggetto dell'elemento nell'anteprima della ricerca di contenuto per la conformità e individuare le registrazioni di riunioni e chiamate nell'organizzazione. Un prerequisito per visualizzare tutte le registrazioni è che dovranno essere configurati in Microsoft Stream con l'accesso di amministratore. Leggere altre informazioni su come [assegnare le autorizzazioni di amministrazione in Teams](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
