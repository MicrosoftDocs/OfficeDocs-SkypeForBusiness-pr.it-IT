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
description: Informazioni su come passare da Stream a OneDrive for Business e allo spazio di archiviazione per la registrazione delle riunioni di SharePoint in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8480e0c4b6d27d48eacd8e6edf2aee3583111cf21aba87df037ebc4b3d7ef6b1
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849671"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usare OneDrive for Business e SharePoint o Stream per le registrazioni delle riunioni

> [!Note]
> Il cambiamento dall'uso di Microsoft Stream OneDrive for Business e microsoft SharePoint per le registrazioni delle riunioni sarà un approccio a fasi.

|Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 ottobre 2020<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Si abilita il criterio Teams riunione in modo che le registrazioni delle riunioni OneDrive for Business e SharePoint invece di Microsoft Stream (classica)|
|Implementazione a partire dal giorno 7 gennaio 2021<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tutte le nuove registrazioni delle riunioni Teams verranno salvate in OneDrive for Business e SharePoint a meno che questa modifica non venga ritardata modificando i criteri riunione Teams dell'organizzazione e impostandoli in modo esplicito su Flusso **.** La visualizzazione dei report dei criteri come Stream non è sufficiente. È necessario impostare in modo esplicito il valore dei criteri su **Stream**.|
|Implementazione a partire dal giorno 11 gennaio 2021<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> Anche se i clienti GCC possono rifiutare esplicitamente tale opzione, a partire dal 5 ottobre, non è possibile acconsentire esplicitamente. Questa funzionalità verrà distribuita a tutti i clienti GCC a partire dall'11 gennaio 2021, a meno che non sia stata rifiutata esplicitamente.<br>  <br>A partire dall'11 gennaio 2021, tutte le nuove registrazioni delle riunioni Teams per i clienti di GCC verranno salvate in OneDrive for Business e SharePoint a meno che non si ritagli questa modifica modificando i criteri riunione Teams dell'organizzazione e impostandoli esplicitamente su **Flusso**. <br><br>Se tale funzionalità è stata rifiutata esplicitamente, ma si vuole attivarla, è possibile impostare i criteri delle riunioni di Teams in modo esplicito su **OneDrive for Business**. |
|Implementazione a partire dal giorno 1 marzo 2021<br> *(Completata)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC-High e DoD**<br> I clienti ora possono abilitare le registrazioni delle riunioni cloud in Microsoft Teams per la prima volta. Queste registrazioni verranno archiviate e riprodotte OneDrive e SharePoint per impostazione predefinita. |
|Implementazione incrementale a partire dal giorno 16 agosto 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tutti i clienti (Enterprise, Education e GCC)**<br>Non è possibile salvare nuove registrazioni delle riunioni in Microsoft Stream (classica); Tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate OneDrive for Business e SharePoint anche se hanno cambiato i criteri Teams riunione in Stream.<br><br> È consigliabile che i clienti, in modo da controllare meglio il cambiamento nell'organizzazione, acconsentano esplicitamente ogni volta che si ha familiarità con la modifica anziché attendere che venga eseguita. |

Microsoft Teams offre un nuovo metodo per salvare le registrazioni delle riunioni. Come prima fase di una transizione dal classico Microsoft Stream al nuovo [stream,](/stream/streamnew/new-stream)questo metodo archivia le registrazioni in Microsoft OneDrive for Business e SharePoint in Microsoft 365 e offre molti vantaggi.

> [!NOTE]
> Se una registrazione Teams riunione non viene caricata correttamente in OneDrive/SharePoint, la registrazione verrà salvata temporaneamente in Servizi multimediali di Azure (AMS). Dopo l'archiviazione in AMS, non vengono eseguiti tentativi di caricamento automatico della registrazione in OneDrive/SharePoint o Stream.

Le registrazioni delle riunioni archiviate in AMS sono disponibili per 21 giorni prima che vengano eliminate automaticamente. Gli utenti possono scaricare il video da AMS se devono conservarne una copia.

I vantaggi dell'uso di OneDrive for Business e SharePoint per l'archiviazione delle registrazioni includono:

- Criteri di conservazione per la registrazione delle riunioni di Teams (TMR) (etichette di autoretenzione S+C E5)
- Trarre vantaggio dalla governance OneDrive for Business e SharePoint delle informazioni
- Autorizzazioni e condivisioni facili da impostare
- Condividere registrazioni con gli utenti guest (utenti esterni) solo con condivisione esplicita
- Richiedere flusso di accesso
- Fornire OneDrive for Business e SharePoint condivisi
- Le registrazioni delle riunioni sono disponibili più velocemente
- Supporto del tenant in **locale**
- Supporto multi-geografico: le registrazioni vengono archiviate in un'area specifica dell'utente
- Supporto BYOK (Bring Your Own Key)

