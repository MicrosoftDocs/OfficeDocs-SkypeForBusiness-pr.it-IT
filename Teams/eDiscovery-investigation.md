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
ms.openlocfilehash: 85124047c5bb894eb4eb4177fad0e0cfee53dfc3
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711770"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Condurre un'indagine di eDiscovery sul contenuto in Microsoft Teams

Le grandi imprese sono spesso esposte a procedimenti legali ad alta sanzione che richiedono l'invio di tutte le informazioni archiviate elettronicamente (ESI). Microsoft Teams contenuto può essere cercato e usato durante le indagini di eDiscovery.

## <a name="overview"></a>Panoramica

Tutte Microsoft Teams chat 1:1 o di gruppo vengono visualizzate nel diario nelle cassette postali dei rispettivi utenti. Tutti i messaggi del canale standard vengono inviati nel journal alla cassetta postale del gruppo che rappresenta il team. I file caricati nei canali standard sono coperti dalla funzionalità eDiscovery per SharePoint Online e OneDrive for Business.

eDiscovery dei messaggi e dei file nei [canali privati](private-channels.md) funziona in modo diverso rispetto ai canali standard. Per altre informazioni, vedere [eDiscovery dei canali privati](#ediscovery-of-private-and-shared-channels).

Non tutto Teams contenuto è eDiscoverable. La tabella seguente mostra i tipi di contenuto che è possibile cercare usando gli strumenti di Microsoft eDiscovery:

| Tipo di contenuto | eDiscoverable | Note |
|:--- | :--- |:--- |
|Registrazioni audio | No | |
|Contenuto della scheda|Sì|Per [altre informazioni, vedere Cercare contenuto della](#search-for-card-content) scheda.|
|Collegamenti alla chat | Sì | |
|Messaggi di chat | Sì |Sono inclusi i contenuti nei canali Teams standard, le chat 1:1, le chat di gruppo 1:N e le chat con i partecipanti degli utenti guest.  |
|Frammenti di codice | No | |
|Messaggi modificati | Sì | Se l'utente è in attesa, vengono mantenute anche le versioni precedenti dei messaggi modificati. |
|Emoji, GIF e adesivi | Sì | |
|Notifiche del feed | No | |
|Immagini incorporate | Sì | |
|Componenti a ciclo continuo| Sì|Il contenuto di un componente di ciclo viene salvato in un file fluido archiviato nell'account OneDrive for Business dell'utente che invia il componente loop. Questo significa che è necessario includere OneDrive come origine dati durante la ricerca di contenuto nei componenti a ciclo continuo. |
|Conversazioni istantanee delle riunioni | Sì | |
|Metadati <sup>riunione1</sup> | Sì |  |
|Nome del canale | Sì | |
|Messaggi chat del canale privato e condiviso | Sì | |
|Virgolette | Sì | Il contenuto tra virgolette è disponibile per la ricerca. Tuttavia, i risultati della ricerca non indicano che il contenuto è stato citato. |
|Reazioni (ad esempio mi piace, cuori e altre reazioni) | No | |
|Oggetto | Sì | |
|Tabelle | Sì | |
||||

<sup>1 I</sup> metadati della riunione (e della chiamata) includono quanto segue:

- Ora di inizio e fine della riunione e durata
- Partecipare e uscire da una riunione per ogni partecipante
- Join/chiamate VOIP
- Join anonimi
- Join di utenti federati
- Partecipazione di utenti guest

Ecco un esempio di conversazione in chat tra partecipanti durante una riunione.

![Conversazione tra partecipanti in Teams.](media/MeetingIMConversations.png)

[!div class="mx-imgBorder"]

Ecco un esempio della copia di conformità della stessa conversazione di chat visualizzata in uno strumento di eDiscovery.

![Conversazione tra partecipanti nei risultati della ricerca eDiscovery.](media/MeetingImConversation2.png)

Ecco un esempio dei metadati della riunione.

  > [!div class="mx-imgBorder"]
  > ![Metadati della riunione dalla copia di conformità.](media/conversationOption3.png)

Per altre informazioni su come condurre un'indagine di eDiscovery, vedere Introduzione [a Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams i dati verranno visualizzati come messaggistica istantanea o Conversazioni nell'output Excel di esportazione di eDiscovery. È possibile aprire il `.pst` file in Outlook visualizzare i messaggi dopo averli esportati.

Quando si visualizza il file PST per il team, tutte le conversazioni si trovano nella cartella Chat del team in Cronologia conversazioni. Il titolo del messaggio contiene il nome del team e il nome del canale. Ad esempio, l'immagine seguente mostra un messaggio di Luca che ha inviato un messaggio al canale standard Project 7 del team Manufacturing Specs.

![Screenshot di una cartella di Team Chat nella cassetta postale di un utente in Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Le chat private nella cassetta postale di un utente vengono archiviate nella cartella Chat del team in Cronologia conversazioni.

## <a name="ediscovery-of-private-and-shared-channels"></a>eDiscovery di canali privati e condivisi

Le copie di conformità dei messaggi nei canali privati e condivisi vengono inviate a cassette postali diverse a seconda del tipo di canale. Questo significa che è necessario eseguire ricerche in posizioni diverse della cassetta postale in base al tipo di canale di cui un utente è membro.

- **Canali privati**. Le copie di conformità vengono inviate alla cassetta postale di tutti i membri dei membri del canale privato. Questo significa che è necessario eseguire una ricerca nella cassetta postale dell'utente durante la ricerca di contenuto nei messaggi del canale privato.

- **Canali condivisi**. Le copie di conformità vengono inviate a una cassetta postale di sistema associata al team padre. Poiché Teams non supporta una ricerca di eDiscovery in una singola cassetta postale di sistema per un canale condiviso, è necessario cercare nella cassetta postale il team padre (selezionando il nome della cassetta postale del team) durante la ricerca del contenuto dei messaggi nei canali condivisi.

Ogni canale privato e condiviso ha un sito SharePoint che è separato dal sito del team padre. Questo significa che i file nei canali privati e condivisi vengono archiviati nel proprio sito e gestiti in modo indipendente dal team padre. Questo significa che è necessario identificare ed eseguire ricerche nel sito specifico associato a un canale durante la ricerca di contenuto nei file e negli allegati dei messaggi del canale.

Usare le sezioni seguenti per identificare il canale privato o condiviso da includere nella ricerca eDiscovery.

### <a name="identifying-the-members-of-a-private-channel"></a>Identificazione dei membri di un canale privato

Usare la procedura descritta in questa sezione per identificare i membri di un canale privato in modo che sia possibile usare gli strumenti di eDiscovery per cercare il contenuto nei messaggi del canale privato nella cassetta postale del membro.

Prima di eseguire questa procedura, assicurarsi di avere installato l'ultima versione [del modulo di PowerShell Teams powershell](teams-powershell-overview.md).

1. Eseguire il comando seguente per ottenere l'ID gruppo del team che contiene i canali condivisi da cercare.

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > Eseguire il cmdlet **Get-Team** senza parametri per visualizzare un elenco di Teams all'interno dell'organizzazione. L'elenco contiene l'ID del gruppo e displayName per ogni team.

2. Eseguire il comando seguente per ottenere un elenco di canali privati nel team padre. Usare l'ID gruppo per il team ottenuto nel passaggio 1.

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. Eseguire il comando seguente per ottenere un elenco di proprietari e membri di canali privati per uno specifico canale privato.

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. Includere le cassette postali dei proprietari e dei membri di un canale privato come parte della query di ricerca [di eDiscovery in Core eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery) o quando si identifica e si raccoglie contenuto dei responsabili [in](/microsoft-365/compliance/add-custodians-to-case) Advanced eDiscovery.

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>Identificazione del sito SharePoint per canali privati e condivisi

Come spiegato in precedenza, i file condivisi in canali privati e condivisi (e i file allegati ai messaggi del canale) vengono archiviati nella raccolta siti associata al canale. Usare la procedura descritta in questa sezione per identificare l'URL del sito associato a uno specifico canale privato o condiviso. È quindi possibile usare gli strumenti di eDiscovery per cercare contenuto nel sito.

Prima di eseguire questa procedura, [installare SharePoint Online Management Shell e connettersi a SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Facoltativamente, eseguire quanto segue per ottenere un elenco di SharePoint raccolte siti associate ai canali condivisi nel team padre.

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > La convenzione di denominazione dell'URL per un sito associato a canali privati e condivisi è `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`. Ad esempio, l'URL del canale condiviso denominato "Collaborazione partner", che si trova nel team padre "Team tecnico" nell'organizzazione Contoso è `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`.

2. Eseguire i comandi di PowerShell seguenti per visualizzare l'URL di tutti i siti SharePoint associati ai canali privati e condivisi dell'organizzazione. L'output dello script include anche l'ID gruppo del team padre, che è necessario eseguire i comandi nel passaggio 3.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > SharePoint per i canali privati creati prima del 28 giugno 2021 usare il valore per `"TEAMCHANNEL#0"` l'ID modello personalizzato. Per visualizzare i canali privati creati dopo questa data, usare il valore `"TEAMCHANNEL#1"` quando si eseguono i due script precedenti. I canali condivisi usano solo il valore di `"TEAMCHANNEL#1"`.

3. Per ogni team padre, eseguire i comandi di PowerShell seguenti per identificare i siti dei canali privati e condivisi, dove `$groupID` è l'ID gruppo del team padre.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. Includere il sito associato a un canale privato o condiviso come parte della query di ricerca [di eDiscovery in Core eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery) o durante l'identificazione e la raccolta di contenuto di un responsabile [in Advanced eDiscovery](/microsoft-365/compliance/add-custodians-to-case).

## <a name="search-for-content-for-guest-users"></a>Cercare contenuto per gli utenti guest

È possibile usare gli strumenti di eDiscovery per cercare Teams contenuti correlati agli utenti guest dell'organizzazione. Teams contenuto della chat associato a un utente guest viene mantenuto in una posizione di archiviazione basata sul cloud e può essere cercato usando eDiscovery. Ciò include la ricerca di contenuto in conversazioni chat 1:1 e 1:N in cui un utente guest è un partecipante con altri utenti dell'organizzazione. È anche possibile cercare messaggi di canale privato in cui un utente guest è un partecipante e cercare contenuti nelle *conversazioni di chat guest:guest* in cui gli unici partecipanti sono utenti guest.

Per cercare contenuto per gli utenti guest:

1. Connessione per Azure AD PowerShell. Per istruzioni, vedere la sezione "Connessione con la Azure Active Directory PowerShell" in Connessione [per Microsoft 365 con PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Assicurarsi di completare i passaggi 1 e 2 nell'argomento precedente.

2. Dopo aver eseguito la connessione a Azure AD PowerShell, eseguire il comando seguente per visualizzare il nome dell'entità utente (UPN) per tutti gli utenti guest dell'organizzazione. È necessario usare l'UPN dell'utente guest quando si crea la ricerca nel passaggio 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Invece di visualizzare un elenco di nomi delle entità utente sullo schermo del computer, è possibile reindirizzare l'output del comando a un file di testo. A questo scopo, aggiungere al `> filename.txt` comando precedente. Il file di testo con i nomi delle entità utente verrà salvato nella cartella corrente.

3. In un'altra Windows PowerShell, connettersi a PowerShell del Centro sicurezza & conformità. Per istruzioni, vedere accedere [Connessione powershell del Centro sicurezza & conformità](/powershell/exchange/connect-to-scc-powershell). È possibile connettersi con o senza usare l'autenticazione a più fattori.

4. Creare una ricerca di contenuto che cerca tutto il contenuto, ad esempio i messaggi di chat e i messaggi di posta elettronica, in cui l'utente guest specificato era un partecipante eseguendo il comando seguente.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Ad esempio, per cercare il contenuto associato all'utente guest Sara Davis, eseguire il comando seguente.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Per altre informazioni sull'uso di PowerShell per creare ricerche contenuto, vedere [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Eseguire il comando seguente per avviare la ricerca di contenuto creata nel passaggio 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Passare a e [https://compliance.microsoft.com](https://compliance.microsoft.com) quindi fare clic **su Mostra tutta la** >  **ricerca contenuto**.

7. Nell'elenco delle ricerche selezionare la ricerca creata nel passaggio 4 per visualizzare la pagina a comparsa.

8. Nella pagina a comparsa è possibile eseguire le operazioni seguenti:

   - Fare **clic su Visualizza risultati** per visualizzare i risultati della ricerca e visualizzare in anteprima il contenuto.

   - Accanto al campo **Query** fare clic su **Modifica** per modificare ed eseguire di nuovo la ricerca. Ad esempio, è possibile aggiungere una query di ricerca per limitare i risultati.

   - Fare **clic su Esporta risultati** per esportare e scaricare i risultati della ricerca.

## <a name="search-for-card-content"></a>Cercare il contenuto della scheda

Il contenuto della scheda generato dalle app nei canali Teams, nelle chat 1:1 e nelle chat 1xN viene archiviato nelle cassette postali e può essere cercato. Una *scheda è* un contenitore dell'interfaccia utente per brevi parti di contenuto. Le schede possono avere più proprietà e allegati e possono includere pulsanti che possono attivare le azioni delle schede. Per altre informazioni, vedere [Schede](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Come altri Teams, in cui è archiviato il contenuto della scheda si basa sulla posizione in cui è stata usata la scheda. Il contenuto per le schede usate in un Teams canale viene archiviato nella cassetta postale Teams gruppo. Il contenuto della scheda per le chat 1:1 e 1xN viene archiviato nelle cassette postali dei partecipanti alla chat.

Per cercare il contenuto della scheda, è possibile usare le condizioni `kind:microsoftteams` di ricerca o `itemclass:IPM.SkypeTeams.Message` . Quando si esaminano i risultati della ricerca, il contenuto della scheda generato dai bot in un canale Teams ha la proprietà di posta elettronica Mittente **/**`<appname>@teams.microsoft.com`Autore come , `appname` dove è il nome dell'app che ha generato il contenuto della scheda. Se il contenuto della scheda è stato generato da un utente, il valore Mittente **/Autore** identifica l'utente.

Quando si visualizza il contenuto della scheda nei risultati della ricerca contenuto, il contenuto viene visualizzato come allegato al messaggio. L'allegato è denominato `appname.html`, dove `appname` è il nome dell'app che ha generato il contenuto della scheda. Gli screenshot seguenti mostrano come viene visualizzato il contenuto della scheda (per un'app denominata Asana) in Teams e nei risultati di una ricerca.

### <a name="card-content-in-teams"></a>Contenuto della scheda in Teams

![Contenuto della scheda nel Teams del canale.](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>Contenuto della scheda nei risultati della ricerca
  
![Stesso contenuto della scheda nei risultati di una ricerca contenuto.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Per visualizzare immagini dal contenuto della scheda nei risultati della ricerca in questo momento, ad esempio i segni di spunta nello screenshot precedente, è necessario accedere a Teams (https://teams.microsoft.com)in un'altra scheda nella stessa sessione del browser che si usa per visualizzare i risultati della ricerca. In caso contrario, vengono visualizzati i segnaposto immagine.

## <a name="related-topics"></a>Argomenti correlati

- [Microsoft 365 eDiscovery](/microsoft-365/compliance/ediscovery)
- [Introduzione a Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams flusso di lavoro in Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams panoramica di PowerShell](teams-powershell-overview.md)
