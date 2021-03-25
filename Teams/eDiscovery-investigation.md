---
title: Condurre un'indagine di eDiscovery sul contenuto
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su cosa fare quando è necessario eseguire eDiscovery, ad esempio quando è necessario inviare tutte le informazioni archiviate elettronicamente per procedimenti legali.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ca1a679fbdce7ca2840c41266053cf13f1452fe0
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197531"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Condurre un'indagine di eDiscovery sul contenuto in Microsoft Teams

Le grandi imprese sono spesso esposte a procedimenti legali ad alta sanzione che richiedono l'invio di tutte le informazioni archiviate elettronicamente (ESI). I contenuti di Microsoft Teams possono essere cercati e usati durante le indagini di eDiscovery.

## <a name="overview"></a>Panoramica

Tutte le chat di Microsoft Teams 1:1 o di gruppo vengono journalate nelle cassette postali dei rispettivi utenti. Tutti i messaggi del canale standard vengono inviati nel journal alla cassetta postale del gruppo che rappresenta il team. I file caricati nei canali standard sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for Business.

eDiscovery dei messaggi e dei file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [eDiscovery dei canali privati.](#ediscovery-of-private-channels)

Non tutti i contenuti di Teams sono eDiscoverable. La tabella seguente mostra i tipi di contenuto che è possibile cercare usando gli strumenti di Microsoft eDiscovery:

| Tipo di contenuto | eDiscoverable | Note |
|:--- | :--- |:--- |
|Registrazioni audio | No | |
|Contenuto della scheda|Sì|Per [altre informazioni, vedere Cercare contenuto della](#search-for-card-content) scheda.|
|Collegamenti alla chat | Sì | |
|Messaggi di chat | Sì |Sono inclusi i contenuti nei canali di Teams, le chat 1:1, le chat di gruppo 1:N e le chat con i partecipanti degli utenti guest.  |
|Frammenti di codice | No | |
|Messaggi modificati | Sì | Se l'utente è in attesa, vengono mantenute anche le versioni precedenti dei messaggi modificati. |
|Emoji, GIF e adesivi | Sì | |
|Immagini incorporate | Sì | |
|Conversazioni istantanee delle riunioni | Sì | |
|Metadati riunione<sup>1</sup> | Sì |  |
|Nome del canale | No | |
|Messaggi del canale privato | Sì | |
|Virgolette | Sì | Il contenuto tra virgolette è disponibile per la ricerca. Tuttavia, i risultati della ricerca non indicano che il contenuto è stato citato. |
|Reazioni (ad esempio mi piace, cuori e altre reazioni) | No | |
|Oggetto | Sì | |
|Tabelle | Sì | |
|Notifiche del feed | No | |
|||

<sup>1 I</sup> metadati della riunione (e della chiamata) includono quanto segue:

- Ora di inizio e fine della riunione e durata
- Partecipare e uscire da una riunione per ogni partecipante
- Partecipazione/chiamate VOIP
- Join anonimo
- Aggiunta di utenti federati
- Partecipazione di utenti guest

  L'immagine mostra un esempio di metadati della riunione.

  > [!div class="mx-imgBorder"]
  > ![L'immagine è dei metadati della riunione dei record CVR.](media/conversationOption3.png)

Ecco un esempio di conversazione istantanea tra i partecipanti durante la riunione.

![Conversazione tra i partecipanti in Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversazione tra partecipanti nei risultati della ricerca eDiscovery.](media/MeetingImConversation2.png)

Per altre informazioni sull'esecuzione di un'indagine di eDiscovery, vedere Introduzione [a Core eDiscovery.](/microsoft-365/compliance/get-started-core-ediscovery)

I dati di Microsoft Teams verranno visualizzati come messaggistica istantanea o Conversazioni nell'output di esportazione di eDiscovery di Excel. È possibile aprire il `.pst` file in Outlook per visualizzare i messaggi dopo averli esportati.

Quando si visualizza il file PST per il team, tutte le conversazioni vengono mantenute nella cartella Chat del team in Cronologia conversazioni. Il titolo del messaggio contiene il nome del team e il nome del canale. Ad esempio, l'immagine seguente mostra un messaggio di Luca che ha inviato un messaggio al canale standard di Project 7 del team Manufacturing Specs.

![Screenshot di una cartella di Team Chat nella cassetta postale di un utente in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Le chat private nella cassetta postale di un utente vengono archiviate nella cartella Chat del team in Cronologia conversazioni.

## <a name="ediscovery-of-private-channels"></a>eDiscovery dei canali privati

I record per i messaggi inviati in un canale privato vengono recapitati nella cassetta postale di tutti i membri del canale privato, anziché in una cassetta postale di gruppo. I titoli dei record vengono formattati in modo da indicare da quale canale privato sono stati inviati.

Poiché ogni canale privato ha un proprio sito di SharePoint separato dal sito del team padre, i file in un canale privato vengono gestiti in modo indipendente dal team padre.

Teams non supporta la ricerca di eDiscovery in un singolo canale all'interno di un team, quindi è necessario eseguire ricerche nell'intero team. Per eseguire una ricerca di contenuto di eDiscovery in un canale privato, eseguire una ricerca in tutto il team, nella raccolta siti associata al canale privato (per includere i file) e nelle cassette postali dei membri del canale privato (per includere i messaggi).

Usare la procedura seguente per identificare i file e i messaggi in un canale privato da includere nella ricerca eDiscovery.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Includere file del canale privato in una ricerca eDiscovery

Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Eseguire le operazioni seguenti per ottenere un elenco di tutte le raccolte siti di SharePoint associate ai canali privati del team.

    ```PowerShell
    Get-SPOSite
    ```

2. Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati ai canali privati del team e l'ID del gruppo di team padre.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Per ogni ID team o gruppo, eseguire lo script di PowerShell seguente per identificare tutti i siti del canale privato pertinenti, dove $groupID è l'ID gruppo del team.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Includere messaggi di canale privato in una ricerca eDiscovery

Prima di eseguire questa procedura, assicurarsi di avere installato la [versione più recente del modulo di PowerShell di Teams.](teams-powershell-overview.md)

1. Eseguire il comando seguente per ottenere un elenco di canali privati nel team.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Eseguire il comando seguente per ottenere un elenco di membri del canale privato.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Includere le cassette postali di tutti i membri di ogni canale privato del team come parte della query di [ricerca di eDiscovery.](/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Cercare contenuto per gli utenti guest

È possibile usare gli strumenti di eDiscovery per cercare il contenuto di Teams relativo agli utenti guest dell'organizzazione. I contenuti della chat di Teams associati a un utente guest vengono mantenuti in una posizione di archiviazione basata sul cloud e possono essere cercati usando eDiscovery. Questo include la ricerca di contenuto in conversazioni chat 1:1 e 1:N in cui un utente guest è un partecipante con altri utenti dell'organizzazione. È anche possibile cercare messaggi di canale privato in cui un utente guest è un partecipante e cercare contenuti nelle conversazioni di chat *guest:guest* in cui gli unici partecipanti sono utenti guest.

Per cercare contenuto per gli utenti guest:

1. Connettersi ad Azure AD PowerShell. Per istruzioni, vedere la sezione "Connettersi con Azure Active Directory PowerShell" in Connettersi a [Microsoft 365 con PowerShell.](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Assicurarsi di completare i passaggi 1 e 2 nell'argomento precedente.

2. Dopo aver eseguito correttamente la connessione a PowerShell di Azure AD, eseguire il comando seguente per visualizzare il nome dell'entità utente (UPN) per tutti gli utenti guest dell'organizzazione. È necessario usare l'UPN dell'utente guest quando si crea la ricerca nel passaggio 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Invece di visualizzare un elenco di nomi delle entità utente sullo schermo del computer, è possibile reindirizzare l'output del comando a un file di testo. A questo scopo, aggiungere `> filename.txt` al comando precedente. Il file di testo con i nomi delle entità utente verrà salvato nella cartella corrente.

3. In un'altra Windows PowerShell, connettersi a PowerShell & Centro sicurezza e conformità. Per istruzioni, vedere [Connettersi a PowerShell del Centro sicurezza & conformità](/powershell/exchange/connect-to-scc-powershell). È possibile connettersi con o senza usare l'autenticazione a più fattori.

4. Creare una ricerca di contenuto che cerca tutto il contenuto, ad esempio i messaggi di chat e i messaggi di posta elettronica, in cui l'utente guest specificato era un partecipante eseguendo il comando seguente.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Ad esempio, per cercare il contenuto associato all'utente guest Sara Davis, eseguire il comando seguente.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Per altre informazioni sull'uso di PowerShell per creare ricerche contenuto, vedere [New-ComplianceSearch.](/powershell/module/exchange/new-compliancesearch)

5. Eseguire il comando seguente per avviare la ricerca di contenuto creata nel passaggio 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fare clic su Mostra tutta **la**  >  **ricerca contenuto.**

7. Nell'elenco delle ricerche selezionare la ricerca creata nel passaggio 4 per visualizzare la pagina a comparsa.

8. Nella pagina a comparsa è possibile eseguire le operazioni seguenti:

   - Fare **clic su Visualizza risultati** per visualizzare i risultati della ricerca e visualizzare in anteprima il contenuto.

   - Accanto al campo **Query** fare clic su **Modifica** per modificare ed eseguire di nuovo la ricerca. Ad esempio, è possibile aggiungere una query di ricerca per limitare i risultati.

   - Fare **clic su Esporta risultati** per esportare e scaricare i risultati della ricerca.

## <a name="search-for-card-content"></a>Cercare il contenuto della scheda

I contenuti delle schede generati dalle app nei canali di Teams, nelle chat 1:1 e nelle chat 1xN vengono archiviati nelle cassette postali e possono essere cercati. Una *scheda è* un contenitore dell'interfaccia utente per brevi parti di contenuto. Le schede possono avere più proprietà e allegati e possono includere pulsanti che possono attivare le azioni delle schede. Per altre informazioni, vedere [Schede](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Come gli altri contenuti di Teams, in cui è archiviato il contenuto della scheda si basa sulla posizione in cui è stata usata la scheda. Il contenuto delle schede usate in un canale di Teams viene archiviato nella cassetta postale del gruppo Teams. Il contenuto della scheda per le chat 1:1 e 1xN viene archiviato nelle cassette postali dei partecipanti alla chat.

Per cercare il contenuto della scheda, è possibile usare le `kind:microsoftteams` condizioni di `itemclass:IPM.SkypeTeams.Message` ricerca o. Quando si esaminano i risultati della ricerca, il contenuto della scheda generato dai bot in un canale di Teams ha la proprietà di posta elettronica **Mittente/Autore** come , dove è il nome dell'app che ha generato il contenuto `<appname>@teams.microsoft.com` `appname` della scheda. Se il contenuto della scheda è stato generato da un utente, il valore **Mittente/Autore** identifica l'utente.

Quando si visualizza il contenuto della scheda nei risultati della ricerca contenuto, il contenuto viene visualizzato come allegato al messaggio. L'allegato è denominato `appname.html` , dove è il nome `appname` dell'app che ha generato il contenuto della scheda. Gli screenshot seguenti mostrano come viene visualizzato il contenuto della scheda (per un'app denominata Asana) in Teams e nei risultati di una ricerca.

**Contenuto della scheda in Teams**

![Contenuto della scheda nel messaggio del canale di Teams](media/CardContentTeams.png)

**Contenuto della scheda nei risultati della ricerca**
  
![Stesso contenuto della scheda nei risultati di una ricerca contenuto](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Per visualizzare immagini dal contenuto della scheda nei risultati della ricerca in questo momento , ad esempio i segni di spunta nello screenshot precedente, è necessario accedere a Teams (in un'altra scheda nella stessa sessione del browser che si usa per visualizzare i risultati della https://teams.microsoft.com) ricerca. In caso contrario, vengono visualizzati i segnaposto immagine.

## <a name="advanced-ediscovery"></a>Advanced eDiscovery

Alcuni contenuti di Microsoft Teams possono anche essere cercati e mantenuti usando il [flusso di lavoro Advanced eDiscovery.](/microsoft-365/compliance/overview-ediscovery-20) Mentre eDiscovery offre una gamma di funzionalità di ricerca, blocco ed esportazione, Advanced eDiscovery offre agli amministratori di conformità più strumenti per identificare le origini dati e analizzarne il contenuto.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Flusso di lavoro di gestione avanzato di eDiscovery per il contenuto di Teams

I custodi potrebbero essere membri di vari team. È possibile acquisire contenuto di Teams pertinente per questi custodi. Per istruzioni sul flusso di lavoro del responsabile, vedere Aggiungere i custodi a un caso [di eDiscovery avanzato.](/microsoft-365/compliance/add-custodians-to-case)

Dopo aver aggiunto un responsabile, fare clic **sul pulsante** Avanti, quindi sul **pulsante** Aggiungi. Viene quindi visualizzata una finestra in cui viene chiesto di selezionare altre posizioni, in cui sono visualizzate tutte le appartenenze del responsabile e le posizioni del sito di SharePoint corrispondenti per i relativi dati. Da tutte queste origini dati e team è possibile scegliere il contenuto da usare per eDiscovery, quindi mettere l'utente e tutte le origini dati identificate in blocco.

È possibile scegliere se includere il contenuto di Exchange, il relativo contenuto di OneDrive o entrambi. Il contenuto di Exchange include tutto il contenuto dell'applicazione nelle cassette postali dell'utente, ad esempio la posta elettronica, il contenuto di Teams archiviato nella propria cassetta postale e così via. Il contenuto di OneDrive include non solo il contenuto dell'utente, ma anche tutto il contenuto di Teams archiviato in OneDrive, ad esempio chat 1:1, chat 1:N e file condivisi nelle chat.

È anche possibile associare qualsiasi team di cui il responsabile è membro, in modo che siano inclusi i messaggi di chat del canale e i file a cui il responsabile ha accesso. Inoltre, qualsiasi altro team può essere associato a un responsabile.

> [!NOTE]
> eDiscovery dei messaggi e dei file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [eDiscovery dei canali privati.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>Applicazione di un blocco a un'origine dati

Se non esiste un utente specifico da designare come responsabile, è possibile mettere in blocco un'intera origine dati. Per altre informazioni sui blocchi, vedere [Gestire i blocchi in Advanced eDiscovery.](/microsoft-365/compliance/managing-holds)

Quando si crea un blocco per il contenuto di Teams, è possibile scegliere tutte le posizioni da includere nel blocco. Anche se gli utenti eliminano o modificano il contenuto, il blocco manterrà copie di tutte le versioni precedenti del contenuto.

È anche possibile usare una query facoltativa per impostare condizioni per il blocco in base a parole chiave, intervallo di date, autore e molti altri criteri. Se non si specificano parole chiave, tutti gli elementi dell'origine dati saranno soggetti al blocco.

### <a name="advanced-ediscovery-searches"></a>Ricerche avanzate di eDiscovery

È anche possibile eseguire ricerche nel contenuto di Teams. Per altre informazioni sulle ricerche, vedere [Raccogliere dati per un caso in Advanced eDiscovery.](/microsoft-365/compliance/collecting-data-for-ediscovery) Una ricerca restituirà un'intera conversazione se anche un messaggio corrisponde alla query di ricerca.

Quando si crea una query di ricerca, è possibile scegliere i custodi in modo che la ricerca sia eseguita in tutte le origini già selezionate. È anche possibile eseguire ricerche in origini non custodiali, ad esempio un sito di Teams non mappato a un utente. Sono disponibili anche query facoltative per restringere la ricerca all'interno del contenuto di Teams.

Dopo aver creato e selezionato una ricerca, viene visualizzata una finestra con altri dettagli e azioni che è possibile eseguire sulla ricerca selezionata. Se si  fa clic sul pulsante Statistiche, è possibile visualizzare le statistiche sulla ricerca, incluse le suddivisioni in base ai tipi di posizione, all'origine originale del contenuto e al fatto che il contenuto si trovi in una cassetta postale del gruppo, nella cassetta postale del singolo utente o in un sito di SharePoint. È quindi possibile visualizzare un'analisi delle origini che contribuiscono ai risultati della ricerca. È disponibile anche una **visualizzazione** Query che consente di vedere le singole parole chiave che contribuiscono ai risultati.

Dopo aver finalizzato la ricerca, è possibile fare clic sul **pulsante Aggiungi risultati** per rivedere il set e aggiungerlo a un set di revisioni. Per altre informazioni sui set di revisioni, vedere Gestire i set di revisione nel flusso di lavoro [Advanced eDiscovery](/microsoft-365/compliance/managing-review-sets) e [Set di](#review-sets-workflow) revisioni più avanti in questo articolo.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Set di revisione normali e set di revisione delle conversazioni

Quando si aggiunge una ricerca a un set di revisioni, è possibile scegliere tra un set di revisioni normale o un set di revisioni di conversazione.

Un set di revisioni normale è simile a un'esportazione. fornisce i singoli `.msg` file per il contenuto di Teams e presenta il contenuto in una visualizzazione di base. In genere si usa un normale set di revisioni quando si prevede di usare altri strumenti software per rielaborare i file in un secondo momento.

Un set di revisione delle conversazioni offre una visualizzazione in thread più intuitiva delle conversazioni; visualizza i messaggi correlati nell'ordine corretto.

> [!div class="mx-imgBorder"]
> ![Screenshot del set di revisioni delle conversazioni](media/conversationOptions2.png)

Funzionalità come la redazione sono disponibili in entrambi i tipi di set di revisioni. Per altre informazioni sui set di revisioni, vedere [Rivedere le conversazioni in eDiscovery avanzato.](/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>Opzioni di raccolta

Quando si aggiunge un set di revisioni, sono disponibili diverse opzioni come  caselle di controllo nella sezione **Opzioni** raccolta della finestra, tra cui Opzioni di recupero conversazioni e **Conversazioni di Teams.** Se si abilitano queste opzioni, verranno visualizzati anche i singoli messaggi di Teams che fanno parte del set di revisioni, con altri messaggi che li circondano per il contesto. Ad esempio, se la query è specifica e di conseguenza viene restituito un solo messaggio, l'abilitazione di queste opzioni restituirà anche diversi messaggi che portano e segue il messaggio corrispondente alla query.

Molti criteri logici vengono usati per determinare se altri messaggi forniscono contesto ai messaggi che corrispondono alla query. Ad esempio, per il contenuto di Teams, l'abilitazione di queste opzioni recupererà il messaggio padre e tutti i messaggi figlio a causa del modo in cui i messaggi sono in thread.

Vengono controllati anche gli indicatori di data e ora dei messaggi. Se un messaggio corrisponde alla query, i messaggi adiacenti che lo precedono entro un intervallo di 4 ore o che lo seguono entro un intervallo di 4 ore vengono considerati parte della conversazione e vengono inclusi anche nei risultati.

Se è necessario essere certi di quali messaggi contestuali verranno restituiti con corrispondenze alla query di ricerca, non è necessario usare queste opzioni. È possibile raccogliere tutto il contenuto oppure ampliare l'intervallo di date della ricerca in modo che più messaggi siano restituiti come risultato della query.

### <a name="review-sets-workflow"></a>Flusso di lavoro set di revisioni

È possibile visualizzare i set di revisioni esistenti o crearne di nuovi facendo clic **sulla scheda Set di** revisioni. Per altre informazioni sui set di revisioni, vedere [Gestire i set di revisioni in Advanced eDiscovery.](/microsoft-365/compliance/managing-review-sets)

Oltre ai documenti, è possibile aggiungere messaggi di posta elettronica, messaggi di Teams, messaggi di Yammer e altri contenuti al set di revisioni. All'interno di un set di revisioni è anche possibile eseguire molte delle stesse operazioni che è possibile eseguire in altri contesti, ad esempio la ricerca di contenuto e la creazione di query personalizzate. Queste operazioni si applicano solo agli elementi aggiunti al set di revisioni.

Il **pulsante Gestisci set di revisioni** include opzioni aggiuntive, ad esempio analisi, report di riepilogo, il numero di set di caricamento aggiunti e così via.

Per accedere alle visualizzazioni e ai grafici dei dati, fare clic su **Risultati singoli** Visualizzazione profilo di \> **ricerca** in alto a destra. È possibile fare clic sui cunei in questi grafici per selezionare in modo interattivo il tipo di contenuto su cui eseguire una query. Ad esempio, è possibile scegliere di eseguire query solo sul contenuto di Teams. È anche possibile salvare queste query esattamente come si salvano le query che si scrivono manualmente.

#### <a name="summary-view-text-view-and-annotate-view"></a>Visualizzazione Riepilogo, visualizzazione testo e visualizzazione annotazioni

Se si fa clic su una conversazione di Teams nel set di revisioni, viene visualizzata la visualizzazione **Riepilogo,** che visualizza un'intera conversazione di Teams come elenco di messaggi con cui è possibile interagire singolarmente. Fare clic sulla freccia rivolta verso il basso a destra di un messaggio per visualizzare un menu di scelta rapida che consente di visualizzare i dettagli del messaggio o scaricare il singolo `.msg` file. Se si fa clic sui dettagli del messaggio, viene visualizzato un riepilogo dei metadati o dei metadati completi del messaggio.

Per scaricare un PDF, fare clic sul pulsante di download nell'angolo in alto a destra della visualizzazione di riepilogo.

Fare clic **sulla scheda Visualizzazione** testo per visualizzare una visualizzazione in testo normale del testo estratto della conversazione di Teams. Questo contenuto in testo normale è adatto per l'esportazione e può essere facilmente utilizzato con altri strumenti software.

Fare clic sulla scheda **Visualizzazione annotazioni** per accedere alle caratteristiche di annotazione. Questa scheda visualizza il contenuto in un formato simile a una conversazione di Teams, ma sono disponibili anche altre opzioni per la modifica. È disponibile uno strumento a matita che è possibile usare per creare note, disegnare sul messaggio o eseguire graffi a grana fine a scopo di redazione. È anche disponibile uno **strumento di riattivazione** area che è possibile usare per disegnare un rettangolo che nere l'area e lo contrassegna come "Rifatto".

Ecco un esempio di file redacted per la conversazione in thread tra utenti.

> [!div class="mx-imgBorder"]
> ![Screenshot del file redacted](media/RedactedFileExample.png)

Nella parte inferiore della scheda **Visualizzazione annotazioni** è visualizzato il **pulsante** Contrassegna documenti, che visualizza il riquadro di aggiunta di tag. All'interno di questo riquadro è possibile applicare un tag a tutti i messaggi all'interno della conversazione di Teams. È possibile etichettare una conversazione come reattiva o non reattiva, privilegiata o non privilegiata, se contiene "Elementi interessanti", se deve essere inclusa nell'esportazione e se deve essere ulteriormente esaminata. È anche possibile gestire e applicare altri tag personalizzabili.

#### <a name="action-menu"></a>Menu Azioni

All'interno della finestra dei set di revisioni è possibile esportare il contenuto facendo clic **su Azione** \> **esporta.** Durante l'esportazione sono disponibili molte opzioni.

Per esportare un file che contiene tutti i metadati per tutti i messaggi di Teams, fare clic per selezionare la **casella di controllo Carica file.** Per includere nel file tutti i tag applicati al contenuto, fare clic per selezionare la casella **di controllo** Contrassegni.

Usare **l'opzione File** nativi per esportare i file nel formato nativo. È possibile scegliere di esportare una conversazione come un unico file o tutti i singoli messaggi di chat nei propri file separati.

**L'opzione File** di testo consente di salvare versioni di contenuto in testo normale. Per altre informazioni su come ottenere una visualizzazione in testo normale delle conversazioni di Teams nel set di revisioni, vedere visualizzazione Riepilogo, visualizzazione testo e [visualizzazione annotazioni riportata sopra.](#summary-view-text-view-and-annotate-view)

Se sono state applicate modifiche al contenuto come descritto nella sezione [Riepilogo,](#summary-view-text-view-and-annotate-view) visualizzazione testo e  visualizzazione annotazioni precedente, è possibile selezionare l'opzione Sostituisci i nativi con PDF convertiti per sostituire i file nativi con copie convertite in PDF.

È possibile scegliere di esportare in un contenitore di archiviazione BLOB di Azure fornito da Microsoft oppure fornire un contenitore di archiviazione BLOB di Azure personalizzato.

Quando si è pronti per iniziare il processo di esportazione, fare clic **sul pulsante** Esporta. Vedere [Scaricare i processi di esportazione](/microsoft-365/compliance/download-export-jobs) per altre informazioni su come accedere al contenitore di archiviazione BLOB di Azure e scaricare il contenuto esportato al termine dell'esportazione.

> [!NOTE]
> L'esportazione può richiedere un periodo di tempo prolungato. Per tenere traccia dello stato del processo di esportazione, chiudere la scheda **Set di** revisioni e fare clic sulla **scheda** Esportazioni.

## <a name="related-topics"></a>Argomenti correlati

- [eDiscovery in Microsoft 365](/microsoft-365/compliance/ediscovery)
- [Panoramica di Teams PowerShell](teams-powershell-overview.md)