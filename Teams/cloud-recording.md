---
title: Registrazione delle riunioni cloud di Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
f1.keywords:
- NOCSH
description: Linee guida pratiche per la distribuzione di funzionalità cloud Voice in Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38981774af168c978371b06d8de6eeedd4b16644
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825604"
---
# <a name="teams-cloud-meeting-recording"></a>Registrazione delle riunioni cloud di Teams

> [!IMPORTANT]
> **In futuro, stiamo effettuando una modifica della configurazione** in cui la caratteristica di registrazione delle riunioni di team sarà attivata per i clienti i cui dati del team sono archiviati in paese anche se Microsoft Stream non è disponibile nell'area di residenza dati in paese. Quando questa modifica ha effetto, le registrazioni delle riunioni verranno archiviate per impostazione predefinita nell'area di flusso Microsoft più vicina. Se i dati del team sono archiviati in paese e si preferisce archiviare le registrazioni delle riunioni nel paese, è consigliabile disattivare le registrazioni delle riunioni e quindi attivarle dopo la distribuzione di Microsoft Stream nell'area del paese. Per altre informazioni, vedere [dove sono archiviate le registrazioni delle riunioni](#where-your-meeting-recordings-are-stored).

In Microsoft teams gli utenti possono registrare le riunioni del team e le chiamate di gruppo per acquisire attività audio, video e condivisione dello schermo. È anche disponibile un'opzione per la trascrizione automatica delle registrazioni, che consente agli utenti di riprodurre le registrazioni delle riunioni con sottotitoli e cercare gli elementi di discussione importanti nella trascrizione. La registrazione si verifica nel cloud e viene salvata in [Microsoft Stream](https://docs.microsoft.com/stream/), in modo che gli utenti possano condividerla in tutta sicurezza nell'organizzazione.

