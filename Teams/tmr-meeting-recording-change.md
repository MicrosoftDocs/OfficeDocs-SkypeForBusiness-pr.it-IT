---
title: Usare OneDrive for Business e SharePoint per le registrazioni delle riunioni
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come passare da Stream a OneDrive for Business e all'archiviazione di registrazioni delle riunioni di SharePoint in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3172250c1bf6fe914c331712db74a83ebe98a6d
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196350"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usare OneDrive for Business e SharePoint o Stream per le registrazioni delle riunioni

> [!Note]
> Il cambiamento dall'uso di Microsoft Stream a OneDrive for Business e Microsoft SharePoint per le registrazioni delle riunioni sarà un approccio a fasi.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 ottobre 2020 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| È possibile abilitare il criterio Riunione di Teams in modo che le registrazioni delle riunioni possano essere salvate in OneDrive for Business e SharePoint invece che in Microsoft Stream (classico)|
|Distribuzione a partire dal 7 gennaio 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tutte le nuove registrazioni delle riunioni di Teams verranno salvate in OneDrive for Business e SharePoint, a meno che questa modifica non venga ritardata modificando i criteri delle riunioni di Teams dell'organizzazione e impostandoli esplicitamente su **Stream.** La segnalazione dei criteri come Stream non è sufficiente. È necessario impostare in modo esplicito il valore del criterio su **Stream.**|
|Distribuzione a partire dall'11 gennaio 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> Anche se i clienti GCC possono rifiutare esplicitamente a partire dal 5 ottobre, non è possibile acconsentire esplicitamente. Questa funzionalità verrà implementazione a tutti i clienti GCC a partire dall'11 gennaio 2021, a meno che non si sia scelto di rifiutare esplicitamente.<br>  <br>A partire dall'11 gennaio 2021, tutte le nuove registrazioni delle riunioni di Teams per i clienti GCC verranno salvate in OneDrive for Business e SharePoint, a meno che questa modifica non venga ritardata modificando i criteri di riunione di Teams dell'organizzazione e impostando esplicitamente lo **stream.** <br><br>Se si è scelto di rifiutare esplicitamente ma si è pronti ad attivare questa funzionalità, è possibile farlo impostando esplicitamente i criteri di riunione di Teams su **OneDrive for Business.** |
|Distribuzione a partire dal 1 marzo 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clienti GCC & Enterprise**<br>Non è possibile salvare le nuove registrazioni delle riunioni in **Microsoft Stream (classico).** Tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate in OneDrive for Business e SharePoint anche se hanno modificato i criteri di riunione di Teams in Stream.<br><br> È consigliabile implementare questa caratteristica prima di questa data in modo che possano controllare le tempistiche del rilascio. |
|Distribuzione a partire dal 7 luglio 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clienti del settore dell'istruzione**<br>Non è possibile salvare le nuove registrazioni delle riunioni in **Microsoft Stream (classico).** Tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate in OneDrive for Business e SharePoint anche se hanno modificato i criteri di riunione di Teams in Stream.<br><br> È consigliabile implementare questa caratteristica prima di questa data in modo che possano controllare le tempistiche del rilascio. Questa pianificazione è stata aggiornata per offrire ai clienti del settore dell'istruzione la possibilità di completare i semestrali in corso. |

> [!Note]
> Per controllare meglio le modifiche all'interno dell'organizzazione, è consigliabile acconsentire esplicitamente quando si è a proprio agio e non aspettare che si ripeta.

