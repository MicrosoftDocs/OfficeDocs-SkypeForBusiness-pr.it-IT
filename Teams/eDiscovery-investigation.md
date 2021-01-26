---
title: Eseguire un'analisi eDiscovery del contenuto
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
description: Informazioni su cosa fare quando è necessario eseguire eDiscovery, ad esempio quando è necessario inviare tutti i dati archiviati elettronicamente per il procedimento legale.
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
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Eseguire un'analisi eDiscovery del contenuto in Microsoft Teams

Le grandi imprese sono spesso esposte a procedimenti legali di pena elevata che richiedono l'invio di tutte le informazioni archiviate elettronicamente (ESI). Il contenuto di Microsoft teams può essere cercato e usato durante le indagini eDiscovery.

## <a name="overview"></a>Panoramica

Tutti i Microsoft teams 1:1 o chat di gruppo vengono inseriti nelle cassette postali degli utenti rispettivi. Tutti i messaggi di canale standard vengono inseriti nella cassetta postale del gruppo che rappresenta il team. I file caricati nei canali standard sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for business.

eDiscovery di messaggi e file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [eDiscovery di canali privati](#ediscovery-of-private-channels).

Non tutto il contenuto del team è eDiscoverable. Nella tabella seguente sono illustrati i tipi di contenuto che è possibile cercare usando gli strumenti di Microsoft eDiscovery:

| Tipo di contenuto | eDiscoverable | Note |
|:--- | :--- |:--- |
|Registrazioni audio | No | |
|Contenuto della scheda|Sì|Per altre informazioni, vedere [cercare il contenuto della scheda](#search-for-card-content) .|
|Collegamenti alle chat | Sì | |
|Messaggi di chat | Sì |Questo include il contenuto nei canali teams, le chat di 1:1, 1: N chat di gruppo e chat con i partecipanti agli utenti guest.  |
|Frammenti di codice | No | |
|Messaggi modificati | Sì | Se l'utente è in attesa, vengono mantenute anche versioni precedenti dei messaggi modificati. |
|Emoji, gif e adesivi | Sì | |
|Immagini in linea | Sì | |
|Conversazioni ISTANTANEe della riunione | Sì | |
|Metadati della riunione<sup>1</sup> | Sì |  |
|Nome del canale | No | |
|Messaggi di canale privato | Sì | |
|Citazioni | Sì | Il contenuto tra virgolette è ricercabile. Tuttavia, i risultati della ricerca non indicano che il contenuto è stato citato. |
|Reazioni (ad esempio simili, cuori e altre reazioni) | No | |
|Oggetto | Sì | |
|Tabelle | Sì | |
|||

<sup>1</sup> i metadati di una riunione (e di una chiamata) includono i seguenti:

- Ora di inizio e fine della riunione e durata
- Partecipare a riunioni e uscire dagli eventi per ogni partecipante
- Join/chiamate VOIP
- Join anonimo
- Join degli utenti federati
- Join utente Guest

  L'immagine mostra un esempio di metadati della riunione.

  > [!div class="mx-imgBorder"]
  > ![L'immagine è dei metadati della riunione di CVR Records.](media/conversationOption3.png)

Ecco un esempio di conversazione di messaggistica istantanea tra partecipanti durante la riunione.

![Conversazione tra partecipanti in teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversazione tra partecipanti nei risultati della ricerca di eDiscovery.](media/MeetingImConversation2.png)

Per altre informazioni su come eseguire un'analisi di eDiscovery, vedere [Introduzione a core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery).

I dati di Microsoft teams verranno visualizzati come messaggi istantanei o conversazioni nell'output di esportazione di Excel eDiscovery. È possibile aprire il `.pst` file in Outlook per visualizzare i messaggi dopo l'esportazione.

Quando si Visualizza il file PST per il team, tutte le conversazioni vengono mantenute nella cartella chat del team in Cronologia conversazioni. Il titolo del messaggio contiene il nome del team e il nome del canale. Ad esempio, l'immagine seguente mostra un messaggio di Roberto che ha inviato un messaggio al canale standard di Project 7 del team di specifiche di manufacturing.

![Screenshot di una cartella della chat del team nella cassetta postale di un utente in Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Le chat private nella cassetta postale di un utente sono archiviate nella cartella chat del team in Cronologia conversazioni.

## <a name="ediscovery-of-private-channels"></a>eDiscovery dei canali privati

I record per i messaggi inviati in un canale privato vengono recapitati nella cassetta postale di tutti i membri del canale privato, anziché in una cassetta postale di gruppo. I titoli dei record vengono formattati in modo da indicare da quale canale privato sono stati inviati.

Poiché ogni canale privato ha un proprio sito di SharePoint separato dal sito del team padre, i file in un canale privato vengono gestiti indipendentemente dal team padre.

Teams non supporta la ricerca eDiscovery di un singolo canale all'interno di un team, quindi è necessario cercare tutto il team. Per eseguire una ricerca eDiscovery del contenuto in un canale privato, cercare in tutto il team, la raccolta siti associata al canale privato (per includere i file) e le cassette postali dei membri del canale privato (per includere i messaggi).

Seguire i passaggi seguenti per identificare i file e i messaggi in un canale privato da includere nella ricerca di eDiscovery.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Includere file di canale privato in una ricerca eDiscovery

Prima di eseguire questa procedura, installare [SharePoint Online Management Shell e connettersi a SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Eseguire la procedura seguente per ottenere un elenco di tutte le raccolte siti di SharePoint associate a canali privati nel team.

    ```PowerShell
    Get-SPOSite
    ```

2. Eseguire lo script di PowerShell seguente per ottenere un elenco di tutti gli URL della raccolta siti di SharePoint associati a canali privati nel team e nell'ID del gruppo del team padre.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Per ogni ID team o gruppo, Esegui lo script di PowerShell seguente per identificare tutti i siti di canale privati rilevanti, dove $groupID è l'ID del gruppo del team.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Includere messaggi di canale privato in una ricerca eDiscovery

Prima di eseguire questa procedura, verificare di avere installato la [versione più recente del modulo di PowerShell teams](teams-powershell-overview.md) .

1. Eseguire il comando seguente per ottenere un elenco di canali privati nel team.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Eseguire il comando seguente per ottenere un elenco dei membri del canale privato.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Includere le cassette postali di tutti i membri di ogni canale privato del team come parte della [query di ricerca di eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery).

## <a name="search-for-content-for-guest-users"></a>Cercare contenuto per gli utenti Guest

Puoi usare gli strumenti di eDiscovery per cercare il contenuto dei team correlati agli utenti Guest dell'organizzazione. Il contenuto della chat in Team associato a un utente guest viene mantenuto in una posizione di archiviazione basata sul cloud e può essere cercato usando eDiscovery. Questo include la ricerca di contenuto in 1:1 e 1: N conversazioni di chat in cui un utente Guest è un partecipante con altri utenti dell'organizzazione. È anche possibile cercare messaggi di canale privato in cui un utente Guest è partecipante e cercare contenuto in *Guest:* conversazioni chat Guest in cui gli unici partecipanti sono utenti guest.

Per cercare contenuto per gli utenti Guest:

1. Connettersi ad Azure AD PowerShell. Per istruzioni, vedere la sezione "connettersi con Azure Active Directory PowerShell" in [connettersi a Microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Assicurarsi di completare il passaggio 1 e il passaggio 2 nell'argomento precedente.

2. Dopo avere eseguito correttamente la connessione a Azure AD PowerShell, eseguire il comando seguente per visualizzare il nome dell'entità utente (UPN) per tutti gli utenti Guest dell'organizzazione. Quando si crea la ricerca nel passaggio 4, è necessario usare l'UPN dell'utente Guest.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Invece di visualizzare un elenco di nomi di entità utente nello schermo del computer, è possibile reindirizzare l'output del comando a un file di testo. Puoi eseguire questa operazione aggiungendo `> filename.txt` il comando precedente. Il file di testo con i nomi dell'entità utente verrà salvato nella cartella corrente.

3. In una finestra di Windows PowerShell diversa connettersi alla sicurezza & PowerShell Center di conformità. Per istruzioni, vedere [connettersi alla pagina Security & PowerShell Center Compliance](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell). È possibile connettersi con o senza usare l'autenticazione a più fattori.

4. Creare una ricerca di contenuto per cercare tutto il contenuto, ad esempio i messaggi di chat e i messaggi di posta elettronica, in cui l'utente Guest specificato è stato partecipante eseguendo il comando seguente.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Ad esempio, per cercare contenuto associato all'utente Guest Sara Davis, eseguire il comando seguente.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Per altre informazioni sull'uso di PowerShell per creare ricerche di contenuto, vedere [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch).

5. Eseguire il comando seguente per avviare la ricerca di contenuto creata al passaggio 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Passa a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fai clic su **Mostra tutte le**  >  **ricerche di contenuto**.

7. Nell'elenco delle ricerche selezionare la ricerca creata nel passaggio 4 per visualizzare la pagina del riquadro a comparsa.

8. Nella pagina a comparsa è possibile eseguire le operazioni seguenti:

   - Fare clic su **Visualizza risultati** per visualizzare i risultati della ricerca e visualizzare in anteprima il contenuto.

   - Accanto al campo della **query** , fare clic su **modifica** per modificare e quindi eseguire di nuovo la ricerca. Ad esempio, è possibile aggiungere una query di ricerca per restringere i risultati.

   - Fare clic su **Esporta risultati** per esportare e scaricare i risultati della ricerca.

## <a name="search-for-card-content"></a>Cercare il contenuto della scheda

Il contenuto della scheda generato dalle app nei canali di Team, nelle chat di 1:1 e nelle chat di 1xN è archiviato nelle cassette postali e può essere cercato. Una *scheda* è un contenitore dell'interfaccia utente per brevi frammenti di contenuto. Le schede possono avere più proprietà e allegati e possono includere pulsanti che possono attivare le azioni della scheda. Per altre informazioni, Vedi [schede](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Come il contenuto di altri team, in cui è archiviato il contenuto della scheda si basa sulla posizione in cui è stata usata la scheda. Il contenuto delle schede usate in un canale di teams è archiviato nella cassetta postale del gruppo teams. I contenuti delle schede per le chat di 1:1 e 1xN sono archiviati nelle cassette postali dei partecipanti alla chat.

Per cercare il contenuto della scheda, è possibile usare `kind:microsoftteams` le `itemclass:IPM.SkypeTeams.Message` condizioni di ricerca. Quando si rivedeno i risultati della ricerca, il contenuto della scheda generato da bot in un canale di Teams ha la proprietà **mittente/autore** della posta elettronica come `<appname>@teams.microsoft.com` , dove `appname` è il nome dell'app che ha generato il contenuto della scheda. Se il contenuto della scheda è stato generato da un utente, il valore di **sender/Author** identifica l'utente.

Quando si Visualizza il contenuto della scheda nei risultati della ricerca contenuto, il contenuto viene visualizzato come allegato al messaggio. L'allegato è denominato `appname.html` , dove `appname` è il nome dell'app che ha generato il contenuto della scheda. Gli screenshot seguenti mostrano il modo in cui il contenuto della scheda (per un'app denominata asana) viene visualizzato in teams e nei risultati di una ricerca.

**Contenuto della scheda in teams**

![Contenuto della scheda nel messaggio del canale Teams](media/CardContentTeams.png)

**Contenuto della scheda nei risultati della ricerca**
  
![Stesso contenuto della scheda nei risultati di una ricerca contenuto](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Per visualizzare le immagini dal contenuto della scheda nei risultati della ricerca in questo momento, ad esempio i segni di spunta nello screenshot precedente, è necessario essere connessi a teams (in https://teams.microsoft.com) una scheda diversa della stessa sessione del browser che si usa per visualizzare i risultati della ricerca. In caso contrario, verranno visualizzati i segnaposto di immagine.

## <a name="advanced-ediscovery"></a>EDiscovery avanzato

Alcuni contenuti di Microsoft teams possono essere cercati e conservati anche usando il [flusso di lavoro Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20). Mentre eDiscovery offre una gamma di funzionalità di ricerca, attesa ed esportazione, Advanced eDiscovery offre agli amministratori della conformità altri strumenti per identificare le origini dati e analizzarne il contenuto.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Flusso di lavoro custode avanzato di eDiscovery per il contenuto Teams

I custodi possono essere membri di vari team. È possibile acquisire il contenuto di teams rilevante per questi custodi. Per istruzioni sul flusso di lavoro della banca depositaria, vedere [aggiungere i custodi a un caso di eDiscovery avanzato](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).

Dopo aver aggiunto un custode, fare clic sul pulsante **Avanti** e quindi sul pulsante **Aggiungi** . Verrà visualizzata una finestra in cui viene chiesto di selezionare altre posizioni, in cui verranno visualizzate tutte le appartenenze del custode e le rispettive posizioni del sito di SharePoint per i relativi dati. Da tutte queste origini dati e teams, è possibile scegliere il contenuto che si vuole usare per eDiscovery, quindi inserire l'utente e tutte le origini dati identificate in attesa.

Puoi scegliere se includere il contenuto di Exchange, il contenuto di OneDrive o entrambi. Il contenuto di Exchange include tutto il contenuto dell'applicazione nelle cassette postali dell'utente, ad esempio i messaggi di posta elettronica, il contenuto dei team archiviati nella cassetta postale e così via. Il contenuto di OneDrive include non solo il contenuto dell'utente, ma anche tutti i contenuti del team archiviati in OneDrive, ad esempio le chat di 1:1, le chat 1: N e i file condivisi nelle chat.

Hai anche la possibilità di associare qualsiasi team a cui è associato il custode, in modo che siano inclusi i messaggi e i file di chat del canale a cui il custode ha accesso. Inoltre, qualsiasi altro team può essere associato a un custode.

> [!NOTE]
> eDiscovery di messaggi e file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [eDiscovery di canali privati](#ediscovery-of-private-channels).

### <a name="placing-a-data-source-on-hold"></a>Inserimento di un'origine dati in blocco

Se non è presente un utente specifico da designare come custode, è possibile inserire un'intera origine dati in attesa. Per altre informazioni su holds, vedere [gestire le esenzioni in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).

Quando si crea un blocco per il contenuto del team, è possibile scegliere tutte le posizioni che si desidera includere nel blocco. Anche se gli utenti stanno eliminando o modificando il contenuto, il blocco manterrà copie di tutte le versioni precedenti del contenuto.

È anche possibile usare una query facoltativa per impostare le condizioni per il blocco in base a parole chiave, intervallo di date, autore e molti altri criteri. Se non si specificano parole chiave, tutto il contenuto dell'origine dati sarà soggetto al blocco.

### <a name="advanced-ediscovery-searches"></a>Ricerche eDiscovery avanzate

È anche possibile cercare il contenuto teams. Per altre informazioni sulle ricerche, vedere [raccolta di dati per un caso in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery). Una ricerca restituirà un'intera conversazione se anche un messaggio corrisponde alla query di ricerca.

Quando si crea una query di ricerca, è possibile scegliere custodi in modo che tutte le fonti già selezionate vengano ricercate. È anche possibile cercare fonti non detentive, ad esempio un sito di teams non mappato a un utente. Le query facoltative sono disponibili anche per restringere la ricerca all'interno del contenuto teams.

Dopo aver creato una ricerca e averla selezionata, viene visualizzata una finestra con ulteriori dettagli e azioni che è possibile eseguire nella ricerca selezionata. Se si fa clic sul pulsante **statistiche** , è possibile visualizzare le statistiche relative alla ricerca, incluse le disaggregazioni in base ai tipi di posizione, l'origine originale per il contenuto e se il contenuto si trova in una cassetta postale del gruppo, nella singola cassetta postale dell'utente o in un sito di SharePoint. In questo modo, puoi vedere una ripartizione delle fonti che contribuiscono ai risultati della ricerca. È disponibile anche una visualizzazione **query** , in modo da poter vedere quali singole parole chiave contribuiscono ai risultati.

Dopo aver completato la ricerca, è possibile fare clic sul pulsante **Add results to Review set** e aggiungerlo a un set di recensioni. Per altre informazioni sui set di revisione, vedere [gestire i set di revisione in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) e [set di revisione del flusso di lavoro](#review-sets-workflow) più avanti in questo articolo.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Set di revisione normale e set di revisione delle conversazioni

Quando si aggiunge una ricerca a un set di revisione, è possibile scegliere da un set di revisione normale o da un set di revisione della conversazione.

Un set di revisione normale è simile a un'esportazione; fornisce i singoli `.msg` file per il contenuto del team e presenta il contenuto in una visualizzazione di base. In genere si usa un normale set di revisione quando si prevede di usare altri strumenti software per rielaborare i file in un secondo momento.

Un set di revisione della conversazione offre una visualizzazione più intuitiva e con thread delle conversazioni; Visualizza insieme i messaggi correlati nell'ordine corretto.

> [!div class="mx-imgBorder"]
> ![Screenshot del set di recensioni di conversazioni](media/conversationOptions2.png)

Funzionalità come la redazione è disponibile in entrambi i tipi di set di revisione. Per altre informazioni sui set di revisione, vedere [rivedere le conversazioni in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets).

#### <a name="collection-options"></a>Opzioni di raccolta

Quando si aggiunge un set di revisione, sono disponibili diverse opzioni come caselle di controllo nella sezione **Opzioni raccolta** della finestra, incluse le **Opzioni di recupero** delle conversazioni e le **conversazioni di Team**. Se si abilitano queste opzioni, verranno visualizzati anche i singoli messaggi di team che fanno parte del set di revisione con i messaggi aggiuntivi che li circondano per il contesto. Ad esempio, se la query è specifica e viene restituito un solo messaggio, l'abilitazione di queste opzioni restituirà anche diversi messaggi che conducono al messaggio che corrisponde alla query.

Molti criteri logici vengono usati per determinare se i messaggi aggiuntivi conferiscono un contesto ai messaggi che corrispondono alla query. Ad esempio, per il contenuto teams, l'abilitazione di queste opzioni recupererà il messaggio padre e tutti i messaggi figlio a causa del modo in cui i messaggi vengono filettati.

Vengono selezionati anche i timestamp del messaggio. Se un messaggio corrisponde alla query, i messaggi adiacenti che lo precedono entro un intervallo di 4 ore o che lo seguono entro un intervallo di 4 ore sono considerati parte della conversazione e sono inclusi anche nei risultati.

Se è necessario essere certi di quali messaggi contestuali verranno restituiti con le corrispondenze alla query di ricerca, non è necessario usare queste opzioni. Puoi raccogliere tutto il contenuto oppure allargare l'intervallo di date della ricerca in modo che vengano restituiti più messaggi come risultato della query.

### <a name="review-sets-workflow"></a>Verifica set di flussi di lavoro

È possibile visualizzare i set di revisione esistenti o crearne di nuovi facendo clic sulla scheda **set di revisione** . Per altre informazioni sui set di revisione, vedere [gestire i set di revisione in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).

Oltre ai documenti, è possibile aggiungere posta elettronica, messaggi di Team, messaggi di Yammer e altri contenuti al set di recensioni. All'interno di un set di revisione è anche possibile eseguire molte delle stesse operazioni che è possibile eseguire in altri contesti, ad esempio la ricerca di contenuto e la creazione di query personalizzate. Queste operazioni si applicano solo agli elementi che sono stati aggiunti al set di revisione.

Il pulsante **Gestisci set di revisione** offre opzioni aggiuntive, ad esempio analisi, report di riepilogo, numero di set di carichi aggiunti e così via.

Per accedere a visualizzazioni e grafici dei dati, fare clic  su \> **visualizzazione profilo di ricerca** singoli risultati nell'angolo in alto a destra. È possibile fare clic su cunei in questi grafici per selezionare in modo interattivo il tipo di contenuto che si vuole eseguire. Ad esempio, puoi scegliere di eseguire query solo sul contenuto di teams. È anche possibile salvare queste query come si salvano le query scritte manualmente.

#### <a name="summary-view-text-view-and-annotate-view"></a>Visualizzazione Riepilogo, visualizzazione testo e visualizzazione annotazioni

Se si fa clic su una conversazione in teams nel set di revisione, viene visualizzata la **visualizzazione Riepilogo**, che visualizza un'intera conversazione teams come elenco dei messaggi con cui è possibile interagire singolarmente. Fare clic sulla freccia rivolta verso il basso a destra di un messaggio per visualizzare un menu di scelta rapida che consente di visualizzare i dettagli del messaggio o scaricare il singolo `.msg` file. Se si fa clic su Dettagli messaggio, verrà visualizzato un riepilogo dei metadati o i metadati completi del messaggio.

Per scaricare un PDF, fare clic sul pulsante Scarica nell'angolo in alto a destra della visualizzazione riepilogo.

Fare clic sulla scheda **visualizzazione testo** per visualizzare una visualizzazione in testo normale del testo estratto della conversazione teams. Questo contenuto di testo normale è adatto per l'esportazione e può essere usato facilmente con altri strumenti software.

Fare clic sulla scheda **Visualizza** annotazioni per accedere alle caratteristiche di annotazione. Questa scheda Visualizza il contenuto in un formato simile a una conversazione in teams, ma sono disponibili anche altre opzioni per la modifica. È disponibile uno strumento matita che consente di creare note, disegnare sul messaggio o eseguire graffiature a grana fine per scopi di redazione. Esiste anche uno strumento di **redazione di area** che puoi usare per disegnare un rettangolo che oscura l'area e lo contrassegna come "redatto".

Ecco un esempio di file redatto per la conversazione in thread tra gli utenti.

> [!div class="mx-imgBorder"]
> ![Screenshot del file redatto](media/RedactedFileExample.png)

Nella parte inferiore della scheda **Visualizzazione annotazioni** si trova il pulsante **tag Documents** , che Visualizza il pannello di tagging. All'interno di questo pannello puoi applicare un contrassegno a tutti i messaggi all'interno della conversazione teams. È possibile contrassegnare una conversazione come reattiva o non rispondente, privilegiata o non privilegiata, se contiene "elementi interessanti", se deve essere inclusa nell'esportazione e se deve essere ulteriormente riesaminata. È anche possibile gestire e applicare altri tag personalizzabili.

#### <a name="action-menu"></a>Menu azione

All'interno della finestra Revisione set è possibile esportare il contenuto facendo clic  su \> **Esporta** azione. Durante l'esportazione sono disponibili molte opzioni.

Per esportare un file contenente tutti i metadati per tutti i messaggi di teams, fare clic su per selezionare la casella di controllo **Carica file** . Per includere nel file i tag applicati al contenuto, fare clic su per selezionare la casella di controllo **Contrassegni** .

Usare l'opzione **file nativi** per esportare i file nel formato nativo. È possibile scegliere di esportare una conversazione come file o in tutti i singoli messaggi di chat nei propri file separati.

L'opzione **file di testo** consente di salvare le versioni in testo normale del contenuto. Per altre informazioni su come ottenere una visualizzazione in testo normale delle conversazioni dei team nel set di recensioni, vedere visualizzazione [Riepilogo, visualizzazione testo e visualizzazione annotazioni](#summary-view-text-view-and-annotate-view) sopra.

Se sono state applicate redazioni al contenuto, come descritto nella sezione visualizzazione [Riepilogo, visualizzazione testo e annotazione](#summary-view-text-view-and-annotate-view) , è possibile selezionare l'opzione **Sostituisci nativi ritirati con file PDF convertiti** per sostituire i file nativi con copie convertite in formato PDF.

Puoi scegliere di esportare in un contenitore di archiviazione BLOB di Azure fornito da Microsoft oppure puoi fornire un contenitore di archiviazione di Azure BLOB personalizzato.

Quando si è pronti per iniziare il processo di esportazione, fare clic sul pulsante **Esporta** . Vedere [scaricare i processi di esportazione](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) per altre informazioni su come accedere al contenitore di archiviazione di Azure BLOB e scaricare il contenuto esportato al termine dell'esportazione.

> [!NOTE]
> L'esportazione può richiedere un periodo di tempo prolungato. Per tenere traccia dello stato del processo di esportazione, chiudere la scheda **set di revisione** e fare clic sulla scheda **Esporta** .

## <a name="related-topics"></a>Argomenti correlati

- [eDiscovery in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Panoramica di PowerShell Teams](teams-powershell-overview.md)