Consultare l'elenco completo delle [funzionalità disponibili oggi e nel tempo](/stream/streamnew/features-new-version-stream).

Per altre informazioni, guardare il video "What's New for Microsoft Teams Meeting Recordings".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurare l'opzione di registrazione della riunione per OneDrive for Business e SharePoint

L'opzione di registrazione della riunione è un'impostazione a livello di criteri di Teams. Nell'esempio seguente viene illustrato come impostare il criterio globale. Assicurarsi di impostare l'opzione di registrazione delle riunioni per il criterio o i criteri assegnati agli utenti.

> [!Note]
> La propagazione delle modifiche ai criteri delle riunioni di Teams richiede qualche tempo. È necessario ricontrollare dopo alcune ore dall'impostazione, quindi disconnettersi e accedere di nuovo all'applicazione desktop di Teams o riavviare semplicemente il computer.

1. Installare PowerShell per Teams.

   > [!NOTE]
   > Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente. Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online. Vedere [Gestire Skype for Business Online con PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Avviare PowerShell come amministratore.

3. Installare il [modulo di PowerShell per Teams](./teams-powershell-install.md).

4. Importare il modulo di Microsoft Teams e accedere come amministratore di Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

5. Usare [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) per impostare criteri riunione Teams per la transizione dallo spazio di archiviazione Stream a OneDrive for Business e SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se ad alcuni utenti è stato assegnato un criterio per organizzatore o per utente, è necessario impostare questa impostazione su questo criterio se si vuole che archivino anche le registrazioni delle riunioni in OneDrive for Business e SharePoint. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md).

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Rifiutare esplicitamente di OneDrive for Business e SharePoint continuare a usare Stream

Anche se un criterio indica che è impostato su **Stream**, potrebbe non essere impostato. In genere, se il criterio non è impostato, l'impostazione predefinita è **Flusso**. Tuttavia, con questa nuova modifica, se si vuole rifiutare esplicitamente di usare SharePoint o OneDrive for Business, è necessario reimpostare i criteri su Stream per assicurarsi che **Stream** sia l'impostazione predefinita. 

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Autorizzazioni o accesso basato sui ruoli

> [!Note]
> È consigliabile che il destinatario sia un utente connesso durante la condivisione Teams registrazioni riunioni. Selezionare **l'opzione Persone in (organizzazione)** quando si condivide il file come documentato in Condividi SharePoint [file o cartelle.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) La condivisione esterna non è progettata per la distribuzione di file di grandi dimensioni o di un numero elevato di file. Per evitare frodi e abusi, potrebbero verificarsi problemi quando si condivide una grande quantità di dati con utenti esterni.