Microsoft Teams ha un nuovo metodo per salvare le registrazioni delle riunioni. Come prima fase di una transizione dalla versione classica di Microsoft Stream al nuovo [Stream,](https://docs.microsoft.com/stream/streamnew/new-stream)questo metodo archivia le registrazioni in Microsoft OneDrive for Business e SharePoint in Microsoft 365 e offre molti vantaggi.

I vantaggi dell'uso di OneDrive for Business e SharePoint per l'archiviazione delle registrazioni includono:

- Criteri di conservazione per le etichette di autore delle riunioni di Teams (TMR) (S+C E5)
- Vantaggi della governance delle informazioni di OneDrive for Business e SharePoint
- Facile da impostare le autorizzazioni e la condivisione
- Condividere le registrazioni con utenti guest (utenti esterni) solo con la condivisione esplicita
- Richiesta flusso di accesso
- Fornire collegamenti condivisi di OneDrive for Business e SharePoint
- Aumento della quota
- Le registrazioni delle riunioni sono disponibili più velocemente
- **Vai al supporto** tenant locale
- Supporto multi-geo: le registrazioni vengono archiviate in un'area geografica specifica per l'utente
- Supporto per BYOK (Bring your own key)

Esistono alcune limitazioni da considerare:

- Ci saranno sottotitoli solo in inglese e sarai in grado di attivare o disattivare i sottotitoli.
- Inizialmente *non* sarà possibile visualizzare, modificare ed eseguire ricerche in una trascrizione completa (tuttavia questa funzionalità verrà aggiunta tra breve).
- Non sarà possibile modificare le trascrizioni, ma sarà possibile attivare o disattivare le didascalie.
- È possibile controllare con chi si condivide la registrazione, ma non si potrà impedire agli utenti con accesso condiviso di scaricare la registrazione.
- Al termine del salvataggio, non si riceverà un messaggio di posta elettronica, ma la registrazione verrà visualizzata nella chat della riunione al termine. Questa operazione sarà molto più rapida rispetto a stream in precedenza

Per altre informazioni, guardare "Registrazione riunione".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Impostare l'opzione di registrazione di una riunione per OneDrive for Business e SharePoint

L'opzione di registrazione della riunione è un'impostazione a livello di criteri di Teams. L'esempio seguente mostra come impostare i criteri globali. Assicurarsi di impostare l'opzione di registrazione della riunione per il criterio o i criteri assegnati agli utenti.

> [!Note]
> La propagazione delle modifiche ai criteri di riunione di Teams può richiedere del tempo. Ripartire dopo alcune ore dall'impostazione, quindi disconnettersi ed eseguire di nuovo l'accesso.

1. Installare PowerShell di Skype for Business online.
**Nota:** Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams. Se si usa la versione pubblica più recente di Teams PowerShell, non è necessario installare Skype for Business Online Connector. Consulta [Gestire Skype for Business online con PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    a. Scarica [PowerShell di Skype for Business online.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    b. Seguire le istruzioni visualizzate per installarlo.

    c. Riavviare il computer.

2. Avviare PowerShell come amministratore

3. Importare SkypeOnline Connector e accedere come amministratore di Teams.

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Usare [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) per impostare un criterio di riunione di Teams per la transizione dallo spazio di archiviazione di Stream a OneDrive for Business e SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se alcuni utenti hanno assegnato criteri per organizzatore o per utente, è necessario impostare questa impostazione su questo criterio se si vuole che archivino anche le registrazioni delle riunioni in OneDrive for Business e SharePoint. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Rifiutare esplicitamente di usare OneDrive for Business e SharePoint per continuare a usare Stream

Anche se un criterio indica che è impostato su **Stream,** potrebbe non essere impostato. In genere, se il criterio non è impostato, l'impostazione predefinita è **Stream.** Tuttavia, con questa nuova modifica, se si vuole rifiutare esplicitamente di usare SharePoint o OneDrive for Business, è necessario reimpostare i criteri su **Stream** per assicurarsi che **Stream** sia l'impostazione predefinita.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Autorizzazioni o accesso basato sui ruoli

> [!Note]
> È consigliabile che il destinatario sia un utente connesso quando condivide le registrazioni delle riunioni di Teams. Selezionare **l'opzione Persone dell'organizzazione** quando si condivide il file come documentato in file o cartelle [di SharePoint.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) La condivisione esterna non è progettata per la distribuzione di file di grandi dimensioni o per un numero elevato di file. Per evitare situazioni di frode e abuso, potrebbero verificarsi problemi durante la condivisione di una grande quantità di dati con utenti esterni.

|Tipo di riunione                               | Chi ha fatto clic su Registra?| Dove si trova la registrazione?                               |Chi ha accesso? R/W, R o condivisione                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Chiamata 1:1 con parti interne             |Chiamante                 |Account di OneDrive for Business del chiamante                        |Il chiamante è proprietario e ha diritti completi. <br /><br />Il chiamato (se nello stesso tenant) ha accesso di sola lettura. Nessun accesso di condivisione. <br /><br /> Il chiamato (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il chiamato.|
|Chiamata 1:1 con parti interne             |Chiamato                 |Account di OneDrive for Business del chiamato                        |Il chiamato è proprietario e ha i diritti completi. <br /><br />Chiamante (se nello stesso tenant ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br />Il chiamante (se in un tenant diverso) non ha accesso. Il chiamato deve condividerlo con il chiamante.|
|Chiamata 1:1 con chiamata esterna             |Chiamante                 |Account di OneDrive for Business del chiamante                        |Il chiamante è proprietario e ha diritti completi.<br /> <br />Il chiamato non ha accesso. Il chiamante deve condividerlo con il chiamato.|
|Chiamata 1:1 con chiamata esterna             |Chiamato                 |Account di OneDrive for Business del chiamato                        |Il chiamato è proprietario e ha i diritti completi.<br /><br />Il chiamante non ha alcun accesso. Il chiamato deve condividerlo con il chiamante.|
|Chiamata di gruppo                                 |Qualsiasi membro della chiamata |Membro che ha fatto clic sull'account di OneDrive for Business del record  |Il membro che ha fatto clic su Record ha i diritti completi. <br /><br /> Gli altri membri dello stesso tenant hanno diritti di lettura. <br /><br /> Gli altri membri di diversi tenant non hanno alcun diritto su di esso.|
|Adhoc/Scheduled meeting                    |Organizzatore              |Account di OneDrive for Business dell'organizzatore                     |L'organizzatore ha i diritti completi per la registrazione. <br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura.|
|Adhoc/Scheduled meeting                    |Altro membro della riunione   |Membro che ha fatto clic su Record                                  |Il membro che ha fatto clic su Registra ha i diritti completi per la registrazione. <br /><br />L'organizzatore ha diritti di modifica e può condividere.<br /><br /> Tutti gli altri membri hanno accesso in lettura.|
|Adhoc/Scheduled meeting with external users|Organizzatore              |Account di OneDrive for Business dell'organizzatore                     |L'organizzatore ha i diritti completi per la registrazione.<br /> <br /> Tutti gli altri membri della riunione nello stesso tenant dell'organizzatore hanno accesso in lettura. <br /><br /> Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Adhoc/Scheduled meeting with external users|Altro membro della riunione   |Membro che ha fatto clic su Record                                  |Il membro che ha fatto clic su Registra ha i diritti completi per la registrazione. L'organizzatore ha diritti di modifica e può condividere. <br /><br /> Tutti gli altri membri della riunione nello stesso tenant dell'organizzatore hanno accesso in lettura. <br /><br />Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione del canale                            |Membro del canale         |Posizione di SharePoint di Teams per quel canale                   |Il membro che ha fatto clic su Registra ha diritti di modifica per la registrazione. <br /> <br />Le autorizzazioni di ogni altro membro si basano sulle autorizzazioni di SharePoint del canale.|

## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove verrà archiviata la registrazione della riunione?**

- Per le riunioni non di canale, la  registrazione viene archiviata in una cartella denominata Registrazioni che si trova al livello superiore di OneDrive for Business che appartiene alla persona che ha avviato la registrazione della riunione. Esempio:

  <i>OneDrive for Business</i> del registratore / **Registrazioni**

- Per le riunioni del canale, la registrazione viene archiviata nella raccolta della documentazione del sito di Teams in una cartella denominata **Registrazioni.** Esempio:

  <i>Nome team - Nome del canale</i> / **Documenti** / **Registrazioni**

**Quando i file di flusso (ad esempio le registrazioni) vengono archiviati in SharePoint/OneDrive, come si decide dove vengono archiviati? L'amministratore ha la possibilità di cambiare la posizione in cui viene snodato?**

Per impostazione predefinita, tutti i file di registrazione vengono vai all'account OneDrive dell'utente che ha selezionato **Registra.** Per le riunioni del canale, la registrazione sarà sempre sul sito di SharePoint del canale. L'amministratore non può cambiare la posizione in cui è archiviata la registrazione.

**Come si gestiscono le registrazioni di ex dipendenti?**

Poiché i video sono come qualsiasi altro file in OneDrive for Business e SharePoint, la gestione della proprietà e della conservazione dopo che un dipendente lascia il computer seguirà il normale processo di OneDrive for Business e [SharePoint.]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**Chi ha le autorizzazioni per visualizzare la registrazione della riunione?**

- Per le riunioni non di canale, tutti gli invitati alle riunioni, tranne gli utenti esterni, riceveranno automaticamente un collegamento personale condiviso. Gli utenti esterni dovranno essere aggiunti esplicitamente all'elenco condiviso dall'organizzatore della riunione o dalla persona che ha avviato la registrazione della riunione.

- Per le riunioni del canale, le autorizzazioni vengono ereditate dall'elenco dei proprietari e dei membri del canale.

**Come si gestiscono le trascrizioni?**

I clienti che acconsentono esplicitamente a questa anteprima non hanno sottotitoli codificati disponibili nelle registrazioni delle riunioni di Teams migrate a OneDrive for Business e SharePoint.Stiamo lavorando per aggiungere sottotitoli, a partire da sottotitoli codificati in inglese, alle registrazioni delle riunioni in T4 CY2020.

I sottotitoli codificati saranno disponibili nelle registrazioni delle riunioni di Teams per i clienti che hanno acconsentito esplicitamente a consentire le trascrizioni come descritto nelle [registrazioni cloud di Teams.](cloud-recording.md)

Le didascalie aiutano a creare contenuti inclusivi per chi ha tutte le abilità. I proprietari possono nascondere le didascalie, anche se la trascrizione sarà ancora disponibile in Teams, a meno che non si eliminino le didascalie da Teams. Informazioni [su come attivare o disattivare le registrazioni delle riunioni.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

I sottotitoli codificati sono supportati per le registrazioni delle riunioni di Teams per 60 giorni dalla registrazione della riunione.

I sottotitoli codificati non sono completamente supportati se la registrazione della riunione di Teams viene spostata o copiata dalla posizione originale in OneDrive for Business o SharePoint.

**In che modo influisce sulla quota di archiviazione?**

I file di registrazione delle riunioni di Teams sono disponibili in OneDrive for Business e SharePoint e sono inclusi nella quota per tali servizi. Vedere [Quota di SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [quota di OneDrive for Business.](https://docs.microsoft.com/onedrive/set-default-storage-space)

Con [OneDrive for Business](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) si ottiene più spazio di archiviazione rispetto a Stream e più spazio di archiviazione fungibile con SharePoint.

**Come si riproduce la registrazione di una riunione di Teams?**

Il video verrà riprodotto nel lettore video di OneDrive for Business o SharePoint, a seconda di dove si accede al file.

**Se si prevede di deprecare l'aggiunta a Stream, i video esistenti manteranno e per quanto tempo?**

Lo streaming come piattaforma non sarà deprecato nel prossimo futuro. I video attualmente disponibili in Stream rimarranno in stream finché non verrà avviata la migrazione. Al momento della migrazione, verrà eseguita la migrazione di questi video anche a OneDrive for Business o SharePoint. Per altre [informazioni, vedere La migrazione a Stream](https://docs.microsoft.com/stream/streamnew/classic-migration) classico.

**Come si applica un'etichetta di conservazione?**

Vedere [come applicare automaticamente un'etichetta di conservazione.](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Come si assegnano i criteri agli utenti in Microsoft Teams e quali criteri hanno la precedenza?**

Vedere [Quali criteri hanno la precedenza?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).
