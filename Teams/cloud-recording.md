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
ms.openlocfilehash: 7e68c0563420ad2c4e2d53421dc8dfaecfc23cd1
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023979"
---
# <a name="teams-cloud-meeting-recording"></a>Registrazione delle riunioni di Teams nel cloud

In Microsoft Teams, gli utenti possono registrare le riunioni e le chiamate di gruppo per acquisire audio, video e attività di condivisione dello schermo. È anche disponibile un'opzione per la trascrizione automatica delle registrazioni, che consente agli utenti di riprodurre le registrazioni delle riunioni con sottotitoli ed esaminare gli elementi di discussione importanti nella trascrizione. La registrazione avviene nel cloud e viene salvata in OneDrive o SharePoint, in modo che gli utenti possano condividerla in modo sicuro all'interno dell'organizzazione.

Dopo la registrazione, una riunione viene automaticamente:

- Caricato in OneDrive o SharePoint
- Autorizzata per le persone invitate alla riunione
- Collegata nella chat per la riunione
- Visualizzata nella scheda Registrazioni e trascrizioni per la riunione nel calendario di Teams
- Aggiunta a vari elenchi di file in Microsoft 365: Condivisi con l'utente corrente, office.com, Consigliati, Recenti e così via.
- Indicizzata per la ricerca di Microsoft 365

