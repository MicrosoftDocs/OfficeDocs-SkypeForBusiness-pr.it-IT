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
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: Suggerimenti pratici per la distribuzione delle funzionalità Cloud Voice in Teams per registrare riunioni e chiamate di gruppo in Teams e acquisire le attività audio, video e di condivisione dello schermo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c1e8bc4836cab206389fcc011e4d7a41d2b54f74
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973064"
---
# <a name="teams-cloud-meeting-recording"></a>Registrazione delle riunioni di Teams nel cloud

In Microsoft Teams, gli utenti possono registrare le riunioni e le chiamate di gruppo per acquisire audio, video e attività di condivisione dello schermo. È anche disponibile un'opzione per la trascrizione automatica delle registrazioni, che consente agli utenti di riprodurre le registrazioni delle riunioni con sottotitoli ed esaminare gli elementi di discussione importanti nella trascrizione. La registrazione avviene nel cloud e viene salvata in Microsoft OneDrive for Business e Microsoft SharePoint Online, in modo che gli utenti possano condividerla in tutta sicurezza nell'organizzazione.

Dopo la registrazione, una riunione viene automaticamente:

- Caricata in OneDrive for Business o SharePoint Online
- Autorizzata per le persone invitate alla riunione
- Collegata nella chat per la riunione
- Visualizzata nella scheda Registrazioni e trascrizioni per la riunione nel calendario di Teams
- Aggiunta a vari elenchi di file in Microsoft 365: Condivisi con l'utente corrente, office.com, Consigliati, Recenti e così via.
- Indicizzata per la ricerca di Microsoft 365

