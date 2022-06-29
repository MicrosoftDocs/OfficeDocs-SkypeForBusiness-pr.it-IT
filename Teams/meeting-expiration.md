---
title: Criteri per le riunioni e scadenza delle riunioni in Microsoft Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Informazioni su come usare le impostazioni dei criteri riunione per controllare la scadenza delle riunioni in Microsoft Teams.
ms.openlocfilehash: 08ca5a75b8dd470b006d44e562eb795f814faba6
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529688"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Criteri per le riunioni e scadenza delle riunioni in Microsoft Teams

[I criteri per](meeting-policies-overview.md) le riunioni in Microsoft Teams vengono usati per controllare se gli utenti dell'organizzazione possono avviare e pianificare le riunioni e le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. È possibile gestire i criteri delle riunioni nell'interfaccia di amministrazione di Microsoft Teams o usando i cmdlet [PowerShell Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy.

Le impostazioni dei criteri riunione che controllano se gli utenti possono avviare e pianificare le riunioni e anche la scadenza delle riunioni pianificate dagli utenti. Quando scade il collegamento per l'accesso alla riunione e l'ID conferenza per una riunione, nessuno può partecipare alla riunione. Le impostazioni dei criteri di riunione seguenti determinano se gli utenti possono avviare e pianificare le riunioni in Teams. In questo articolo vengono illustrate le impostazioni delle riunioni.

- [Riunione immediata nei canali](meeting-policies-in-teams-general.md#meet-now-in-channels): controlla se un utente può avviare una riunione estemporanea in un canale.
- [Pianificazione delle riunioni del canale](meeting-policies-in-teams-general.md#channel-meeting-scheduling): controlla se un utente può pianificare una riunione in un canale.
- [Pianificazione delle riunioni private](meeting-policies-in-teams-general.md#private-meeting-scheduling): controlla se un utente può pianificare una riunione privata in Teams. Una riunione è privata quando non viene pubblicata in un canale in un team.
- [Componente aggiuntivo di Outlook](meeting-policies-in-teams-general.md#outlook-add-in): controlla se un utente può pianificare una riunione privata da Outlook. Una riunione è privata quando non viene pubblicata in un canale in un team.
- [Riunione immediata nelle riunioni private](meeting-policies-in-teams-general.md#meet-now-in-private-meetings): controlla se un utente può avviare una riunione privata estemporanea.

Per impostazione predefinita, queste impostazioni sono attivate. Quando una di queste impostazioni è disattivata, qualsiasi utente a cui è assegnato il criterio non può avviare o pianificare nuove riunioni di quel tipo. Allo stesso tempo, i collegamenti di partecipazione alla riunione e gli ID conferenza di tutte le riunioni esistenti di quel tipo che l'utente ha iniziato o pianificato in precedenza scadono.

Ad esempio, se a un utente è assegnato un criterio riunione in cui queste impostazioni dei criteri riunione sono impostate su **Attivato** e quindi si disattiva l'impostazione **Consenti riunione immediata nei canali** , l'utente non può più avviare riunioni estemporanee nei canali e il canale Riunione immediata partecipa ai collegamenti creati in precedenza sono scaduti. L'utente può comunque avviare e pianificare altri tipi di riunione e partecipare a riunioni organizzate da altre persone.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Cosa succede quando scadono il collegamento per l'accesso alla riunione e l'ID conferenza?

Quando il collegamento per l'accesso alla riunione e l'ID conferenza per una riunione scadono, nessuno può partecipare alla riunione. Quando un utente tenta di partecipare alla riunione tramite il collegamento o tramite telefono, riceve un messaggio che indica che la riunione non è più disponibile. Conversazioni, file, lavagne, registrazioni, trascrizioni e altri contenuti correlati alla riunione vengono mantenuti e gli utenti possono comunque accedervi.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Cosa succede quando si attiva e disattiva un'impostazione dei criteri riunione?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Attivare o disattivare un'impostazione dei criteri riunione

Quando un'impostazione dei criteri riunione è impostata su **Attivato**, gli utenti a cui è assegnato il criterio possono avviare o pianificare riunioni di quel tipo e tutti possono partecipare. Quando si imposta il criterio riunione su **Disattivato**, gli utenti a cui è assegnato il criterio non possono avviare o pianificare nuove riunioni di quel tipo e i collegamenti di partecipazione alla riunione e gli ID conferenza delle riunioni esistenti pianificate in precedenza dall'utente sono scaduti.

Tenere presente che l'utente può comunque partecipare alle riunioni organizzate da altre persone.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Impostare un criterio riunione da disattivato ad attivato

Quando si imposta un criterio riunione da **Disattivato** ad **Attivato**, gli utenti a cui è assegnato il criterio possono avviare o pianificare riunioni di quel tipo. Se un'impostazione dei criteri riunione è disattivata e quindi di nuovo attivata per un utente, tutte le riunioni pianificate in precedenza (e scadute) organizzate dall'utente diventano attive e le persone possono parteciparvi usando il collegamento per partecipare alla riunione o tramite telefono.  

## <a name="meeting-expiration-scenarios"></a>Scenari di scadenza delle riunioni

Ecco un riepilogo del funzionamento della scadenza delle riunioni per ognuna delle impostazioni dei criteri riunione illustrate in questo articolo.

|Se vuoi...&nbsp;&nbsp; |Esegui questa operazione&nbsp;&nbsp;&nbsp;&nbsp;  |Comportamento di partecipazione a una riunione&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Scadenza delle riunioni private Riunione immediata avviata da un utente&nbsp;&nbsp;|Disattiva **Riunione immediata nelle riunioni private**.&nbsp;&nbsp;|Nessuno può partecipare **alle riunioni riunione** immediata private avviate dall'utente.|
|Scadenza delle riunioni private pianificate da un utente&nbsp;&nbsp;|Disattivare **la pianificazione delle riunioni private** _e_ il **componente aggiuntivo Outlook**. &nbsp;&nbsp;|Nessuno può partecipare a riunioni private pianificate dall'utente. In questo modo si impedisce alle persone di partecipare alle riunioni seguenti:<ul><li>Riunioni private che si sono verificate in passato.</li><li>Riunioni private pianificate per il futuro e non ancora avvenute.</li><li>Istanze future di riunioni private ricorrenti.</li></ul><br>Sia **la pianificazione delle riunioni private** che il **componente aggiuntivo di Outlook** devono essere disattivati per scadere le riunioni private pianificate da un utente. Se un'impostazione è disattivata e l'altra è attivata, i collegamenti di partecipazione alle riunioni e gli ID conferenza delle riunioni esistenti rimangono attivi e non saranno scaduti.|
|Canale Scadenza **Riunioni immediata** avviate da un utente&nbsp;&nbsp;|Disattivare **Riunione immediata nei canali** _e_ disattivare **la pianificazione delle riunioni del canale**.&nbsp;&nbsp;|Nessuno può partecipare alle riunioni **Riunione immediata** del canale avviate dall'utente.|
|Scadenza delle riunioni del canale pianificate da un utente&nbsp;&nbsp;|Disattivare **la pianificazione delle riunioni del canale**.&nbsp;&nbsp;|Nessuno può partecipare alle riunioni del canale pianificate dall'utente. In questo modo si impedisce alle persone di partecipare alle riunioni seguenti:<ul><li>Riunioni di canale che si sono verificati in passato.</li><li>Riunioni di canale pianificate per il futuro e che non si sono ancora verificate.</li><li>Istanze future di riunioni del canale ricorrente.</li></ul>|

Se si vuole consentire alle persone di accedere alle riunioni pianificate o avviate in precedenza da un utente specifico, è possibile:

- Attivare l'impostazione dei criteri riunione per l'utente.
- Disattivare l'impostazione dei criteri riunione per l'utente e chiedere a un altro utente che ha abilitato l'impostazione dei criteri di creare una nuova riunione per sostituire la riunione scaduta.

> [!NOTE]
> Se la riunione è stata inviata da un delegato, a cui sono state concesse le autorizzazioni per inviare inviti alle riunioni per conto di un'altra persona, ad esempio un responsabile, l'impostazione dei criteri della riunione viene applicata alla persona che ha concesso l'autorizzazione (il responsabile).

## <a name="changes-to-meeting-expiration"></a>Modifiche alla scadenza della riunione

Tutte le registrazioni delle riunioni di Teams appena create avranno una scadenza predefinita di 120 giorni. Questa opzione è attivata per impostazione predefinita per tutti i tenant. Ciò significa che per impostazione predefinita, tutte le FUNZIONALITÀ create *dopo che questa funzionalità è stata attivata* verranno eliminate 120 giorni dopo la data di creazione. Gli amministratori possono anche impostare le riunioni in modo che **non scada mai automaticamente**. Il sistema OneDrive e SharePoint monitorerà la data di scadenza impostata in tutti i TMR e sposterà automaticamente ITR nel Cestino alla data di scadenza.

> [!NOTE]
> Una copia della trascrizione della riunione viene salvata in OneDrive SharePoint e una seconda copia viene salvata in Exchange in un archivio temporaneo. La copia OSDP scade alla scadenza automatica di TMR.

La scadenza automatica delle riunioni è un meccanismo di pulizia leggero che consente di ridurre il disordine di archiviazione creato da regole di gestione dello spazio di archiviazione meno recenti. In media, in tutti i clienti, il 96% dei TMR non viene guardato dopo 60 giorni e il 99% non viene guardato dopo 110 giorni. Siamo convinti che quasi tutti i clienti beneficeranno della riduzione del carico di archiviazione nel proprio tenant rimuovendo le registrazioni che probabilmente non verranno controllate di nuovo dopo 60 giorni. Il nostro obiettivo è fornire un'esperienza il più pulita possibile per tutti i clienti per impostazione predefinita.

Usare la scadenza delle riunioni per limitare l'uso di OneDrive o SharePoint per l'archiviazione cloud basata sui record delle riunioni di Teams. Una tipica registrazione di una riunione richiede circa 400 MB all'ora di registrazione.

> [!NOTE]
> La data di scadenza predefinita massima per gli utenti A1 è di 30 giorni.

### <a name="expiration-date"></a>Data di scadenza

- La data di scadenza viene calcolata come **giorno di creazione** più il **numero predefinito di giorni impostato nel criterio di Teams dall'amministratore**.
- La riproduzione non influisce sulla data di scadenza.

### <a name="change-the-default-expiration-date"></a>Modificare la data di scadenza predefinita

Gli amministratori possono modificare l'impostazione di scadenza predefinita in PowerShell o nell'interfaccia di amministrazione di Teams. Qualsiasi modifica avrà effetto solo sui nuovi TMR *creati* da quel momento in poi. Non influirà su registrazioni create prima di tale data. Gli amministratori non possono modificare la data di scadenza nei TMR esistenti. Questo viene fatto per proteggere la decisione dell'utente che possiede il TMR. Questa impostazione consente di controllare sia le riunioni che le chiamate.

Il valore della data di scadenza può essere impostato nel modo seguente:

- Valore minimo: **1 giorno**
- Valore massimo: **99.999 giorni**
- Puoi anche impostare la data di scadenza su **-1** in modo che le registrazioni non scada mai.

Esempio di comando di PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

È possibile impostare la data di scadenza nell'interfaccia di amministrazione di Teams in **Criteri riunione.** Dopo aver attivato **Riunioni scade automaticamente,** si ottiene l'opzione per impostare una scadenza per la registrazione.

![Amministrazione screenshot del centro dei criteri di scadenza delle riunioni.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Sicurezza e conformità

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>Devo fare affidamento su questa funzionalità per una stretta adesione alla sicurezza e alla conformità?

No, non è consigliabile affidarsi a questa opzione per la protezione legale in quanto gli utenti finali possono modificare la data di scadenza di tutte le registrazioni che controllano.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>I criteri di conservazione e/o di eliminazione impostati nel Centro sicurezza & conformità sostituiscono l'impostazione di scadenza della registrazione delle riunioni di Teams?

Sì, tutti i criteri impostati nel Centro conformità avranno la precedenza.

Ad esempio:

- Se hai un criterio che indica che tutti i file in un sito devono essere conservati per 100 giorni e l'impostazione di scadenza per la registrazione di una riunione di Teams è di 30 giorni, la registrazione verrà conservata per tutti i 100 giorni.
- Se hai un criterio di eliminazione che indica che tutte le registrazioni delle riunioni di Teams verranno eliminate dopo cinque giorni e hai un'impostazione di scadenza per la registrazione di una riunione di Teams di 30 giorni, la registrazione verrà eliminata dopo cinque giorni.

### <a name="will-this-feature-enforce-file-retention"></a>Questa funzionalità implicherà la conservazione dei file?

No, i file non verranno conservati a causa di questa funzionalità o delle relative impostazioni. Se un utente con autorizzazioni di eliminazione tenta di eliminare un TMR con un'impostazione di scadenza, verrà eseguita l'azione di eliminazione dell'utente.

### <a name="what-skus-are-required-for-this-feature"></a>Quali SKU sono necessari per questa funzionalità?

- Per impostazione predefinita, tutti gli SKU avranno questa funzionalità.
- Per impostazione predefinita, gli utenti A1 hanno una scadenza massima di 30 giorni, ma possono modificare la data di scadenza in base alle esigenze.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>Cosa succede se si vuole che l'amministratore abbia il controllo completo sul ciclo di vita delle registrazioni delle riunioni e non si voglia offrire agli utenti finali la possibilità di ignorare la data di scadenza?

È consigliabile usare i criteri di conservazione e/o eliminazione della sicurezza e/o della conformità. Questa offerta è destinata a risolvere problemi legali amministrativi complessi e basati sul contratto di servizio.

La funzionalità di scadenza automatica è esclusivamente pensata come un leggero meccanismo di pulizia per ridurre il disordine di archiviazione creato dalle vecchie registrazioni delle riunioni di Teams.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>Le future richieste di registrazione migrate da Stream (versione classica) dopo il rilascio di questa funzionalità avranno anche la scadenza automatica?

No, le registrazioni migrate non avranno una scadenza. Al contrario, si consiglia agli amministratori di eseguire la migrazione solo delle registrazioni che vogliono conservare. Verranno forniti maggiori dettagli nella documentazione sulla migrazione.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>Qual è la differenza tra questa funzionalità e il messaggio di scadenza visualizzato quando un caricamento TMR in OneDrive e SharePoint non riesce?

Quando una registrazione non viene caricata in OneDrive o SharePoint, l'applicazione Teams visualizza un messaggio nella chat che gli utenti hanno fino a 21 giorni per scaricare il TMR prima che venga eliminato definitivamente dal server di Teams. Questa esperienza di scadenza esistente a causa di caricamenti TMR non riusciti non è correlata alla funzionalità di scadenza automatica di OneDrive e SharePoint illustrata nel documento della Guida.

### <a name="how-do-i-know-the-distribution-of-tmr-playbacks-so-i-know-what-the-optimal-auto-expiration-default-should-be-for-my-tenant"></a>Ricerca per categorie conosce la distribuzione delle riproduzioni TMR, quindi so quale dovrebbe essere l'impostazione predefinita ottimale per la scadenza automatica per il tenant?

1. Trovare il video nella raccolta.
1. Seleziona **...** >  **Dettagli**
1. Selezionare il numero di visualizzazioni nella parte superiore del riquadro dei dettagli.

Verranno visualizzate le statistiche dei file che mostrano:

- Il numero di spettatori unici
- Numero di visualizzazioni totali
- La tendenza di spettatori e visualizzazioni giorno per giorno per gli ultimi 90 giorni
- Conservazione del visualizzatore (che parte del video è stata visualizzata o non visualizzata)

### <a name="when-will-the-file-be-deleted"></a>Quando verrà eliminato il file?

La registrazione viene in genere eliminata entro un giorno dalla data di scadenza, ma in rari casi può richiedere fino a cinque giorni. Il proprietario del file riceverà una notifica tramite posta elettronica alla scadenza della registrazione e verrà indirizzato al Cestino per recuperare la registrazione.

> [!NOTE]
> Alla data di scadenza, la registrazione viene spostata nel Cestino e il campo della data di scadenza viene cancellato. Se si recupera la registrazione dal Cestino, non verrà eliminata di nuovo da questa funzionalità perché la data di scadenza è stata cancellata.

## <a name="related-topics"></a>Argomenti correlati

[Modificare la data di scadenza delle riunioni - controlli per l'utente finale](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Gestire i criteri di riunione in Teams](meeting-policies-overview.md)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Limiti e specifiche per Microsoft Teams](/microsoftteams/limits-specifications-teams)