Argomenti correlati: [documentazione per gli utenti finali sulla registrazione delle riunioni di Teams](https://support.microsoft.com/en-us/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> Il passaggio dall’uso di Microsoft Stream (classico) all’uso di OneDrive e SharePoint per le registrazioni delle riunioni avverrà automaticamente nel mese di agosto 2021. Per informazioni dettagliate, vedere [Usare OneDrive e SharePoint o Stream per registrare le riunioni](tmr-meeting-recording-change.md).

> [!NOTE]
> Per informazioni sull'uso dei ruoli nelle riunioni di Teams, e su come modificare i ruoli degli utenti, vedere [Ruoli nelle riunioni di Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019). Per le opzioni di registrazione degli eventi live, vedere [Criteri di registrazione degli eventi live in Teams](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Prerequisiti per la registrazione delle riunioni di Teams nel cloud

Per registrare le riunioni di un utente di Teams, è necessario abilitare OneDrive e SharePoint per il tenant. Sono inoltre necessari i prerequisiti seguenti sia per l'organizzatore della riunione che per la persona che avvia la registrazione:

- L'utente dispone di spazio di archiviazione sufficiente in OneDrive per salvare le registrazioni delle riunioni non di canale.

- Il canale di Teams dispone di spazio di archiviazione sufficiente in SharePoint per salvare le registrazioni delle riunioni del canale.

- L'utente ha impostato `CsTeamsMeetingPolicy -AllowCloudRecording` su true per registrare riunioni e chiamate di gruppo.

- L'utente ha impostato `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` su true per registrare le chiamate 1:1.

- L'utente non è un utente anonimo, guest o federato nella riunione.

- Per abilitare la trascrizione per una riunione di un utente, è necessario che l'impostazione `-AllowTranscription` sia configurata sul valore "true".

- Per consentire il salvataggio delle registrazioni delle riunioni del canale in modo che i membri del canale non possano modificarle o scaricarle, l'impostazione `CSTeamsMeetingPolicy -ChannelRecordingDownload` deve essere configurata su Blocca.

> [!IMPORTANT]
>
> Gli utenti non dovranno abilitare OneDrive o SharePoint se vogliono solo salvare e scaricare le registrazioni. Questo significa che le registrazioni non vengono archiviate in OneDrive o SharePoint, bensì in uno spazio di archiviazione temporaneo di Teams, con un limite di 21 giorni prima dell'eliminazione. Al momento l'amministratore non può controllare, gestire o eliminare questa impostazione.
>
> Per altre [informazioni sul funzionamento dell'archiviazione temporanea della registrazione delle riunioni](#temp-storage), vedere di seguito.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurare la registrazione di riunioni di Teams nel cloud per gli utenti dell'organizzazione

In questa sezione viene descritto come configurare e pianificare la registrazione delle riunioni di Teams tramite i [criteri di riunione di Teams](policy-assignment-overview.md).

### <a name="turn-on-or-turn-off-cloud-recording"></a>Attivare o disattivare la registrazione nel cloud

È possibile usare l'interfaccia di amministrazione di Microsoft Teams o PowerShell per impostare un criterio per le riunioni di Teams con cui controllare se le riunioni degli utenti possono essere registrate.

Nell'interfaccia di amministrazione di Microsoft Teams, attivare o disattivare l'impostazione **Registrazione cloud** nei criteri della riunione. Per altre informazioni, vedere [Impostazioni dei criteri di riunioni per audio e video](meetings-policies-recording-and-transcription.md#allow-cloud-recording).

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

- **Consenti** (impostazione predefinita): salva le registrazioni delle riunioni del canale in una cartella "Registrazioni" nel canale. Le autorizzazioni per i file di registrazione saranno basate sulle autorizzazioni di SharePoint nel canale. Ciò vale anche per qualsiasi altro file caricato per il canale.

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
Questa impostazione controlla la disponibilità di didascalie e funzionalità di trascrizione durante la riproduzione di registrazioni delle riunioni. La persona che ha avviato la registrazione deve attivare questa impostazione per permettere alle funzionalità di operare in fase di registrazione.
  
Con l’attivazione di questa impostazione, viene creata una copia della trascrizione archiviata con la registrazione della riunione, che permette di eseguire **ricerche**, **CC** e **trascrizioni** nella registrazione della riunione.


> [!NOTE]
> Tale trascrizione per le riunioni registrate è attualmente supportata solo per: inglese (Stati Uniti), inglese (Canada), inglese (India), inglese (Regno Unito), inglese (Australia), inglese (Nuova Zelanda), arabo (Emirati Arabi Uniti), arabo (Arabia Saudita), cinese (semplificato, Cina), cinese (tradizionale, Ras di Hong Kong), cinese (tradizionale, Taiwan), ceco (Repubblica Ceca), danese (Danimarca), olandese (Belgio), olandese (Paesi Bassi), francese (Canada), francese (Francia), finlandese (Finlandia), tedesco (Germania), greco (Grecia), ebraico (Israele), hindi (India), ungherese (Ungheria), italiano (Italia), giapponese (Giappone), coreano (Corea), norvegese (Norvegia), polacco (Polonia), portoghese (Brasile), portoghese (Portogallo), romeno (Romania), russo (Russia), slovacco (Slovacchia), spagnolo (Messico), spagnolo (Spagna), svedese (Svezia), thai (Thailandia), turco (Turchia), ucraino (Ucraina), vietnamita (Vietnam). Vengono archiviati insieme alle registrazioni delle riunioni nello spazio di archiviazione nel cloud di OneDrive e SharePoint.

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

### <a name="set-a-custom-privacy-policy-url"></a>Impostare un URL dell'informativa sulla privacy personalizzato

Gli amministratori possono aggiornare l'URL dei criteri di privacy per registrazione e trascrizione di Teams con un collegamento personalizzato per l'organizzazione. È possibile eseguire questa operazione [nell'Azure AD di amministrazione ](https://aad.portal.azure.com)usando la procedura seguente:

1. Accedere all'interfaccia di amministrazione di Azure AD.
1. Passare a Proprietà di **Azure Active Directory** > ****.
1. Aggiornare il campo **URL dell'informativa sulla privacy** con il collegamento all'informativa sulla privacy.

> [!NOTE]
> Se il campo è già stato aggiornato per l'organizzazione, non è necessario apportare modifiche.

Dopo aver aggiunto l'URL dell'informativa sulla privacy, l'informativa sulla privacy predefinita per la registrazione e la trascrizione delle riunioni di Teams verrà sostituita con il nuovo URL fornito dall'organizzazione.

> [!NOTE]
> Gli utenti anonimi, guest e federati che partecipano alle riunioni di Teams ospitate dall'organizzazione avranno ancora l'informativa sulla privacy predefinita per la registrazione e la trascrizione delle riunioni di Teams.

## <a name="permissions-and-storage"></a>Autorizzazioni e archiviazione

Le registrazioni delle riunioni vengono archiviate in OneDrive e SharePoint. La posizione e le autorizzazioni dipendono dal tipo di riunione e dal ruolo dell'utente nella riunione. Le autorizzazioni predefinite applicate alla registrazione sono elencate di seguito. Gli utenti con diritti di modifica completi sul file di registrazione video possono modificare le autorizzazioni e condividerle in un secondo momento con altri utenti in base alle esigenze.

### <a name="non-channel-meetings"></a>Riunioni non di canale

- La registrazione viene archiviata in una cartella denominata **Registrazioni** in OneDrive dell'utente che ha fatto clic su Registra. 

  Esempio: <i>Registrazioni di OneDrive</i>/**del registratore**

- Alle persone invitate alla riunione, ad eccezione dei partecipanti esterni, verrà automaticamente concessa l'autorizzazione per il file di registrazione con accesso in visualizzazione senza possibilità di download.

- Il proprietario della riunione e la persona che ha fatto clic su Registra otterranno l'accesso completo alle modifiche con la possibilità di modificare le autorizzazioni e condividere con altre persone.

### <a name="channel-meetings"></a>Riunioni di canale

Se `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` è impostato su Consenti (impostazione predefinita):

- La registrazione viene archiviata nella raccolta della documentazione del sito di Teams in una cartella denominata **Registrazioni**.

  Esempio: <i>Nome di Teams - Nome canale</i>/**Documenti**/**Registrazioni**

- Il membro che ha fatto clic su Registra ha i diritti di modifica per la registrazione.

- Le autorizzazioni di ogni altro membro sono basate sulle autorizzazioni di SharePoint nel canale.

Se `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` è impostato su Blocca:

- La registrazione viene archiviata nella raccolta della documentazione del sito di Teams in una cartella denominata **Registrazioni/Solo visualizzazione**. 

  Esempio: <i>Nome di Teams - Nome canale</i>/**Documenti/Registrazioni/Solo visualizzazione**

- I proprietari dei canali avranno diritti completi di modifica e download per le registrazioni in questa cartella.

- I membri del canale avranno accesso in sola visualizzazione senza possibilità di download.

Per altre informazioni su tipi di riunione specifici, vedere la tabella seguente:

| Tipo di riunione  | Chi ha fatto clic su Registra?| Dove viene salvata la registrazione? | Chi può accedere? R/W, R o condivisione  |
|-------------|-----------------------|------------------------|------------------------|
|Chiamata 1:1 con parti interne             |Chiamante                 |Account di OneDrive del chiamante                        |Il chiamante è proprietario e ha i diritti completi. <br /><br />Il destinatario della chiamata (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br /> Il destinatario della chiamata (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il destinatario della chiamata.|
|Chiamata 1:1 con parti interne             |Destinatario della chiamata                 |Account di OneDrive del destinatario della chiamata                        |Il destinatario della chiamata è proprietario e ha i diritti completi. <br /><br />Il chiamante (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br />Il chiamante (se in un tenant diverso) non ha accesso. Il destinatario della chiamata deve condividerlo con il chiamante.|
|Chiamata 1:1 con una chiamata esterna             |Chiamante                 |Account di OneDrive del chiamante                        |Il chiamante è proprietario e ha i diritti completi.<br /> <br />Il destinatario della chiamata non ha accesso. Il chiamante deve condividerlo con il destinatario della chiamata.|
|Chiamata 1:1 con una chiamata esterna             |Destinatario della chiamata                 |Account di OneDrive del destinatario della chiamata                        |Il destinatario della chiamata è proprietario e ha i diritti completi.<br /><br />Il chiamante non ha accesso. Il destinatario della chiamata deve condividerlo con il chiamante.|
|Chiamata di gruppo                                 |Qualsiasi membro della chiamata |Account di OneDrive del membro del gruppo che ha fatto clic su Registra  |Il membro che ha fatto clic su Registra ha diritti completi. <br /><br /> Gli altri membri dello stesso tenant hanno diritti di lettura. <br /><br /> Gli altri membri del gruppo di tenant diversi non hanno alcun diritto.|
|Riunione ad hoc/pianificata                    |Organizzatore              |Account di OneDrive dell'organizzatore                     |L'organizzatore ha i diritti completi per la registrazione. <br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura senza possibilità di download.|
|Riunione ad hoc/pianificata                    |Altro membro della riunione   |Membro della riunione che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Registra ha diritti completi sulla registrazione. <br /><br />L'organizzatore ha diritti di modifica e può condividere.<br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura senza possibilità di download.|
|Riunione ad hoc/pianificata con partecipanti esterni|Organizzatore              |Account di OneDrive dell'organizzatore                     |L'organizzatore ha i diritti completi per la registrazione.<br /> <br /> Tutti gli altri membri della riunione provenienti dallo stesso tenant dell’organizzatore hanno accesso in lettura senza possibilità di download. <br /><br /> Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione ad hoc/pianificata con partecipanti esterni|Altro membro della riunione   |Membro che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Registra ha diritti completi sulla registrazione. L'organizzatore ha diritti di modifica e può condividere. <br /><br /> Tutti gli altri membri della riunione provenienti dallo stesso tenant dell’organizzatore hanno accesso in lettura senza possibilità di download. <br /><br />Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione di canale                            |Membro del canale         |Posizione in SharePoint di Teams per quel canale                   |Se Set-CsTeamsMeetingPolicy -ChannelRecordingDownload è impostato su Consenti (impostazione predefinita), il membro che ha fatto clic su Registra ha i diritti di modifica per la registrazione. Le autorizzazioni di ogni altro membro sono basate sulle autorizzazioni di SharePoint nel canale.<Br><Br>Se Set-CsTeamsMeetingPolicy -ChannelRecordingDownload è impostato su Blocca, i proprietari dei canali avranno diritti completi sulla registrazione, ma i membri del canale avranno accesso in lettura senza possibilità di download.|

<a name="temp-storage"></a>
### <a name="temporary-storage-when-unable-to-upload-to-onedrive-and-sharepoint"></a>Archiviazione temporanea quando non è possibile caricare in OneDrive e SharePoint

Se non è possibile caricare una registrazione della riunione in OneDrive e SharePoint, sarà temporaneamente disponibile per il download da Teams per 21 giorni prima che venga eliminata. Al momento, l'amministratore non può controllare o gestire questo aspetto, inclusa la capacità di eliminazione.

Le registrazioni delle riunioni potrebbero finire in questa risorsa di archiviazione temporanea per i motivi seguenti:

- Per le riunioni non di canale, se la registrazione dell'utente non ha una configurazione per OneDrive o se lo spazio in OneDrive ha raggiunto la quota di archiviazione
- Per una riunione di canale, se il sito di SharePoint ha raggiunto la quota di archiviazione o se non è stato ancora effettuato il provisioning del sito
- Se sono abilitati specifici criteri di OneDrive e SharePoint che impediscono agli utenti di caricare file quando non sono compresi in intervalli IP specifici e così via.

La conservazione della registrazione per questa archiviazione temporanea è interessata dal messaggio di chat stesso. Di conseguenza, qualsiasi eliminazione del messaggio di chat originale per la registrazione impedirà agli utenti di accedere alla registrazione. Esistono due scenari che possono influire su questo problema:

- **L'utente elimina manualmente il messaggio di chat**: in questo scenario, poiché il messaggio originale è scomparso, gli utenti non potranno più accedere alla registrazione e non saranno più disponibili altri download. Tuttavia, la registrazione stessa può essere comunque conservata nei sistemi interni Microsoft per un periodo di tempo, non superiore al periodo originale di 21 giorni.

- **La registrazione del messaggio di chat viene eliminata dai criteri di conservazione della chat**: le registrazioni in archiviazione temporanea vengono direttamente collegate al criteri di conservazione della chat. Di conseguenza, anche se le registrazioni nello spazio di archiviazione temporanea di Teams verranno conservate per impostazione predefinita per 21 giorni prima dell'eliminazione, se il messaggio di chat viene eliminato prima del periodo di 21 giorni, a causa dei criteri di conservazione dei messaggi di chat, anche la registrazione verrà eliminata. Non è possibile recuperare le registrazioni dopo questa operazione.

### <a name="planning-for-storage"></a>Pianificazione dell'archiviazione

Le dimensioni di una registrazione di 1 ora sono pari a 400 MB. Assicurarsi di aver compreso la capacità necessaria per i file registrati e di avere spazio di archiviazione sufficiente in OneDrive e SharePoint.  Leggere [Impostare lo spazio di archiviazione predefinito per OneDrive](/onedrive/set-default-storage-space) e [Gestire i limiti di archiviazione dei siti di SharePoint](/sharepoint/manage-site-collection-storage-limits) per comprendere lo spazio di archiviazione di base incluso nella sottoscrizione e come acquistare spazio di archiviazione aggiuntivo.

 <a name="auto-expiration"></a>
### <a name="auto-expiration-of-teams-meeting-recordings"></a>Scadenza automatica delle registrazioni delle riunioni di Teams

Vedere le domande frequenti per gli amministratori e gli utenti finali per raccogliere informazioni su come funzionerà la scadenza automatica delle registrazioni delle riunioni di Teams, quali azioni è possibile intraprendere ora e quali azioni sarà possibile eseguire dopo il lancio della funzionalità.
  
Altre informazioni sulle modifiche specifiche dell'amministratore sono disponibili [qui](meeting-expiration.md#changes-to-meeting-expiration).

Altre informazioni su come gli utenti finali possono gestire la scadenza delle riunioni sono disponibili [qui](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date).
  
## <a name="manage-meeting-recordings"></a>Gestire le registrazioni delle riunioni

Le registrazioni delle riunioni vengono archiviate come file video in OneDrive e SharePoint e seguono le opzioni di gestione e governance disponibili in tali piattaforme. Per altre informazioni, vedere [Panoramica della governance di SharePoint](/sharepoint/governance-overview).

Per le riunioni non di canale, le registrazioni vengono archiviate nello spazio di OneDrive del registratore, in modo che la gestione della proprietà e della conservazione dopo che un dipendente lascia l'organizzazione segua il normale [processo di OneDrive e SharePoint](/onedrive/retention-and-deletion#the-onedrive-deletion-process).

## <a name="closed-captions-for-recordings"></a>Sottotitoli codificati per le registrazioni

I sottotitoli codificati per le registrazioni delle riunioni di Teams saranno disponibili durante la riproduzione solo se l'utente ha attivato la trascrizione al momento della registrazione. Gli amministratori devono [attivare la trascrizione della registrazione tramite criteri](#turn-on-or-turn-off-recording-transcription) per assicurarsi che gli utenti abbiano la possibilità di registrare le riunioni con la trascrizione.

I sottotitoli consentono di creare contenuto inclusivo per i visualizzatori di tutte le capacità. In qualità di proprietario, è possibile nascondere i sottotitoli nella registrazione della riunione, anche se la trascrizione della riunione sarà ancora disponibile in Teams, a meno che non venga eliminata.

Oggi i sottotitoli codificati per il file video di registrazione sono collegati alla trascrizione della riunione di Teams. Questo collegamento rimarrà per tutta la durata del file nella maggior parte dei casi, ma può essere interrotto se il file video viene copiato all'interno dello stesso sito di OneDrive o SharePoint, con conseguente mancata disponibilità dei sottotitoli nel file video copiato.

Eventuali modifiche future al collegamento tra la trascrizione in Teams e la registrazione verranno chiarite qui e nelle notifiche del Centro messaggi. In caso di modifiche future, assicurarsi che i file di registrazione con meno di 60 giorni contengano la trascrizione della riunione in forma di sottotitoli.

> [!NOTE]
> La trascrizione della riunione non è ancora disponibile in Government Community Cloud.

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>eDiscovery e conformità per le registrazioni delle riunioni

### <a name="ediscovery"></a>eDiscovery

Le registrazioni delle riunioni vengono archiviate in OneDrive e SharePoint, che sono conformi a Microsoft 365 e Office 365 Tier-D. Per supportare le richieste di e-Discovery per gli amministratori di conformità interessati alle registrazioni delle riunioni o delle chiamate, il messaggio di registrazione completata è disponibile nella funzionalità di ricerca contenuto per la conformità per Microsoft Teams. Gli amministratori di conformità possono cercare la parola chiave "registrazione" nella riga dell'oggetto dell'elemento nell'anteprima della ricerca di contenuto per la conformità e individuare le registrazioni di riunioni e chiamate nell'organizzazione.

Inoltre, il file video della registrazione della riunione è disponibile tramite ricerche di eDiscovery per i file in SharePoint e OneDrive.

Per altre informazioni su eDiscovery, vedere l'articolo [Soluzioni di eDiscovery per Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Criteri di conservazione

È possibile applicare etichette di conservazione automatica solo ai file video di registrazione delle riunioni di Teams tramite la proprietà ProgID. Per altre informazioni, vedere [Come applicare automaticamente un'etichetta di conservazione per le registrazioni delle riunioni di Teams](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings).

### <a name="microsoft-purview-data-loss-prevention-dlp-policies"></a>Criteri di Prevenzione della perdita dei dati Microsoft Purview(DLP)

È possibile applicare i criteri di prevenzione della perdita dei dati ai file di registrazione delle riunioni anche tramite la proprietà ProgID. Nella regola di prevenzione della perdita dei dati per i file in SharePoint e OneDrive impostare le condizioni seguenti:

- Proprietà documento = *ProgID*
- Valore = *Media.Meeting*

Per altre informazioni sulla prevenzione della perdita dei dati, vedere l’articolo [Informazioni sulla prevenzione della perdita di dati](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="meeting-recording-diagnostic-tools"></a>Strumenti di diagnostica per la registrazione delle riunioni
  ### <a name="user-cannot-record-meetings"></a>L'utente non può registrare le riunioni

Gli amministratori possono usare lo strumento di diagnostica seguente per verificare che l'utente sia configurato correttamente per registrare una riunione in Teams:

1. Selezionare **Esegui test** di seguito, per popolare la diagnostica nell’Admin Centre di Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Eseguire test: Registrazione riunione](https://aka.ms/MeetingRecordingDiag)

2. Nel riquadro Esegui diagnostica immettere l’indirizzo e-mail dell'utente che non può registrare le riunioni nel campo **Nome utente o E-mail** e quindi selezionare **Esegui test**.

3. I test restituiranno i passaggi successivi migliori per risolvere eventuali configurazioni degli utenti o di criteri per verificare che l'utente sia configurato correttamente per registrare una riunione in Teams.
  
  ### <a name="meeting-record-is-missing"></a>Registrazione riunione mancante

Gli amministratori possono usare lo strumento di diagnostica seguente per verificare che la registrazione della riunione sia stata completata correttamente e che sia stata caricata in Stream o OneDrive, in base all'ID riunione e all'ora di inizio della registrazione:

1. Selezionare **Esegui test** di seguito, per popolare la diagnostica nell’Admin Centre di Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Esegui test: Registrazione riunione mancante](https://aka.ms/MissingRecordingDiag)

2. Nel riquadro Esegui diagnostica, immettere l'URL della riunione nel campo **URL della riunione registrata** (in genere presente nell'invito alla riunione) e la data della riunione nel campo **Quando è stata registrata la riunione? **, quindi selezionare **Esegui il test**.

3. I test verificano che la registrazione della riunione sia stata completata correttamente e che sia stata caricata in Stream o OneDrive.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