Argomenti correlati: [documentazione per gli utenti finali sulla registrazione delle riunioni di Teams](https://support.microsoft.com/en-us/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> Il passaggio dall’uso di Microsoft Stream (classico) all’uso di OneDrive for Business e SharePoint Online per le registrazioni delle riunioni avverrà automaticamente nel mese di agosto 2021. Per informazioni dettagliate, vedere [Usare OneDrive for Business e SharePoint o Stream per registrare le riunioni](tmr-meeting-recording-change.md).

> [!NOTE]
> Per informazioni sull'uso dei ruoli nelle riunioni di Teams, e su come modificare i ruoli degli utenti, vedere [Ruoli nelle riunioni di Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019). Per le opzioni di registrazione degli eventi live, vedere [Criteri di registrazione degli eventi live in Teams](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Prerequisiti per la registrazione delle riunioni di Teams nel cloud

Per registrare le riunioni di un utente di Teams, è necessario abilitare OneDrive for Business e SharePoint Online per il tenant. Sono inoltre necessari i prerequisiti seguenti sia per l'organizzatore della riunione che per la persona che avvia la registrazione:

- L'utente ha spazio di archiviazione sufficiente in OneDrive for Business per salvare le registrazioni delle riunioni non di canale.

- Il canale di Teams ha spazio di archiviazione sufficiente in SharePoint Online per salvare le registrazioni delle riunioni del canale.

- L'utente ha impostato `CsTeamsMeetingPolicy -AllowCloudRecording` su true per registrare riunioni e chiamate di gruppo.

- L'utente ha impostato `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` su true per registrare le chiamate 1:1.

- L'utente non è un utente anonimo, guest o federato nella riunione.

- Per abilitare la trascrizione per una riunione di un utente, è necessario che l'impostazione `-AllowTranscription` sia configurata sul valore "true".

- Per consentire il salvataggio delle registrazioni delle riunioni del canale in modo che i membri del canale non possano modificarle o scaricarle, l'impostazione `CSTeamsMeetingPolicy -ChannelRecordingDownload` deve essere configurata su Blocca.

> [!IMPORTANT]
>
> Gli utenti non dovranno abilitare OneDrive for Business o SharePoint Online se vogliono solo salvare e scaricare le registrazioni. Questo significa che le registrazioni non vengono archiviate in OneDrive for Business o SharePoint Online, bensì in uno spazio di archiviazione temporaneo di Teams, con un limite di 21 giorni prima dell'eliminazione. Al momento l'amministratore non può controllare, gestire o eliminare questa impostazione.
>
> Per altre [informazioni sul funzionamento dell'archiviazione temporanea della registrazione delle riunioni](#temp-storage), vedere di seguito.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurare la registrazione di riunioni di Teams nel cloud per gli utenti dell'organizzazione

In questa sezione viene descritto come configurare e pianificare la registrazione delle riunioni di Teams tramite i [criteri di riunione di Teams](policy-assignment-overview.md).

### <a name="turn-on-or-turn-off-cloud-recording"></a>Attivare o disattivare la registrazione nel cloud

È possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare un criterio per le riunioni di Teams con cui controllare se le riunioni degli utenti possono essere registrate.

Nell'interfaccia di amministrazione di Microsoft Teams attivare o disattivare l'impostazione **Consenti registrazione cloud** nel criterio di riunione. Per altre informazioni, vedere [Impostazioni dei criteri di riunioni per audio e video](meetings-policies-recording-and-transcription.md#allow-cloud-recording).

Con PowerShell, configurare l'opzione AllowCloudRecording in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

Sia l'organizzatore della riunione che la persona che avvia la registrazione devono avere le autorizzazioni di registrazione per registrare la riunione. A meno che non siano stati assegnati criteri personalizzati, gli utenti ottengono il criterio globale, che ha AllowCloudRecording disabilitato per impostazione predefinita.

> [!NOTE]
> Per altre informazioni sull'uso dei ruoli di Teams per configurare chi è autorizzato a registrare le riunioni, vedere [Ruoli nelle riunione di Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Affinché un utente rientri nel criterio globale, usare il cmdlet seguente per rimuovere l'assegnazione di un criterio specifico per un utente:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Per modificare il valore di AllowCloudRecording nel criterio globale, usare il cmdlet seguente:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|Scenario|Passaggi|
|--|--|
| Voglio che tutti gli utenti dell'azienda possano registrare le loro riunioni. | <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = True.<li>Tutti gli utenti hanno il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True.</ol> |
| Voglio che la maggior parte degli utenti possa registrare le riunioni, ma disabilitare selettivamente la registrazione per utenti specifici. | <ol><li>Verificare che GlobalCsTeamsMeetingPolicy abbia AllowCloudRecording = True.<li>La maggior parte degli utenti ha il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True.<li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False.</ol> |
| Voglio che la registrazione sia completamente disabilitata. | <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = False.<li>A tutti gli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False. |
| Voglio disattivare la registrazione per la maggior parte degli utenti, ma abilitare in modo selettivo la registrazione per utenti specifici. | <ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = False.<li>Alla maggior parte degli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False.<li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True. <ol> |


<a name="bd-channel"></a>
### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>Bloccare o consentire il download delle registrazioni delle riunioni del canale

Questa impostazione controlla se le riunioni del canale vengono salvate in una cartella "Registrazioni" o in una cartella "Registrazioni\Solo visualizzazione" nel canale. L'impostazione si applica ai criteri dell'utente che seleziona la registrazione per la riunione del canale.

I due valori per questa impostazione sono:

- **Consenti** (impostazione predefinita): salva le registrazioni delle riunioni del canale in una cartella "Registrazioni" nel canale. Le autorizzazioni per i file di registrazione saranno basate sulle autorizzazioni di SharePoint Online nel canale. Ciò vale anche per qualsiasi altro file caricato per il canale.

- **Blocca** : salva le registrazioni delle riunioni del canale in una cartella "Registrazioni\Solo visualizzazione" nel canale. I proprietari dei canali avranno diritti completi sulle registrazioni in questa cartella, ma i membri del canale avranno accesso in lettura senza possibilità di download.

Con PowerShell, configurare l'opzione ChannelRecordingDownload in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

A meno che non siano stati assegnati criteri personalizzati, gli utenti ottengono il criterio globale, che ha ChannelRecordingDownload configurato su Consenti per impostazione predefinita.

Affinché un utente rientri nel criterio globale, usare il cmdlet seguente per rimuovere l'assegnazione di un criterio specifico a un utente:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Per modificare il valore di ChannelRecordingDownload nel criterio globale, usare il cmdlet seguente:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> L'impostazione ChannelRecordingDownload è disponibile solo nell'anteprima del modulo PowerShell di Teams versione 2.4.1 o successiva. Per scaricare la versione di anteprima più recente del modulo, usare questo comando:
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>Attivare o disattivare la trascrizione delle registrazioni

Questa impostazione controlla la disponibilità di didascalie e funzionalità di trascrizione durante la riproduzione di registrazioni delle riunioni. Se si disattiva questa opzione, durante la riproduzione di una registrazione di riunione non saranno disponibili le opzioni **Cerca** e **Cc**. La persona che ha avviato la registrazione ha bisogno che questa impostazione sia attivata perché la registrazione includa anche una trascrizione.

> [!NOTE]
> Si noti che la trascrizione per le riunioni registrate è attualmente supportata solo per gli utenti che hanno la lingua di Teams impostata sull'inglese, e quando durante la riunione si parla inglese. Vengono archiviati insieme alle registrazioni delle riunioni nello spazio di archiviazione nel cloud di OneDrive for Business e SharePoint Online.

È possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare un criterio per le riunioni di Teams con cui controllare se chi avvia la registrazione riceve l'opzione per trascriverne la registrazione.

Nell'interfaccia di amministrazione di Microsoft Teams attivare o disattivare l'impostazione **Consenti la trascrizione** nel criterio di riunione. Per altre informazioni, vedere [Impostazioni dei criteri di riunioni per audio e video](meetings-policies-recording-and-transcription.md#allow-transcription).

Con PowerShell, configurare l'opzione AllowTranscription in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

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
|Voglio che tutti gli utenti dell'azienda possano generare la trascrizione quando avviano la registrazione di una riunione. |<ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowTranscription = True. <li>Tutti gli utenti hanno il criterio csTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = True. </ol>|
|Voglio che la maggior parte degli utenti possa trascrivere le registrazioni di riunioni, ma disabilitare selettivamente la trascrizione per utenti specifici. |<ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowTranscription = True. <li>La maggior parte degli utenti ha il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = True. <li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = False. </ol>|
|Voglio disabilitare completamente la trascrizione delle registrazioni. |<ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowTranscription = False. <li>A tutti gli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowTranscription = False. </ol>|
|Voglio disabilitare la trascrizione per la maggior parte degli utenti, ma abilitare in modo selettivo la trascrizione per utenti specifici. |<ol><li>Verificare che il criterio CsTeamsMeetingPolicy globale abbia AllowCloudRecording = False. <li>Alla maggior parte degli utenti è stato assegnato il criterio CsTeamsMeetingPolicy globale OPPURE uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = False. <li>A tutti gli altri utenti è stato assegnato uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = True. </ol>|

### <a name="terms-of-use-acceptance"></a>Accettazione delle condizioni per l'utilizzo
Se l'organizzazione dispone di un criterio di registrazione delle riunioni che si desidera che gli utenti accettino prima di registrare una riunione, utilizzare la funzionalità [Condizioni per l'utilizzo di Azure Active Directory](/azure/active-directory/conditional-access/terms-of-use). Questa funzionalità consente agli utenti di accettare i termini dei criteri utente dell'organizzazione prima di accedere a Microsoft Teams. Questa funzionalità non è specifica per fare clic sul pulsante di registrazione, ma è correlata all'uso di Teams o di altre app Microsoft 365 in generale. Si consiglia di aggiungere le informazioni sulla registrazione della riunione alle condizioni per l'utilizzo generali per l'uso di Teams o Microsoft 365. 

## <a name="permissions-and-storage"></a>Autorizzazioni e archiviazione

Le registrazioni delle riunioni vengono archiviate nello spazio di archiviazione nel cloud di OneDrive for Business e SharePoint Online. La posizione e le autorizzazioni dipendono dal tipo di riunione e dal ruolo dell'utente nella riunione. Le autorizzazioni predefinite applicate alla registrazione sono elencate di seguito. Gli utenti con diritti di modifica completi sul file di registrazione video possono modificare le autorizzazioni e condividerle in un secondo momento con altri utenti in base alle esigenze.

### <a name="non-channel-meetings"></a>Riunioni non di canale

- La registrazione viene archiviata in una cartella denominata **Registrazioni** nello spazio di OneDrive for Business dell'utente che ha fatto clic su Registra. 

  Esempio: <i>OneDrive for Business di chi registra</i>/**Registrazioni**

- Alle persone invitate alla riunione, ad eccezione degli utenti esterni, verrà automaticamente concessa l'autorizzazione per il file di registrazione con accesso in visualizzazione senza possibilità di download.

- Il proprietario della riunione e la persona che ha fatto clic su Registra otterranno l'accesso completo alle modifiche con la possibilità di modificare le autorizzazioni e condividere con altre persone.

### <a name="channel-meetings"></a>Riunioni di canale

Se `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` è impostato su Consenti (impostazione predefinita):

- La registrazione viene archiviata nella raccolta della documentazione del sito di Teams in una cartella denominata **Registrazioni**.

  Esempio: <i>Nome di Teams - Nome canale</i>/**Documenti**/**Registrazioni**

- Il membro che ha fatto clic su Registra ha i diritti di modifica per la registrazione.

- Le autorizzazioni di ogni altro membro sono basate sulle autorizzazioni di SharePoint Online nel canale.

Se `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` è impostato su Blocca:

- La registrazione viene archiviata nella raccolta della documentazione del sito di Teams in una cartella denominata **Registrazioni/Solo visualizzazione**. 

  Esempio: <i>Nome di Teams - Nome canale</i>/**Documenti/Registrazioni/Solo visualizzazione**

- I proprietari dei canali avranno diritti completi di modifica e download per le registrazioni in questa cartella.

- I membri del canale avranno accesso in sola visualizzazione senza possibilità di download.

Per altre informazioni su tipi di riunione specifici, vedere la tabella seguente:

| Tipo di riunione  | Chi ha fatto clic su Registra?| Dove viene salvata la registrazione? | Chi può accedere? R/W, R o condivisione  |
|-------------|-----------------------|------------------------|------------------------|
|Chiamata 1:1 con parti interne             |Chiamante                 |Account di OneDrive for Business del chiamante                        |Il chiamante è proprietario e ha i diritti completi. <br /><br />Il destinatario della chiamata (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br /> Il destinatario della chiamata (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il destinatario della chiamata.|
|Chiamata 1:1 con parti interne             |Destinatario della chiamata                 |Account di OneDrive for Business del destinatario della chiamata                        |Il destinatario della chiamata è proprietario e ha i diritti completi. <br /><br />Il chiamante (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br />Il chiamante (se in un tenant diverso) non ha accesso. Il destinatario della chiamata deve condividerlo con il chiamante.|
|Chiamata 1:1 con una chiamata esterna             |Chiamante                 |Account di OneDrive for Business del chiamante                        |Il chiamante è proprietario e ha i diritti completi.<br /> <br />Il destinatario della chiamata non ha accesso. Il chiamante deve condividerlo con il destinatario della chiamata.|
|Chiamata 1:1 con una chiamata esterna             |Destinatario della chiamata                 |Account di OneDrive for Business del destinatario della chiamata                        |Il destinatario della chiamata è proprietario e ha i diritti completi.<br /><br />Il chiamante non ha accesso. Il destinatario della chiamata deve condividerlo con il chiamante.|
|Chiamata di gruppo                                 |Qualsiasi membro della chiamata |Account di OneDrive for Business del membro del gruppo che ha fatto clic su Registra  |Il membro che ha fatto clic su Registra ha diritti completi. <br /><br /> Gli altri membri dello stesso tenant hanno diritti di lettura. <br /><br /> Gli altri membri del gruppo di tenant diversi non hanno alcun diritto.|
|Riunione ad hoc/pianificata                    |Organizzatore              |Account di OneDrive for Business dell’organizzatore                     |L'organizzatore ha i diritti completi per la registrazione. <br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura senza possibilità di download.|
|Riunione ad hoc/pianificata                    |Altro membro della riunione   |Membro della riunione che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Registra ha diritti completi sulla registrazione. <br /><br />L'organizzatore ha diritti di modifica e può condividere.<br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura senza possibilità di download.|
|Riunione ad hoc/pianificata con utenti esterni|Organizzatore              |Account di OneDrive for Business dell’organizzatore                     |L'organizzatore ha i diritti completi per la registrazione.<br /> <br /> Tutti gli altri membri della riunione provenienti dallo stesso tenant dell’organizzatore hanno accesso in lettura senza possibilità di download. <br /><br /> Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione ad hoc/pianificata con utenti esterni|Altro membro della riunione   |Membro che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Registra ha diritti completi sulla registrazione. L'organizzatore ha diritti di modifica e può condividere. <br /><br /> Tutti gli altri membri della riunione provenienti dallo stesso tenant dell’organizzatore hanno accesso in lettura senza possibilità di download. <br /><br />Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione di canale                            |Membro del canale         |Posizione in SharePoint Online di Teams per quel canale                   |Se Set-CsTeamsMeetingPolicy -ChannelRecordingDownload è impostato su Consenti (impostazione predefinita), il membro che ha fatto clic su Registra ha i diritti di modifica per la registrazione. Le autorizzazioni di ogni altro membro sono basate sulle autorizzazioni di SharePoint Online nel canale.<Br><Br>Se Set-CsTeamsMeetingPolicy -ChannelRecordingDownload è impostato su Blocca, i proprietari dei canali avranno diritti completi sulla registrazione, ma i membri del canale avranno accesso in lettura senza possibilità di download.|

<a name="temp-storage"></a>
### <a name="temporary-storage-when-unable-to-upload-to-onedrive-for-business-and-sharepoint-online"></a>Archiviazione temporanea quando non è possibile caricare in OneDrive for Business e SharePoint Online

Se non è possibile caricare una registrazione della riunione in OneDrive for Business e SharePoint Online, sarà temporaneamente disponibile per il download da Teams per 21 giorni prima che venga eliminata. Al momento, l'amministratore non può controllare o gestire questo aspetto, inclusa la capacità di eliminazione.

Le registrazioni delle riunioni potrebbero finire in questa risorsa di archiviazione temporanea per i motivi seguenti:

- Per le riunioni non di canale se la registrazione dell'utente non ha una configurazione per OneDrive for Business o se lo spazio in OneDrive for Business ha esaurito la quota di archiviazione
- Per una riunione di canale se il sito di SharePoint Online ha esaurito la quota di archiviazione o se non è stato ancora effettuato il provisioning del sito
- Se sono abilitati specifici criteri di OneDrive for Business e SharePoint Online che impediscono agli utenti di caricare file quando non sono compresi in intervalli IP specifici e così via.

La conservazione della registrazione per questa archiviazione temporanea è interessata dal messaggio di chat stesso. Di conseguenza, qualsiasi eliminazione del messaggio di chat originale per la registrazione impedirà agli utenti di accedere alla registrazione. Esistono due scenari che possono influire su questo problema:

- **L'utente elimina manualmente il messaggio di chat**: in questo scenario, poiché il messaggio originale è scomparso, gli utenti non potranno più accedere alla registrazione e non saranno più disponibili altri download. Tuttavia, la registrazione stessa può essere comunque conservata nei sistemi interni Microsoft per un periodo di tempo, non superiore al periodo originale di 21 giorni.

- **La registrazione del messaggio di chat viene eliminata dai criteri di conservazione della chat**: le registrazioni in archiviazione temporanea vengono direttamente collegate al criteri di conservazione della chat. Di conseguenza, anche se le registrazioni nello spazio di archiviazione temporanea di Teams verranno conservate per impostazione predefinita per 21 giorni prima dell'eliminazione, se il messaggio di chat viene eliminato prima del periodo di 21 giorni, a causa dei criteri di conservazione dei messaggi di chat, anche la registrazione verrà eliminata. Non è possibile recuperare le registrazioni dopo questa operazione.

### <a name="planning-for-storage"></a>Pianificazione dell'archiviazione

Le dimensioni di una registrazione di 1 ora sono pari a 400 MB. Assicurarsi di aver compreso la capacità necessaria per i file registrati e di avere spazio di archiviazione sufficiente in OneDrive for Business e SharePoint Online.  Leggere [Impostare lo spazio di archiviazione predefinito per OneDrive for Business](/onedrive/set-default-storage-space) e [Gestire i limiti di archiviazione dei siti di SharePoint Online](/sharepoint/manage-site-collection-storage-limits) per comprendere lo spazio di archiviazione di base incluso nella sottoscrizione e come acquistare spazio di archiviazione aggiuntivo.

 <a name="auto-expiration"></a>
### <a name="auto-expiration-of-teams-meeting-recordings"></a>Scadenza automatica delle registrazioni delle riunioni di Teams: 

> [!IMPORTANT]
>
> La funzionalità di scadenza automatica descritta in questo articolo non è ancora stata lanciata. Per altre informazioni sulla data di rilascio, vedere la [roadmap (ID funzionalità: 84580)](https://www.microsoft.com/microsoft-365/roadmap?searchterms=82057&filters=&searchterms=84580).
> 
> Stiamo fornendo informazioni su come funzionerà questa funzionalità in FUTURO, per pianificarla e modificare le impostazioni dei criteri di Teams in anticipo.
>
> Il comando per modificare preventivamente l'impostazione di scadenza predefinita in Teams non è ancora disponibile per l'impostazione.  Quando l'impostazione sarà disponibile per la modifica, verrà pubblicato un post aggiornato del Centro messaggi.
>
>

Vedere le domande frequenti per gli amministratori e gli utenti finali per raccogliere informazioni su come funzionerà la scadenza automatica delle registrazioni delle riunioni di Teams, quali azioni è possibile intraprendere ora e quali azioni sarà possibile eseguire dopo il lancio della funzionalità.
  
## <a name="frequently-asked-questions"></a>Domande frequenti

**Qual modifica verrà effettuata?**
  
Stiamo introducendo un'impostazione di scadenza predefinita di 60 giorni per tutte le registrazioni delle riunioni di Teams appena create. Ciò significa che per impostazione predefinita, tutte le registrazioni delle riunioni di Teams create dopo l'abilitazione di questa funzionalità verranno eliminate 60 giorni dopo la data di creazione. Se gli amministratori vogliono che le registrazioni delle riunioni scadano prima o dopo il parametro predefinito, possono modificare l'impostazione di scadenza. I sistemi OneDrive e SharePoint monitoreranno la data di scadenza impostata per tutte le registrazioni delle riunioni e le sposteranno automaticamente nel Cestino alla data di scadenza.

**Chi verrà interessato da questo cambio?**
  
Chiunque archivi una registrazione di una riunione di Teams (non di canale, canale o riunione ad hoc) in OneDrive o SharePoint.

**Perché è consigliabile usare questa funzionalità?**
  
È consigliabile usare questa funzionalità per limitare lo spazio di archiviazione di OneDrive o SharePoint usato dalle registrazioni delle riunioni di Teams (nota: in genere usano circa 400 MB all'ora di registrazione).
  
**Perché stiamo introducendo questa modifica?**
  
I nostri clienti, grazie ai loro feedback, ci hanno fatto sapere che desiderano avere un maggiore controllo sullo spazio di archiviazione delle registrazioni delle riunioni di Teams, il 99% delle quali, in media, non vengono riguardate dopo 60 giorni.
  
**Perché questa opzione verrà attivata per impostazione predefinita?**
  
Riteniamo che quasi tutti i clienti trarranno vantaggio dalla riduzione del carico di archiviazione nel tenant rimuovendo le registrazioni che probabilmente non verranno mai riguardate dopo 60 giorni. Il nostro obiettivo è offrire un'esperienza più pulita possibile per tutti i clienti per impostazione predefinita.
  
**Verranno eliminati automaticamente anche se si accede o si scaricano i dati?**
  
L'accesso al file non modifica la data di scadenza.
  
**La data di scadenza è visibile come colonna nell'elenco?**

Gli utenti con accesso in visualizzazione alla registrazione vedranno un'icona rossa accanto al file nella cartella OneDrive o SharePoint 14 giorni prima della scadenza del file. Attualmente non è possibile aggiungere una colonna a un elenco con la data di scadenza.
  
**Come viene calcolata la data di scadenza?**
  
La data di scadenza viene calcolata a partire dal giorno in cui viene creata la registrazione della riunione più il numero predefinito di giorni impostato nell'impostazione di Teams dall'amministratore.
  
**È possibile modificare la data di scadenza per ogni registrazione, ad esempio in modo che la data di scadenza dei dati A sia di 30 giorni e la data di scadenza dei dati B sia di 60 giorni?**

Sì, la data di scadenza è impostata per ogni file. Gli utenti possono modificare la data di scadenza nel riquadro dei dettagli di un file selezionato in OneDrive o SharePoint.

**In che modo un amministratore può modificare la data di scadenza?**
  
Gli amministratori potranno modificare l'impostazione di scadenza predefinita in PowerShell o nell'interfaccia di amministrazione di Teams prima del rilascio della funzionalità. L'impostazione non è ancora disponibile per la modifica. Quando l'impostazione sarà disponibile per la modifica, verrà pubblicato un post aggiornato del Centro messaggi. All'avvio della funzionalità, gli amministratori possono modificare questa impostazione nell'interfaccia di amministrazione di Teams. La modifica delle impostazioni di scadenza influirà solo sulle nuove registrazioni delle riunioni di Teams create da quel punto in poi. Non influirà sulle registrazioni effettuate prima di tale data.

I valori dei giorni di scadenza possono essere impostati nel modo seguente:
  
- Il valore può essere compreso tra 1 e 99.999 (massimo 273 anni).
- Il valore può anche essere -1 per impostare il TMR in modo che non scada mai.

Gli amministratori non possono modificare la data di scadenza per registrazioni delle riunioni di Teams esistenti già caricate in OneDrive o SharePoint prima del rilascio di questa funzionalità. Ciò protegge l'intento dell'utente proprietario della registrazione di Teams.
  
**Un amministratore può impostare il TMR in modo che non scada mai?**
  
 Sì, gli amministratori possono impostare il TMR in modo che non scada mai.
  
**La riproduzione della registrazione modifica la data di scadenza?**

No, la riproduzione non influisce sulla data di scadenza.
  
**Cosa accade alla data di scadenza se la registrazione viene scaricata e ricaricata?**

La data di scadenza verrà cancellata se il file viene ricaricato, indipendentemente dallo SKU dell'utente.
  
**Cosa succede se si copia o si sposta la registrazione in un percorso o un sito diverso?**

La data viene conservata solo per i file delle registrazioni di Teams spostati. Un file copiato non avrà data di scadenza, così come una registrazione ricaricata.
  
**In che modo gli utenti finali possono modificare la data di scadenza di una specifica registrazione di una riunione di Teams?**
  
Chiunque disponga di autorizzazioni di modifica ed eliminazione delle registrazione delle riunioni di Teams può modificare la data di scadenza nel riquadro dei dettagli del file in OneDrive o SharePoint.

L'utente può posticipare la scadenza di 14, 30 o 60 giorni, selezionare una data specifica in futuro o impostare il file in modo che non scada mai.
  
**Gli amministratori devono basarsi su questa funzionalità per garantire la massima conformità e sicurezza?**
  
No, gli amministratori non devono fare affidamento su questa funzione per la protezione legale poiché gli utenti finali possono modificare la data di scadenza di tutte le registrazioni che controllano.
  
**Questa funzionalità implicherà la conservazione dei file?**
  
No, i file non verranno conservati a causa di questa funzionalità o delle relative impostazioni. Se un utente con autorizzazioni di eliminazione tenta di eliminare una registrazione di una riunione di Teams con l'impostazione di scadenza attiva, l'azione da parte dell'utente verrà eseguita.

**I criteri di conservazione e/o eliminazione impostati nel Centro sicurezza e conformità sostituiranno l'impostazione di scadenza delle registrazioni delle riunioni di Teams?**
  
Sì, tutti i criteri impostati nel Centro sicurezza e conformità avranno la precedenza completa. Ad esempio:
  
- Se si dispone di un criterio che indica che tutti i file in un sito devono essere conservati per 100 giorni e l'impostazione di scadenza è di 30 giorni, il file di registrazione verrà conservato per l'intero periodo di 100 giorni.  
- Se si dispone di un criterio di eliminazione che indica che tutte le registrazioni verranno eliminate dopo 5 giorni e si ha un'impostazione di scadenza per un file di registrazione di 30 giorni, il file verrà eliminato dopo 5 giorni.

**Cosa accade alla scadenza di una registrazione?**
  
Alla data di scadenza, la registrazione viene spostata nel Cestino di OneDrive o SharePoint e il campo della data di scadenza viene cancellato. Questa azione da parte del sistema è esattamente uguale a quella eseguita da un utente all'eliminazione del file. Il ciclo di vita del Cestino seguirà successivamente il percorso normale. Se l'utente recupera la registrazione dal Cestino, questa non verrà eliminata di nuovo da questa funzionalità perché la data di scadenza è stata cancellata, a meno che l'utente finale non abbia impostato una nuova data di scadenza nel file.
  
**In che modo ricevo una notifica sulla scadenza del file?**
  
Tutti gli utenti con accesso in visualizzazione vedranno una notifica sulla data di scadenza nella finestra della chat di Teams.
  
Tutti gli utenti con accesso in visualizzazione vedranno un'icona rossa accanto al file nella cartella OneDrive o SharePoint 14 giorni prima della scadenza del file.
  
Il proprietario del file riceverà una notifica tramite e-mail alla scadenza della registrazione e verrà indirizzato al Cestino per recuperarla, se lo desidera.
  
**Quali SKU sono necessari per questa funzionalità?**
  
Per impostazione predefinita, tutti gli SKU avranno questa funzionalità e gli utenti A1 avranno un periodo di scadenza di 30 giorni, non modificabile.
  
**La scadenza del file è un evento controllato e sarà possibile visualizzarlo nei log di audit?**
  
Sì, le scadenze dei file verranno visualizzate come eventi di eliminazione del sistema nel log di controllo.
  
**Cosa devo fare se voglio che l'amministratore abbia il pieno controllo sul ciclo di vita delle registrazioni e non voglio dare agli utenti finali la possibilità di ignorare la data di scadenza?**
  
È consigliabile usare i criteri di conservazione e/o eliminazione di sicurezza e conformità disponibili come parte dello SKU di conformità E5. Questa offerta è destinata a risolvere problemi legali amministrativi complessi e basati sul contratto di servizio.

Questa funzione è concepita esclusivamente come un meccanismo di pulizia leggero per ridurre l'ingombro di archiviazione creato dalle registrazioni delle riunioni di Teams.
  
**Quando verrà eliminato il file?**
  
Il file verrà eliminato entro 5 giorni dalla data di scadenza, anche se questa non è una garanzia.
  
**Le future richieste di registrazione migrate da Stream (versione classica) dopo il rilascio di questa funzionalità avranno anche la scadenza automatica?**
  
No, le registrazioni migrate non avranno una scadenza. Al contrario, si consiglia agli amministratori di eseguire la migrazione solo delle registrazioni che vogliono conservare. Verranno forniti maggiori dettagli nella documentazione sulla migrazione.
  
## <a name="manage-meeting-recordings"></a>Gestire le registrazioni delle riunioni

Le registrazioni delle riunioni vengono archiviate come file video in OneDrive for Business e SharePoint Online e seguono le opzioni di gestione e governance disponibili in tali piattaforme. Per altre informazioni, vedere [Panoramica sulla governance di SharePoint Online](/sharepoint/governance-overview), [Guida di OneDrive for Business per le aziende](/onedrive/plan-onedrive-enterprise) o [Guida di OneDrive for Business per le piccole imprese](/onedrive/one-drive-quickstart-small-business).

Per le riunioni non di canale, le registrazioni vengono archiviate nello spazio di OneDrive for Business del registratore, in modo che la gestione della proprietà e della conservazione dopo che un dipendente lascia l'organizzazione segua il normale [processo di OneDrive for Business e SharePoint Online](/onedrive/retention-and-deletion#the-onedrive-deletion-process).

## <a name="closed-captions-for-recordings"></a>Sottotitoli codificati per le registrazioni

I sottotitoli codificati per le registrazioni delle riunioni di Teams saranno disponibili durante la riproduzione solo se l'utente ha attivato la trascrizione al momento della registrazione. Gli amministratori devono [attivare la trascrizione della registrazione tramite criteri](#turn-on-or-turn-off-recording-transcription) per assicurarsi che gli utenti abbiano la possibilità di registrare le riunioni con la trascrizione.

I sottotitoli consentono di creare contenuto inclusivo per i visualizzatori di tutte le capacità. In qualità di proprietario, è possibile nascondere i sottotitoli nella registrazione della riunione, anche se la trascrizione della riunione sarà ancora disponibile in Teams, a meno che non venga eliminata.

Oggi i sottotitoli codificati per il file video di registrazione sono collegati alla trascrizione della riunione di Teams. Questo collegamento rimarrà per tutta la durata del file nella maggior parte dei casi, ma può essere interrotto se il file video viene copiato all'interno dello stesso sito di OneDrive for Business o SharePoint Online, con conseguente mancata disponibilità dei sottotitoli nel file video copiato.

Eventuali modifiche future al collegamento tra la trascrizione in Teams e la registrazione verranno chiarite qui e nelle notifiche del Centro messaggi. Se apporteremo modifiche in futuro, ci assicureremo che i file di registrazione che risalgono a meno di 60 giorni contengano la trascrizione della riunione sotto forma di sottotitoli.

> [!NOTE]
> Saranno presenti sottotitoli codificati solo in inglese (la trascrizione della riunione non è ancora disponibile in GCC).

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>eDiscovery e conformità per le registrazioni delle riunioni

### <a name="ediscovery"></a>eDiscovery

Le registrazioni delle riunioni vengono archiviate in OneDrive for Business e SharePoint Online, che sono conformi a Microsoft 365 e Office 365 Tier-D. Per supportare le richieste di e-Discovery per gli amministratori di conformità interessati alle registrazioni delle riunioni o delle chiamate, il messaggio di registrazione completata è disponibile nella funzionalità di ricerca contenuto per la conformità per Microsoft Teams. Gli amministratori di conformità possono cercare la parola chiave "registrazione" nella riga dell'oggetto dell'elemento nell'anteprima della ricerca di contenuto per la conformità e individuare le registrazioni di riunioni e chiamate nell'organizzazione.

Inoltre, il file video di registrazione delle riunioni è disponibile tramite ricerche di eDiscovery per i file in SharePoint Online e OneDrive for Business.

Per altre informazioni su eDiscovery, vedere l'articolo [Soluzioni di eDiscovery per Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Criteri di conservazione

È possibile applicare etichette di conservazione automatica solo ai file video di registrazione delle riunioni di Teams tramite la proprietà ProgID. Per altre informazioni, vedere [Come applicare automaticamente un'etichetta di conservazione per le registrazioni delle riunioni di Teams](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

### <a name="data-loss-prevention-dlp-policies"></a>Criteri di prevenzione della perdita dei dati (DLP)

È possibile applicare i criteri di prevenzione della perdita dei dati ai file di registrazione delle riunioni anche tramite la proprietà ProgID. Nella regola DLP per i file in SharePoint Online e OneDrive for Business impostare le condizioni seguenti:

- Proprietà documento = *ProgID*
- Valore = *Media.Meeting*

Per altre informazioni sulla prevenzione della perdita dei dati, vedere l’articolo [Informazioni sulla prevenzione della perdita di dati](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
