---
title: Usare OneDrive for Business e SharePoint per le registrazioni delle riunioni
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come passare da Stream a OneDrive for Business e SharePoint di registrazione delle riunioni in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfbff25ff4f241b18baa6b313977c687c73c8262
ms.sourcegitcommit: b7da2655607a17cde9537ed9e00db29b4c1a68df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53219123"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usare OneDrive for Business e SharePoint o Stream per le registrazioni delle riunioni

> [!Note]
> Il cambiamento dall'uso di Microsoft Stream OneDrive for Business e microsoft SharePoint per le registrazioni delle riunioni sarà un approccio a fasi.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 ottobre 2020<br> *(Completa)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Si abilita il criterio Teams riunione in modo che le registrazioni delle riunioni OneDrive for Business e SharePoint invece di Microsoft Stream (classica)|
|Distribuzione a partire dal 7 gennaio 2021<br> *(Completa)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tutte le nuove registrazioni delle riunioni Teams verranno salvate in OneDrive for Business e SharePoint a meno che questa modifica non venga ritardata modificando i criteri riunione Teams dell'organizzazione e impostandoli in modo esplicito su Flusso **.** La visualizzazione dei report dei criteri come Stream non è sufficiente. È necessario impostare in modo esplicito il valore del criterio su **Stream**.|
|Distribuzione a partire dall'11 gennaio 2021<br> *(Completa)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC solo**<br> Anche GCC i clienti possono rifiutare esplicitamente l'accesso a partire dal 5 ottobre, ma non è possibile acconsentire esplicitamente. Questa funzionalità verrà lanciata a tutti GCC clienti a partire dall'11 gennaio 2021, a meno che non si sia scelto di rifiutare esplicitamente l'opzione.<br>  <br>A partire dall'11 gennaio 2021, tutte le nuove registrazioni delle riunioni di Teams per i clienti di GCC verranno salvate in OneDrive for Business e SharePoint a meno che non si ritardi questa modifica modificando i criteri riunione Teams dell'organizzazione e impostandoli esplicitamente su **Flusso**. <br><br>Se si è scelto di rifiutare esplicitamente l'opzione ma si è pronti per attivare questa funzionalità, è possibile farlo impostando esplicitamente i criteri riunione di Teams su **OneDrive for Business**. |
|Distribuzione a partire dall'1 marzo 2021<br> *(Completa)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC high e DoD**<br> I clienti possono ora abilitare le registrazioni delle riunioni nel cloud Microsoft Teams per la prima volta. Queste registrazioni verranno archiviate e riprodotte in OneDrive e SharePoint per impostazione predefinita. |
|Distribuzione a partire dal 7 luglio 2021<br> *(Completa)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tutti i clienti (Enterprise, Education e GCC)**<br> Per una riunione di Teams registrata in OneDrive e SharePoint ed è stata trascritta anche in tempo reale durante la riunione, è ora possibile cercare in Microsoft Search per trovare il file di registrazione della riunione in base alla trascrizione. |
|Distribuzione incrementale a partire dal 16 agosto 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tutti i clienti (Enterprise, Education e GCC)**<br>Non è possibile salvare nuove registrazioni delle riunioni in Microsoft Stream (classica); Tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate OneDrive for Business e SharePoint anche se hanno cambiato i criteri Teams riunione in Stream.<br><br> È consigliabile che i clienti, per controllare meglio la modifica all'interno dell'organizzazione, acconsentano esplicitamente ogni volta che si è a proprio agio con la modifica, invece di attendere che si ripeta. |

Microsoft Teams ha un nuovo metodo per salvare le registrazioni delle riunioni. Come prima fase di una transizione dal classico Microsoft Stream al nuovo [stream,](/stream/streamnew/new-stream)questo metodo archivia le registrazioni in Microsoft OneDrive for Business e SharePoint in Microsoft 365 e offre molti vantaggi.

> [!NOTE]
> Se la Teams di una riunione non viene caricata correttamente in OneDrive/SharePoint, la registrazione verrà salvata temporaneamente in Servizi multimediali di Azure (AMS). Dopo l'archiviazione in AMS, non vengono effettuati tentativi per caricare automaticamente la registrazione in OneDrive/SharePoint o stream.

