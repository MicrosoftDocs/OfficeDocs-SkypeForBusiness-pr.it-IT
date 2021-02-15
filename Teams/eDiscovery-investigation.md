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
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980460"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Condurre un'indagine eDiscovery sul contenuto in Microsoft Teams

Le grandi imprese vengono spesso esposte in procedimenti legali ad alta qualità che richiedono l'invio di tutte le informazioni archiviate elettronicamente. I contenuti di Microsoft Teams possono essere cercati e usati durante le indagini di eDiscovery.

## <a name="overview"></a>Panoramica

Tutte le chat di Microsoft Teams 1:1 o di gruppo vengono dismesse nelle cassette postali dei rispettivi utenti. Tutti i messaggi del canale standard vengono inviati alla cassetta postale del gruppo che rappresenta il team. I file caricati nei canali standard sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for Business.

La eDiscovery dei messaggi e dei file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [eDiscovery dei canali privati.](#ediscovery-of-private-channels)

Non tutti i contenuti di Teams sono eDiscoverable. La tabella seguente mostra i tipi di contenuto che è possibile cercare usando gli strumenti Microsoft eDiscovery:

| Tipo di contenuto | eDiscoverable | Note |
|:--- | :--- |:--- |
|Registrazioni audio | No | |
|Contenuto della scheda|Sì|Per [altre informazioni, vedere Cercare contenuto](#search-for-card-content) della scheda.|
|Collegamenti alla chat | Sì | |
|Messaggi in chat | Sì |Sono inclusi i contenuti nei canali di Teams, le chat 1:1, le chat di gruppo 1:N e le chat con i partecipanti degli utenti guest.  |
|Frammenti di codice | No | |
|Messaggi modificati | Sì | Se l'utente ha un blocco, vengono mantenute anche le versioni precedenti dei messaggi modificati. |
|Emoji, GIF e sticker | Sì | |
|Immagini incorporate | Sì | |
|Conversazioni istantanee delle riunioni | Sì | |
|Metadati riunione<sup>1</sup> | Sì |  |
|Nome del canale | No | |
|Messaggi di canale privato | Sì | |
|Offerte | Sì | Il contenuto tra virgolette è disponibile per la ricerca. Tuttavia, i risultati della ricerca non indicano che il contenuto è stato citato. |
|Reazioni (ad esempio Mi piace, cuori e altre reazioni) | No | |
|Oggetto | Sì | |
|Tabelle | Sì | |
|||

<sup>1</sup> I metadati della riunione (e della chiamata) includono quanto segue:

- Ora di inizio e fine della riunione e durata
- Partecipare a una riunione e lasciare gli eventi per ogni partecipante
- Partecipazione/chiamate VOIP
- Partecipazione anonima
- Aggiunta di utenti federati
- Partecipazione di utenti guest

  L'immagine mostra un esempio di metadati della riunione.

  > [!div class="mx-imgBorder"]
  > ![L'immagine è dei metadati delle riunioni dei record CVR.](media/conversationOption3.png)

Ecco un esempio di conversazione istantanea tra i partecipanti durante la riunione.

![Conversazione tra partecipanti in Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversazione tra partecipanti nei risultati di una ricerca eDiscovery.](media/MeetingImConversation2.png)

Per altre informazioni su come condurre un'indagine di eDiscovery, vedere [Introduzione a Core eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)

I dati di Microsoft Teams verranno visualizzati come messaggistica istantanea o conversazioni nell'output di esportazione di eDiscovery di Excel. È possibile aprire il `.pst` file in Outlook per visualizzare i messaggi dopo averli esportati.

Quando si visualizza il file PST per il team, tutte le conversazioni vengono mantenute nella cartella Chat del team in Cronologia conversazioni. Il titolo del messaggio contiene il nome del team e del canale. Ad esempio, l'immagine seguente mostra un messaggio di Bob che ha inviato un messaggio al canale standard di Project 7 del team di specifiche di produzione.

![Screenshot di una cartella Chat del team nella cassetta postale di un utente in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Le chat private nella cassetta postale di un utente vengono archiviate nella cartella Chat del team in Cronologia conversazioni.

## <a name="ediscovery-of-private-channels"></a>eDiscovery dei canali privati

I record per i messaggi inviati in un canale privato vengono recapitati nella cassetta postale di tutti i membri del canale privato, anziché in una cassetta postale di gruppo. I titoli dei record vengono formattati in modo da indicare da quale canale privato sono stati inviati.

Poiché ogni canale privato ha un proprio sito di SharePoint separato dal sito del team padre, i file in un canale privato vengono gestiti in modo indipendente dal team padre.

Teams non supporta la ricerca eDiscovery in un singolo canale all'interno di un team, quindi è necessario cercare l'intero team. Per eseguire una ricerca di eDiscovery nel contenuto di un canale privato, eseguire una ricerca all'interno del team, nella raccolta siti associata al canale privato (per includere file) e nelle cassette postali dei membri del canale privato (per includere i messaggi).

Usare la procedura seguente per identificare i file e i messaggi in un canale privato da includere nella ricerca eDiscovery.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Includere file di canali privati in una ricerca eDiscovery

Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti di SharePoint associate ai canali privati del team.

    ```PowerShell
    Get-SPOSite
    ```

2. Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati ai canali privati del team e all'ID del gruppo di team padre.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Per ogni ID team o gruppo, eseguire lo script di PowerShell seguente per identificare tutti i siti dei canali privati pertinenti, dove $groupID è l'ID gruppo del team.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Includere messaggi di canale privato in una ricerca eDiscovery

Prima di eseguire questa procedura, assicurarsi di avere installato [l'ultima versione del modulo Teams PowerShell.](teams-powershell-overview.md)

1. Eseguire il comando seguente per ottenere un elenco di canali privati nel team.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Eseguire il comando seguente per ottenere un elenco di membri di canali privati.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Includere le cassette postali di tutti i membri di ogni canale privato del team come parte della query di [ricerca eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Cercare contenuto per gli utenti guest

È possibile usare gli strumenti di eDiscovery per cercare contenuti di Teams relativi agli utenti guest nell'organizzazione. Il contenuto della chat di Teams associato a un utente guest viene mantenuto in una posizione di archiviazione basata sul cloud e può essere cercato con eDiscovery. È inclusa la ricerca di contenuti nelle conversazioni di chat 1:1 e 1:N in cui un utente guest è partecipante con altri utenti dell'organizzazione. È anche possibile cercare messaggi di canale privato in cui un utente guest è un partecipante e cercare contenuti in conversazioni di chat *guest:guest* in cui gli unici partecipanti sono utenti guest.

Per cercare contenuti per gli utenti guest:

1. Connettersi ad Azure AD PowerShell. Per istruzioni, vedere la sezione "Connettersi con Azure Active Directory PowerShell" in Connettersi [a Microsoft 365 con PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) Assicurarsi di completare i passaggi 1 e 2 dell'argomento precedente.

2. Dopo la connessione a PowerShell di Azure AD, eseguire il comando seguente per visualizzare il nome dell'entità utente (UPN) per tutti gli utenti guest nell'organizzazione. È necessario usare l'UPN dell'utente guest quando si crea la ricerca nel passaggio 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Invece di visualizzare un elenco di nomi dell'entità utente sullo schermo del computer, è possibile reindirizzare l'output del comando a un file di testo. A questo scopo, aggiungere `> filename.txt` al comando precedente. Il file di testo con i nomi dell'entità utente verrà salvato nella cartella corrente.

3. In una finestra di Windows PowerShell diversa connettersi a PowerShell del Centro & sicurezza. Per istruzioni, vedere [Connettersi a PowerShell & sicurezza.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) È possibile connettersi con o senza usare l'autenticazione a più fattori.

4. Creare una ricerca di contenuto che cerca tutto il contenuto (ad esempio messaggi di chat e messaggi di posta elettronica) in cui l'utente guest specificato era partecipante eseguendo il comando seguente.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Ad esempio, per cercare contenuto associato all'utente guest Sara Davis, eseguire il comando seguente.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Per altre informazioni sull'uso di PowerShell per creare ricerche di contenuto, vedere [New-ComplianceSearch.](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

5. Eseguire il comando seguente per avviare la ricerca contenuto creata nel passaggio 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e fare clic su Mostra tutta **la** ricerca  >  **di contenuto.**

7. Nell'elenco delle ricerche selezionare la ricerca creata nel passaggio 4 per visualizzare la pagina a comparsa.

8. Nel riquadro a comparsa è possibile eseguire le operazioni seguenti:

   - Fare **clic su Visualizza risultati** per visualizzare i risultati della ricerca e visualizzare in anteprima il contenuto.

   - Accanto al **campo Query** fare clic su **Modifica** per modificare e quindi eseguire di nuovo la ricerca. Ad esempio, è possibile aggiungere una query di ricerca per limitare i risultati.

   - Fare **clic su Esporta per** esportare e scaricare i risultati della ricerca.

## <a name="search-for-card-content"></a>Cercare il contenuto della scheda

I contenuti delle schede generati dalle app nei canali di Teams, le chat 1:1 e le chat 1xN vengono archiviati nelle cassette postali e possono essere cercati. Una *scheda è* un contenitore di interfaccia utente per brevi parti di contenuto. Le schede possono avere più proprietà e allegati e possono includere pulsanti che possono attivare azioni per le schede. Per altre informazioni, vedere [Schede](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Come per altri contenuti di Teams, la posizione in cui è archiviato il contenuto della scheda dipende dalla posizione in cui è stata usata la scheda. Il contenuto delle schede usate in un canale di Teams viene archiviato nella cassetta postale del gruppo Di Teams. Il contenuto della scheda per le chat 1:1 e 1xN viene archiviato nelle cassette postali dei partecipanti alla chat.

Per cercare il contenuto della scheda, è possibile usare le `kind:microsoftteams` condizioni `itemclass:IPM.SkypeTeams.Message` di ricerca. Quando si esaminano i risultati della ricerca, il contenuto della scheda generato dai bot in un canale di Teams ha la proprietà di posta elettronica **Mittente/Autore** come , dove è il nome dell'app che ha generato il contenuto `<appname>@teams.microsoft.com` `appname` della scheda. Se il contenuto della scheda è stato generato da un utente, il valore di **Mittente/Autore** identifica l'utente.

Quando si visualizza il contenuto della scheda nei risultati della ricerca contenuto, il contenuto viene visualizzato come allegato al messaggio. L'allegato viene `appname.html` denominato , dove è il nome `appname` dell'app che ha generato il contenuto della scheda. Gli screenshot seguenti mostrano come viene visualizzato il contenuto delle schede (per un'app denominata Asana) in Teams e nei risultati di una ricerca.

**Contenuto della scheda in Teams**

![Contenuto della scheda nel messaggio del canale di Teams](media/CardContentTeams.png)

**Contenuto della scheda nei risultati della ricerca**
  
![Stesso contenuto della scheda nei risultati di una ricerca di contenuto](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Per visualizzare immagini dal contenuto della scheda nei risultati di ricerca in questo momento (come i segni di spunta nella schermata precedente), è necessario essere connessi a Teams (in una scheda diversa nella stessa sessione del browser che si usa per visualizzare i risultati della https://teams.microsoft.com) ricerca. In caso contrario, vengono visualizzati i segnaposto per l'immagine.

## <a name="advanced-ediscovery"></a>Advanced eDiscovery

Alcuni contenuti di Microsoft Teams possono anche essere cercati e conservati usando il [flusso di lavoro Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) Anche se eDiscovery offre una gamma di funzionalità di ricerca, blocco ed esportazione, Advanced eDiscovery offre agli amministratori di conformità più strumenti per identificare le origini dati e analizzarne il contenuto.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Flusso di lavoro dei responsabile di Advanced eDiscovery per il contenuto di Teams

I responsabile possono essere membri di diversi team. È possibile acquisire contenuti di Teams rilevanti per questi responsabile. Per istruzioni sul flusso di lavoro dei responsabile, vedere [Aggiungere i responsabile a un caso di Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)

Dopo aver aggiunto un responsabile, fare clic **sul pulsante** Avanti e quindi **su** Aggiungi. Viene quindi visualizzata una finestra che chiede di selezionare altre posizioni, che mostrerà tutte le appartenenze dei responsabile e le posizioni dei siti di SharePoint corrispondenti per i relativi dati. Da tutte queste origini dati e team, è possibile scegliere il contenuto da usare per eDiscovery e quindi mettere l'utente in stato di blocco e tutte le origini dati identificate.

È possibile scegliere se includere il contenuto di Exchange, il contenuto di OneDrive o entrambi. Il contenuto di Exchange include tutto il contenuto dell'applicazione nelle cassette postali dell'utente, ad esempio la posta elettronica, il contenuto di Teams archiviato nella propria cassetta postale e così via. Il contenuto di OneDrive include non solo il contenuto dell'utente, ma anche tutti i contenuti di Teams archiviati in OneDrive, ad esempio chat 1:1, chat 1:N e file condivisi nelle chat.

È anche possibile associare qualsiasi team di cui fa parte il responsabile, in modo che i messaggi della chat del canale e i file a cui ha accesso il responsabile siano inclusi. Inoltre, qualsiasi altro team può essere associato a un responsabile.

> [!NOTE]
> La eDiscovery dei messaggi e dei file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [eDiscovery dei canali privati.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>Applicazione di un blocco a un'origine dati

Se non ci sono utenti specifici da designare come responsabile, è possibile mettere in stato di blocco un'intera origine dati. Per altre informazioni sui blocchi, vedere [Gestire i blocchi in Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)

Quando si crea un blocco per il contenuto di Teams, è possibile scegliere tutte le posizioni da includere nel blocco. Anche se gli utenti eliminano o modificano il contenuto, il blocco manterrà copie di tutte le versioni precedenti del contenuto.

È anche possibile usare una query facoltativa per impostare condizioni per il blocco in base a parole chiave, intervallo di date, autore e molti altri criteri. Se non si specificano parole chiave, tutti gli elementi dell'origine dati saranno soggetti al blocco.

### <a name="advanced-ediscovery-searches"></a>Ricerche di eDiscovery avanzate

È anche possibile eseguire ricerche nel contenuto di Teams. Per altre informazioni sulle ricerche, vedere Raccogliere dati [per un caso in Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery) Una ricerca restituirà un'intera conversazione se anche un messaggio corrisponde alla query di ricerca.

Quando si crea una query di ricerca, è possibile scegliere i responsabile in modo che la ricerca verrà eseguita in tutte le origini già selezionate. È anche possibile eseguire ricerche in origini non responsabile, ad esempio un sito di Teams non mappato a un utente. Sono inoltre disponibili query facoltative per restringere la ricerca all'interno del contenuto di Teams.

Dopo aver creato e selezionato una ricerca, viene visualizzata una finestra con dettagli e azioni aggiuntivi che è possibile eseguire sulla ricerca selezionata. Se si  fa clic sul pulsante Statistiche, è possibile visualizzare le statistiche sulla ricerca, incluse le suddivisioni in base al tipo di posizione, l'origine originale del contenuto e se il contenuto si trova in una cassetta postale del gruppo, nella cassetta postale del singolo utente o in un sito di SharePoint. È quindi possibile visualizzare un'analisi delle origini che contribuiscono ai risultati della ricerca. È disponibile anche una **visualizzazione** Query che consente di vedere quali singole parole chiave contribuiscono ai risultati.

Dopo aver finalizzato la ricerca, è possibile fare clic sul pulsante Aggiungi risultati per **rivedere** il set e aggiungerlo a un set di revisioni. Per altre informazioni sui set di revisioni, vedere Gestire i set di revisioni nel flusso di lavoro [Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) e [Set di](#review-sets-workflow) revisioni più avanti in questo articolo.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Set di revisioni normali e set di revisioni conversazioni

Quando si aggiunge una ricerca a un set di revisioni, è possibile scegliere da un set di revisioni normale o da un set di revisioni conversazione.

Un set di revisioni normale è simile a un'esportazione; fornisce i singoli `.msg` file per il contenuto di Teams e presenta il contenuto in una visualizzazione di base. In genere si usa un set di revisioni normale quando si prevede di usare altri strumenti software per rielaborare i file in un secondo momento.

Un set di revisioni conversazioni offre una visualizzazione delle conversazioni più intuitiva e in thread; i messaggi correlati vengono visualizzati nell'ordine corretto.

> [!div class="mx-imgBorder"]
> ![Screenshot del set di revisioni conversazioni](media/conversationOptions2.png)

Funzionalità come la rivistosi sono disponibili in entrambi i tipi di set di revisioni. Per altre informazioni sui set di revisioni, vedere [Esaminare le conversazioni in Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>Opzioni di raccolta

Quando si aggiunge a un set di revisioni,  sono disponibili diverse opzioni  come caselle di controllo nella sezione Opzioni raccolta della finestra, tra cui Opzioni di recupero conversazioni e **Conversazioni di Teams.** Se si abilitano queste opzioni, tutti i singoli messaggi di Teams che fanno parte del set di revisioni verranno visualizzati anche con altri messaggi circostanti per il contesto. Ad esempio, se la query è specifica e viene restituito un solo messaggio come risultato, l'abilitazione di queste opzioni restituisce anche diversi messaggi che portano e segue il messaggio corrispondente alla query.

Molti criteri logici vengono usati per determinare se altri messaggi forniscono contesto ai messaggi corrispondenti alla query. Ad esempio, per il contenuto di Teams, l'abilitazione di queste opzioni recupera il messaggio padre e tutti i messaggi figlio a causa del modo in cui i messaggi sono in thread.

Vengono controllati anche gli indicatori di data e ora dei messaggi. Se un messaggio corrisponde alla query, i messaggi adiacenti che lo precedono entro un intervallo di 4 ore o che lo seguono entro un intervallo di 4 ore sono considerati parte della conversazione e vengono inclusi anche nei risultati.

Se è necessario essere certi di quali messaggi contestuali verranno restituiti con corrispondenze alla query di ricerca, non è necessario usare queste opzioni. È possibile raccogliere tutto il contenuto oppure ampliare l'intervallo di date della ricerca in modo da restituire più messaggi come risultato della query.

### <a name="review-sets-workflow"></a>Flusso di lavoro Set di revisioni

È possibile visualizzare set di revisioni esistenti o crearne di nuovi facendo clic **sulla scheda Set di** revisioni. Per altre informazioni sui set di revisioni, vedere [Gestire i set di revisioni in Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)

Oltre ai documenti, è possibile aggiungere messaggi di posta elettronica, messaggi di Teams, messaggi di Yammer e altri contenuti al set di revisioni. All'interno di un set di revisioni è anche possibile eseguire molte delle stesse operazioni in altri contesti, ad esempio la ricerca di contenuto e la creazione di query personalizzate. Queste operazioni si applicano solo agli elementi aggiunti al set di revisioni.

Il **pulsante Gestisci set di** revisioni offre altre opzioni, ad esempio analisi, report di riepilogo, quanti set di caricamento sono stati aggiunti e così via.

Per accedere a visualizzazioni e grafici dei dati, fare clic su **Singoli risultati** nella visualizzazione Profilo di \> **ricerca** in alto a destra. È possibile fare clic sui cunei in questi grafici per selezionare in modo interattivo il tipo di contenuto in cui eseguire la query. Ad esempio, è possibile scegliere di eseguire query solo sul contenuto di Teams. È anche possibile salvare queste query così come si salvano le query che si scrivono manualmente.

#### <a name="summary-view-text-view-and-annotate-view"></a>Visualizzazione Riepilogo, visualizzazione testo e visualizzazione annotazioni

Se si fa clic su una conversazione di Teams nel set di revisioni, viene visualizzata la visualizzazione Riepilogo, che mostra un'intera conversazione di Teams come elenco di messaggi con cui è possibile interagire singolarmente. Fare clic sulla freccia rivolta verso il basso a destra di un messaggio per visualizzare un menu di scelta rapida che consente di visualizzare i dettagli del messaggio o scaricare il singolo `.msg` file. Facendo clic sui dettagli del messaggio verrà visualizzato un riepilogo dei metadati o dei metadati completi del messaggio.

Per scaricare un PDF, fare clic sul pulsante di download nell'angolo in alto a destra della visualizzazione di riepilogo.

Fare clic **sulla scheda della** visualizzazione Testo per visualizzare in testo normale il testo estratto della conversazione di Teams. Questo contenuto di testo normale è adatto per l'esportazione e può essere facilmente utilizzato con altri strumenti software.

Fare clic sulla scheda **Visualizzazione annotazioni per accedere** alle caratteristiche di annotazione. Questa scheda mostra il contenuto in un formato simile a una conversazione di Teams, ma sono disponibili anche altre opzioni per la modifica. È disponibile uno strumento matita che è possibile usare per creare note, disegnare sul messaggio o grattare via a grana fine ai fini della redazione. È anche disponibile uno strumento di ridisattivazione area che è possibile usare per disegnare un rettangolo che riattiva l'area e lo contrassegna come "Redacted". 

Ecco un esempio di file redacted per le conversazioni in thread tra gli utenti.

> [!div class="mx-imgBorder"]
> ![Screenshot di un file redacted](media/RedactedFileExample.png)

Nella parte inferiore della scheda **Visualizzazione annotazioni si** trova il **pulsante Contrassegna** per i documenti, che mostra il riquadro di tagging. All'interno di questo riquadro è possibile applicare un tag a tutti i messaggi all'interno della conversazione di Teams. È possibile etichettare una conversazione come reattiva o non reattiva, con privilegi o meno, indipendentemente dal fatto che contenga "Elementi interessanti", se deve essere inclusa nell'esportazione e se deve essere esaminata ulteriormente. È anche possibile gestire e applicare altri tag personalizzabili.

#### <a name="action-menu"></a>Menu Azione

Nella finestra dei set di revisioni è possibile esportare il contenuto facendo clic su **Esportazione** \> **azioni.** Sono disponibili molte opzioni per l'esportazione.

Per esportare un file che contiene tutti i metadati per tutti i messaggi di Teams, fare clic per selezionare la **casella di controllo Carica file.** Per includere nel file tutti i tag applicati al contenuto, fare clic per selezionare la **casella di** controllo Contrassegni.

Usare **l'opzione File** nativi per esportare i file nel formato nativo. È possibile scegliere di esportare una conversazione come un unico file o tutti i singoli messaggi di chat nei propri file separati.

**L'opzione File** di testo consente di salvare versioni di contenuto in testo normale. Per altre informazioni su come ottenere una visualizzazione in testo normale delle conversazioni di Teams nel set di revisioni, vedere la visualizzazione Riepilogo, la visualizzazione testo e la [visualizzazione di annotazione](#summary-view-text-view-and-annotate-view) riportata sopra.

Se sono state applicate riattivazioni al contenuto come descritto nella sezione precedente visualizzazione [Riepilogo,](#summary-view-text-view-and-annotate-view) visualizzazione testo e visualizzazione annotazioni, è possibile selezionare l'opzione Sostituisci i nativi con FILE PDF convertiti per sostituire i file nativi con copie convertite in PDF. 

È possibile scegliere di esportare in un contenitore di archiviazione BLOB Azure fornito da Microsoft oppure fornire il proprio contenitore di archiviazione BLOB azure.

Quando si è pronti per iniziare il processo di esportazione, fare clic sul **pulsante** Esporta. Vedere [Scaricare i processi di](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) esportazione per altre informazioni su come accedere al contenitore di archiviazione BLOB di Azure e scaricare il contenuto esportato al termine dell'esportazione.

> [!NOTE]
> L'esportazione può richiedere un periodo prolungato di tempo. Per tenere traccia dello stato del processo di esportazione, chiudere la scheda **Controlla** set e fare clic sulla **scheda** Esportazioni.

## <a name="related-topics"></a>Argomenti correlati

- [eDiscovery in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Panoramica di Teams su PowerShell](teams-powershell-overview.md)