Correlato: [documentazione dell'utente finale di teams Meeting recording](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Prerequisiti per la registrazione di teams Cloud Meeting

Per registrare le riunioni di un utente di teams, Microsoft stream deve essere abilitato per il tenant. Inoltre, sono necessari i prerequisiti seguenti sia per l'organizzatore della riunione che per la persona che avvia la registrazione:

- L'utente ha un Office 365 E1, E3, E5, a1, a3, a5, M365 business, Business Premium o Business Essentials
- L'utente deve essere concesso in licenza per Microsoft Stream<sup>1</sup> 
- L'utente ha le autorizzazioni di Microsoft Stream upload video
- L'utente ha acconsentito alle linee guida della società, se è stato configurato dall'amministratore
- L'utente dispone di spazio di archiviazione sufficiente in Microsoft Stream per le registrazioni da salvare
- L'impostazione TeamsMeetingPolicy-AllowCloudRecording dell'utente è impostata su true
- L'utente non è un utente anonimo, Guest o federato nella riunione

> [!NOTE]
> Inoltre, per consentire alla persona che avvia la registrazione di scegliere se trascrivere automaticamente la registrazione, l'impostazione TeamsMeetingPolicy-AllowTranscription dell'utente deve essere impostata su true

<sup>1</sup> L'utente deve avere la licenza per caricare/scaricare riunioni in/da Microsoft Stream, ma non ha bisogno della licenza per registrare una riunione. Se si vuole impedire a un utente di registrare una riunione Microsoft teams, è necessario concedere un TeamsMeetingPolicy con AllowCloudRecording impostato su $False.

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

Puoi usare l'interfaccia di amministrazione di Microsoft teams o PowerShell per impostare un criterio per la riunione di teams per controllare se le riunioni dell'utente possono essere registrate.

Nell'interfaccia di amministrazione di Microsoft teams attivare o disattivare l'impostazione **Consenti registrazione cloud** nel criterio riunione. Per altre informazioni, vedere [gestire i criteri delle riunioni in teams](meeting-policies-in-teams.md#allow-cloud-recording).

Usando PowerShell, configuri l'impostazione AllowCloudRecording in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Tieni presente che sia l'organizzatore della riunione che l'iniziatore della registrazione devono avere le autorizzazioni di registrazione per registrare la riunione. A meno che non siano stati assegnati criteri personalizzati agli utenti, gli utenti ottengono il criterio globale, che ha AllowCloudRecording disabilitato per impostazione predefinita.

Affinché un utente rientri nei criteri globali, usare il cmdlet seguente per rimuovere una specifica assegnazione di criteri per un utente:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Per modificare il valore di AllowCloudRecording nel criterio globale, usare il cmdlet seguente:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Scenario                                                                 |                                                                                                                                                                         Passaggi                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Voglio che tutti gli utenti della mia azienda possano registrare le loro riunioni                                    |                                                                     <ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowCloudRecording = true<li>Tutti gli utenti hanno il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = true </ol>                                                                     |
| Voglio che la maggior parte degli utenti sia in grado di registrare le proprie riunioni, ma disabilitare selettivamente utenti specifici che non sono autorizzati a registrare |        <ol><li>Conferma GlobalCsTeamsMeetingPolicy ha AllowCloudRecording = true<li>La maggior parte degli utenti ha il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = true<li>A tutti gli altri utenti è stato concesso uno dei criteri di CsTeamsMeetingPolicy con AllowCloudRecording = false</ol>         |
|                                                   Voglio che la registrazione sia disattivata per 100%                                                   |                                                                <ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowCloudRecording = false<li>A tutti gli utenti è stato concesso il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = false                                                                 |
|      Voglio che la registrazione venga disabilitata per la maggior parte degli utenti, ma in modo selettivo consente agli utenti specifici autorizzati a registrare       | <ol><li>Conferma CsTeamsMeetingPolicy globale ha AllowCloudRecording = false<li>Alla maggior parte degli utenti è stato concesso il CsTeamsMeetingPolicy globale o uno dei criteri CsTeamsMeetingPolicy con AllowCloudRecording = false<li>A tutti gli altri utenti è stato concesso uno dei criteri di CsTeamsMeetingPolicy con AllowCloudRecording = true <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Dove sono archiviate le registrazioni delle riunioni

Le registrazioni delle riunioni sono archiviate nello spazio di archiviazione cloud di Microsoft Stream. Attualmente, la caratteristica di registrazione della riunione è disattivata per i clienti i cui dati del team sono archiviati nel paese se Microsoft Stream non è disponibile nell'area di residenza dati in paesi in cui sono archiviati i dati. In futuro, la funzionalità di registrazione della riunione verrà attivata per i clienti i cui dati sono archiviati in paese anche se Microsoft Stream non è disponibile nell'area di residenza dati in paese.

Quando questa modifica avrà effetto, le registrazioni delle riunioni verranno archiviate per impostazione predefinita nell'area geografica più vicina per Microsoft Stream. Se i dati del team sono archiviati in paese e si preferisce archiviare le registrazioni delle riunioni nel paese, è consigliabile disattivare la caratteristica e quindi attivarla dopo la distribuzione di Microsoft Stream nell'area di residenza dati in paese. Per disattivare la funzionalità per tutti gli utenti dell'organizzazione, nell'interfaccia di amministrazione di Microsoft teams disattivare l'impostazione **Consenti registrazione cloud** nei criteri riunione globale teams.

Ecco un riepilogo delle operazioni che si verificano quando si attiva la registrazione delle riunioni quando questa modifica ha effetto:

|Se si attiva la registrazione delle riunioni... |Le registrazioni delle riunioni sono archiviate...  |
|---------|---------|
|prima che Microsoft Stream sia disponibile nell'area di residenza dati in paese    |nell'area del flusso Microsoft più vicina         |
|dopo che Microsoft Stream è disponibile nell'area di residenza dati in paese    | nell'area di residenza dati in paese        |

Per gli inquilini nuovi ed esistenti che non hanno ancora attivato la registrazione delle riunioni, le nuove registrazioni vengono archiviate nel paese dopo che Microsoft Stream è disponibile nell'area di residenza dei dati nazionali. Tuttavia, qualsiasi tenant che Abilita la registrazione delle riunioni prima che Microsoft Stream sia disponibile nell'area di residenza dati in-paese continuerà a usare lo spazio di archiviazione Microsoft Stream per le registrazioni esistenti e quelle nuove anche dopo che Microsoft Stream è disponibile nella pagina area di residenza dati in paese.

Per trovare l'area geografica in cui sono archiviati i dati di Microsoft Stream, fare clic su Microsoft Stream **?** nell'angolo in alto a destra fare clic **su informazioni su Microsoft Stream**, quindi fare clic sui **dati archiviati**.  Per altre informazioni sulle aree geografiche in cui Microsoft Stream archivia i dati, vedere [domande frequenti su Microsoft Stream](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Per altre informazioni sulla posizione di archiviazione dei dati tra i vari servizi in Office 365, vedere [dove si trovano i dati?](https://products.office.com/en-us/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Attivare o disattivare la trascrizione della registrazione

Quando gli utenti registrano le riunioni dei team, possono verificare se una trascrizione deve essere generata automaticamente dopo la registrazione della riunione. Se è stata disabilitata la funzionalità di trascrizione per l'organizzatore della riunione e l'iniziatore della registrazione, l'iniziatore della registrazione non otterrà la possibilità di trascrivere le registrazioni delle riunioni.

Puoi usare l'interfaccia di amministrazione di Microsoft teams o PowerShell per impostare un criterio per la riunione di teams per controllare se l'iniziatore della registrazione riceve una scelta per trascrivere la registrazione della riunione.

Nell'interfaccia di amministrazione di Microsoft teams attivare o disattivare l'impostazione **Consenti trascrizione** nei criteri della riunione. Per altre informazioni, vedere [gestire i criteri delle riunioni in teams](meeting-policies-in-teams.md#allow-transcription).

Usando PowerShell, configuri l'impostazione AllowTranscription in TeamsMeetingPolicy. Per altre informazioni, vedere [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

A meno che non siano stati assegnati criteri personalizzati agli utenti, gli utenti ottengono il criterio globale, che ha AllowTranscription disabilitato per impostazione predefinita.

Affinché un utente rientri nei criteri globali, usare il cmdlet seguente per rimuovere una specifica assegnazione di criteri per un utente:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Per modificare il valore di AllowCloudRecording nel criterio globale, usare il cmdlet seguente:

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

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell Teams](teams-powershell-overview.md)