Le registrazioni delle riunioni archiviate in AMS sono disponibili per 21 giorni prima di essere eliminate automaticamente. Gli utenti possono scaricare il video da AMS se devono conservarne una copia.

I vantaggi dell'uso di OneDrive for Business e SharePoint per l'archiviazione delle registrazioni includono:

- Criteri di conservazione per Teams registrazione delle riunioni (TMR) (etichette di autoretenzione S+C E5)
- Trarre vantaggio dalla governance OneDrive for Business e SharePoint delle informazioni
- Facile impostare le autorizzazioni e la condivisione
- Condividere registrazioni con utenti guest (utenti esterni) solo con condivisione esplicita
- Richiedi flusso di accesso
- Fornire OneDrive for Business e SharePoint condivisi
- Le registrazioni delle riunioni sono disponibili più velocemente
- Trascrizione della base di ricerca registrata nella riunione
- **Passare al supporto tenant** locale
- Supporto multi-geo: le registrazioni vengono archiviate in un'area geografica specifica dell'utente
- Portare il proprio supporto per la chiave (BYOK)

Vedere l'elenco completo delle [funzionalità disponibili oggi e cosa aspettarsi nel corso del tempo.](/stream/streamnew/features-new-version-stream) 

Per altre informazioni, vedere "Novità Microsoft Teams registrazioni delle riunioni".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurare l'opzione di registrazione della riunione per OneDrive for Business e SharePoint

L'opzione di registrazione della riunione è un'impostazione a Teams livello di criteri. L'esempio seguente mostra come impostare i criteri globali. Assicurarsi di impostare l'opzione di registrazione della riunione per i criteri assegnati agli utenti.

> [!Note]
> Teams la propagazione delle modifiche ai criteri delle riunioni può richiedere del tempo. Controllare di nuovo dopo alcune ore di impostazione, quindi disconnettersi e accedere di nuovo all'app desktop Teams o semplicemente riavviare il computer.

1. Installare Teams PowerShell di PowerShell.

   > [!NOTE]
   > Skype for Business Online Connector fa attualmente parte dell'Teams di PowerShell più recente. Se si usa la versione pubblica più recente Teams PowerShell, non è necessario installare Skype for Business Online Connector. Vedere [Gestire Skype for Business Online con PowerShell.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)

2. Avviare PowerShell come amministratore.

3. Installare [Teams modulo di PowerShell](./teams-powershell-install.md).

4. Importare il modulo MicrosoftTeams e accedere come Teams amministratore.


   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Usare [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) per impostare un criterio Teams riunione per la transizione dallo spazio di archiviazione Stream a OneDrive for Business e SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se ad alcuni utenti è stato assegnato un criterio per organizzatore o per utente, è necessario impostare questa impostazione su questo criterio se si vuole che archivino anche le registrazioni delle riunioni in OneDrive for Business e SharePoint. Per altre informazioni, vedere [Gestire i criteri riunione in Teams](meeting-policies-in-teams.md).

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Rifiutare esplicitamente di OneDrive for Business e SharePoint continuare a usare Stream

Anche se un criterio indica che è impostato su **Stream**, potrebbe non essere impostato. In genere, se il criterio non è impostato, l'impostazione predefinita è **Flusso**. Tuttavia, con questa nuova modifica, se si vuole rifiutare esplicitamente di usare SharePoint o OneDrive for Business, è necessario reimpostare i criteri su Stream per assicurarsi che **Stream** sia l'impostazione predefinita. 

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Autorizzazioni o accesso basato sui ruoli

> [!Note]
> È consigliabile che il destinatario sia un utente connesso durante la condivisione Teams registrazioni riunioni. Selezionare **l'opzione Persone nell'organizzazione** quando si condivide il file come documentato in Condividi SharePoint [file o cartelle.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) La condivisione esterna non è progettata per la distribuzione di file di grandi dimensioni o di un numero elevato di file. Per evitare frodi e abusi, potrebbero verificarsi problemi quando si condivide una grande quantità di dati con utenti esterni.