|Tipo di riunione                               | Chi ha fatto clic su Registra?| Dove viene salvata la registrazione?                               |Chi può accedere? R/W, R o condivisione                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Chiamata 1:1 con parti interne             |Chiamante                 |Account di OneDrive for Business del chiamante                        |Il chiamante è proprietario e ha i diritti completi. <br /><br />Il destinatario della chiamata (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br /> Il destinatario della chiamata (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il destinatario della chiamata.|
|Chiamata 1:1 con parti interne             |Destinatario della chiamata                 |Account di OneDrive for Business del destinatario della chiamata                        |Il destinatario della chiamata è proprietario e ha i diritti completi. <br /><br />Il chiamante (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br />Il chiamante (se in un tenant diverso) non ha accesso. Il destinatario della chiamata deve condividerlo con il chiamante.|
|Chiamata 1:1 con una chiamata esterna             |Chiamante                 |Account di OneDrive for Business del chiamante                        |Il chiamante è proprietario e ha i diritti completi.<br /> <br />Il destinatario della chiamata non ha accesso. Il chiamante deve condividerlo con il destinatario della chiamata.|
|Chiamata 1:1 con una chiamata esterna             |Destinatario della chiamata                 |Account di OneDrive for Business del destinatario della chiamata                        |Il destinatario della chiamata è proprietario e ha i diritti completi.<br /><br />Il chiamante non ha accesso. Il destinatario della chiamata deve condividerlo con il chiamante.|
|Chiamata di gruppo                                 |Qualsiasi membro della chiamata |Account di OneDrive for Business del membro del gruppo che ha fatto clic su Registra  |Il membro che ha fatto clic su Registra ha diritti completi. <br /><br /> Altri fr dello stesso tenant hanno diritti di lettura. <br /><br /> Gli altri membri del gruppo di tenant diversi non hanno alcun diritto.|
|Riunione ad hoc/pianificata                    |Organizzatore              |Account di OneDrive for Business dell’organizzatore                     |L'organizzatore ha i diritti completi per la registrazione. <br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura.|
|Riunione ad hoc/pianificata                    |Altro membro della riunione   |Membro della riunione che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Registra ha diritti completi sulla registrazione. <br /><br />L'organizzatore ha diritti di modifica e può condividere.<br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura.|
|Riunione ad hoc/pianificata con utenti esterni|Organizzatore              |Account di OneDrive for Business dell’organizzatore                     |L'organizzatore ha i diritti completi per la registrazione.<br /> <br /> Tutti gli altri membri della riunione dallo stesso tenant dell'organizzatore hanno accesso in lettura. <br /><br /> Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione ad hoc/pianificata con utenti esterni|Altro membro della riunione   |Membro che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Registra ha diritti completi sulla registrazione. L'organizzatore ha diritti di modifica e può condividere. <br /><br /> Tutti gli altri membri della riunione dallo stesso tenant dell'organizzatore hanno accesso in lettura. <br /><br />Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione di canale                            |Membro del canale         |Teams SharePoint posizione del canale. **Nota:** il caricamento della registrazione delle riunioni del canale SharePoint non è supportato per le restrizioni basate su IP. È consigliabile usare [l'accesso condizionale di Azure.](/azure/active-directory/conditional-access/overview) |Il membro che ha fatto clic su Record ha i diritti di modifica per la registrazione. <br /> <br />Le autorizzazioni di ogni altro membro si basano sulle autorizzazioni SharePoint canale.|

## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove verrà archiviata la registrazione della riunione?**

- Per le riunioni non del Canale, la  registrazione viene archiviata in una cartella denominata Registrazioni che si trova al livello superiore del OneDrive for Business che appartiene alla persona che ha avviato la registrazione della riunione. Esempio:

  <i>il nome del registratore OneDrive for Business</i> / **Registrazioni**

- Per le riunioni del Canale, la registrazione viene archiviata nella raccolta Teams documentazione del sito in una cartella denominata **Registrazioni.** Esempio:

  <i>Teams - Nome canale</i> / **Documenti** / **Registrazioni**

**Quando i file di flusso (ad esempio le registrazioni) vengono archiviati in SharePoint/OneDrive, come si decide dove vanno? L'amministratore ha la possibilità di cambiare la posizione in cui si trova?**

Per impostazione predefinita, tutti i file di registrazione verranno OneDrive'account dell'utente che ha selezionato **Registra**. Per le riunioni del canale, la registrazione verrà sempre SharePoint sito del canale. L'amministratore non può modificare la posizione in cui è archiviata la registrazione.

**Come si gestiscono le registrazioni di ex dipendenti?**

Poiché i video sono come qualsiasi altro file in OneDrive for Business e SharePoint, la gestione della proprietà e della conservazione dopo l'uscita di un dipendente seguirà il normale processo di OneDrive for Business e [SharePoint.](/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**Who le autorizzazioni per visualizzare la registrazione della riunione?**

- Per le riunioni non del Canale, tutti gli invitati alle riunioni, ad eccezione degli utenti esterni, riceveranno automaticamente un collegamento condiviso personalmente. Gli utenti esterni dovranno essere aggiunti esplicitamente all'elenco condiviso dall'organizzatore della riunione o dalla persona che ha avviato la registrazione della riunione.

- Per le riunioni del Canale, le autorizzazioni vengono ereditate dall'elenco dei proprietari e dei membri nel canale.

> [!NOTE]
> Non si riceverà un messaggio di posta elettronica al termine del salvataggio della registrazione, ma la registrazione verrà visualizzata nella chat della riunione al termine. Questa operazione si verifica molto più velocemente di quanto non accadesse in Stream in precedenza.

**Come si gestiscono le didascalie?**

I sottotitoli codificati per le registrazioni delle riunioni di Teams saranno disponibili durante la riproduzione solo se l'utente ha attivato la trascrizione al momento della registrazione. Gli amministratori devono [attivare la trascrizione della registrazione tramite criteri](/microsoftteams/cloud-recording#turn-on-or-turn-off-recording-transcription) per assicurarsi che gli utenti abbiano la possibilità di registrare le riunioni con la trascrizione.

I sottotitoli consentono di creare contenuto inclusivo per i visualizzatori di tutte le capacità. In qualità di proprietario, è possibile nascondere i sottotitoli nella registrazione della riunione, anche se la trascrizione della riunione sarà ancora disponibile in Teams, a meno che non venga eliminata.

I sottotitoli codificati sono supportati Teams registrazioni delle riunioni per 60 giorni dalla registrazione della riunione.

I sottotitoli codificati non sono completamente supportati se la registrazione Teams riunione viene spostata o copiata dalla posizione originale in OneDrive for Business o SharePoint.

> [!NOTE]
> Saranno presenti sottotitoli codificati solo in inglese (la trascrizione della riunione non è ancora disponibile in GCC).

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