|Tipo di riunione                               | Who fatto clic su Record?| Dove si trova la registrazione?                               |Who ha accesso? R/W, R o condivisione                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Chiamata 1:1 con parti interne             |Chiamante                 |Account OneDrive for Business chiamante                        |Il chiamante è proprietario e ha diritti completi. <br /><br />Il chiamato (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br /> Il chiamato (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il chiamato.|
|Chiamata 1:1 con parti interne             |Chiamato                 |Account OneDrive for Business del OneDrive for Business chiamata                        |Il chiamato è proprietario e ha diritti completi. <br /><br />Chiamante (se nello stesso tenant ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br />Il chiamante (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il chiamante.|
|Chiamata 1:1 con una chiamata esterna             |Chiamante                 |Account OneDrive for Business chiamante                        |Il chiamante è proprietario e ha diritti completi.<br /> <br />Il chiamato non ha accesso. Il chiamante deve condividerlo con il chiamato.|
|Chiamata 1:1 con una chiamata esterna             |Chiamato                 |Account OneDrive for Business del OneDrive for Business chiamata                        |Il chiamato è proprietario e ha diritti completi.<br /><br />Il chiamante non ha accesso. Il chiamante deve condividerlo con il chiamante.|
|Chiamata di gruppo                                 |Qualsiasi membro della chiamata |Membro del gruppo che ha fatto clic sull'account OneDrive for Business record  |Il membro che ha fatto clic su Record ha diritti completi. <br /><br /> Altri membri dello stesso tenant hanno diritti di lettura. <br /><br /> Gli altri membri del gruppo di tenant diversi non hanno alcun diritto.|
|Riunione adhoc/pianificata                    |Organizzatore              |Account OneDrive for Business organizzatore                     |L'organizzatore ha i diritti completi per la registrazione. <br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura.|
|Riunione adhoc/pianificata                    |Altro membro della riunione   |Membro della riunione che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Record ha i diritti completi per la registrazione. <br /><br />L'organizzatore ha i diritti di modifica e può condividere.<br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura.|
|Riunione adhoc/pianificata con utenti esterni|Organizzatore              |Account OneDrive for Business organizzatore                     |L'organizzatore ha i diritti completi per la registrazione.<br /> <br /> Tutti gli altri membri della riunione dallo stesso tenant dell'organizzatore hanno accesso in lettura. <br /><br /> Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione adhoc/pianificata con utenti esterni|Altro membro della riunione   |Membro che ha fatto clic su Record                                  |Il membro che ha fatto clic su Record ha i diritti completi per la registrazione. L'organizzatore ha i diritti di modifica e può condividere. <br /><br /> Tutti gli altri membri della riunione dallo stesso tenant dell'organizzatore hanno accesso in lettura. <br /><br />Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione del canale                            |Membro del canale         |Teams posizione SharePoint per il canale                   |Il membro che ha fatto clic su Record ha i diritti di modifica per la registrazione. <br /> <br />Le autorizzazioni di ogni altro membro si basano sulle autorizzazioni SharePoint canale.|

## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove verrà archiviata la registrazione della riunione?**

- Per le riunioni non del Canale, la  registrazione viene archiviata in una cartella denominata Registrazioni che si trova al livello superiore del OneDrive for Business che appartiene alla persona che ha avviato la registrazione della riunione. Esempio:

  <i>Il nome del registratore OneDrive for Business</i> / **Registrazioni**

- Per le riunioni del Canale, la registrazione viene archiviata nella raccolta Teams documentazione del sito in una cartella denominata **Registrazioni.** Esempio:

  <i>Teams - Nome canale</i> / **Documenti** / **Registrazioni**

**Quando i file di flusso (ad esempio le registrazioni) vengono archiviati in SharePoint/OneDrive, come si decide dove vanno? L'amministratore ha la possibilità di cambiare la posizione in cui si trova?**

Per impostazione predefinita, tutti i file di registrazione verranno OneDrive'account dell'utente che ha selezionato **Registra**. Per le riunioni del canale, la registrazione verrà sempre SharePoint sito del canale. L'amministratore non può modificare la posizione in cui è archiviata la registrazione.

**Come si gestiscono le registrazioni di ex dipendenti?**

Poiché i video sono esattamente come qualsiasi altro file in OneDrive for Business e SharePoint, la gestione della proprietà e della conservazione dopo l'uscita di un dipendente seguirà il normale processo di OneDrive for Business e [SharePoint.](/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**Who le autorizzazioni per visualizzare la registrazione della riunione?**

- Per le riunioni non del Canale, tutti gli invitati alle riunioni, ad eccezione degli utenti esterni, riceveranno automaticamente un collegamento condiviso personalmente. Gli utenti esterni dovranno essere aggiunti esplicitamente all'elenco condiviso dall'organizzatore della riunione o dalla persona che ha avviato la registrazione della riunione.

- Per le riunioni del Canale, le autorizzazioni vengono ereditate dall'elenco dei proprietari e dei membri nel canale.

> [!NOTE]
> Non si riceverà un messaggio di posta elettronica al termine del salvataggio della registrazione, ma la registrazione verrà visualizzata nella chat della riunione al termine. Questa operazione si verifica molto più velocemente di quanto non accadesse in Stream in precedenza.

**Come si gestiscono le didascalie?**

I sottotitoli codificati Teams registrazioni delle riunioni saranno disponibili durante la riproduzione solo se l'utente aveva attivato la trascrizione al momento della registrazione. Gli amministratori devono [attivare la trascrizione della registrazione tramite criteri](/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription) per assicurarsi che gli utenti hanno la possibilità di registrare le riunioni con la trascrizione.

I sottotitoli consentono di creare contenuti inclusivi per gli utenti di tutte le abilità. I proprietari possono nascondere le didascalie nella registrazione della riunione, anche se la trascrizione della riunione sarà ancora disponibile Teams a meno che non venga eliminato. 

I sottotitoli codificati sono supportati Teams registrazioni delle riunioni per 60 giorni dalla registrazione della riunione.

I sottotitoli codificati non sono completamente supportati se la registrazione Teams riunione viene spostata o copiata dalla posizione originale in OneDrive for Business o SharePoint.

> [!NOTE]
> Ci saranno sottotitoli codificati solo in inglese (la trascrizione della riunione non è ancora disponibile in GCC).

**In che modo verrà influenzata la quota di archiviazione?**

Teams i file di registrazione delle riunioni vengono OneDrive for Business e SharePoint e sono inclusi nella quota per tali servizi. Vedere [SharePoint quota e quota](/sharepoint/sites/plan-site-maintenance-and-management#quotas) OneDrive for Business [quota](/onedrive/set-default-storage-space).

Si ottiene più spazio di [archiviazione OneDrive for Business](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) rispetto a Stream e più spazio di archiviazione fungible con SharePoint.

**Come si riproduce una registrazione Teams riunione?**

Il video verrà riprodotto nel lettore video di OneDrive for Business o SharePoint a seconda di dove si accede al file.

**Se si prevede di deprecazione dell'aggiunta a Stream, i video esistenti rimarranno così com'è e per quanto tempo?**

Lo stream come piattaforma non sarà deprecato nel prossimo futuro. I video attualmente in diretta in Stream rimarranno lì fino a quando non inizieremo a eseguire la migrazione. Al momento della migrazione, questi video verranno migrati anche a OneDrive for Business o SharePoint. Per altre [informazioni, vedere Migrazione classica](/stream/streamnew/classic-migration) di Stream.

**Come si applica un'etichetta di conservazione alle registrazioni Microsoft Teams riunione?**

Vedere [Come applicare automaticamente un'etichetta di conservazione.](/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Come si assegnano i criteri agli utenti in Microsoft Teams e quali criteri hanno la precedenza?**

Vedere [Quali criteri hanno la precedenza?](./assign-policies.md#which-policy-takes-precedence).

**Dove si trova la registrazione se l'utente non ha OneDrive for Business o SharePoint o se la quota di archiviazione è piena?**

La registrazione verrà atterrato nella posizione di archiviazione temporanea in cui verrà tenuta per 21 giorni. Durante questo periodo, l'organizzatore deve scaricare la registrazione. Se non viene scaricato entro 21 giorni, la registrazione viene eliminata.
