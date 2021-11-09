---
title: Configurare la gerarchia di destinazione del team
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: Informazioni su come configurare una gerarchia di team nell'organizzazione per pubblicare contenuto in un set di team di grandi dimensioni.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f65ffa8fa6dc661451669ded8f407bb519468112
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850549"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurare la gerarchia di destinazione del team

La configurazione di una gerarchia di targeting del team consentirà all'organizzazione di pubblicare contenuto in un set di team di grandi dimensioni. La gerarchia di destinazione del team definisce in che modo tutti i team della gerarchia sono correlati tra loro, quali utenti possono pubblicare attività e in quali team gli utenti hanno le autorizzazioni per la pubblicazione. Le caratteristiche di pubblicazione sono disabilitate per tutti gli utenti, a meno che non sia stata impostata una gerarchia di destinazione del team per l'organizzazione. Per configurare una gerarchia di destinazione del team, è necessario creare un file che definisce la gerarchia e quindi caricarlo in Teams per applicarla all'organizzazione. Dopo il caricamento dello schema, le app all'interno Teams possono usarlo.

> [!IMPORTANT]
> Per la versione iniziale, solo l'app Attività supporta i team gerarchici.  L'applicazione di una gerarchia di destinazione del team all'organizzazione consentirà [la pubblicazione delle attività](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) nell'app Attività. Non verrà visualizzata una gerarchia di team in altre aree di Microsoft Teams.

Ecco un esempio di come viene rappresentata la gerarchia nell'app Attività in Teams. Dopo aver creato un elenco attività, i membri del team di pubblicazione possono quindi selezionare i team dei destinatari a cui inviare (pubblicare) l'elenco attività. Quando si selezionano i team, il team di pubblicazione può filtrare in base alla gerarchia, in base agli attributi o a una combinazione di entrambi.<br>

![Screenshot della pubblicazione delle attività.](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>Terminologia

I termini seguenti saranno importanti durante l'esplorazione delle gerarchie. Teams verrà definito **nodi**.

* **I nodi radice** sono i nodi più in alto nella gerarchia. Nell'esempio, Retail Communications è un nodo radice.
* **I nodi padre** **e i nodi figlio** sono termini che rappresentano una relazione tra due nodi connessi. Nell'esempio, Distretto 01 è un nodo figlio dell'area 1.
* Più livelli di elementi figlio sono definiti **discendenti.** Distretto 01, Store 01, Store 03, Store 07, Distretto 02 e Distretto 03 sono tutti discendenti dell'Area 1.
* Un nodo senza elementi figlio è denominato **nodo foglia.** Si tratta della parte inferiore di una gerarchia.
* **I team dei** destinatari sono team selezionati per ricevere un set specifico di contenuti da pubblicare. Devono essere nodi foglia.

## <a name="plan-your-hierarchy"></a>Pianificare la gerarchia

Prima di creare lo schema che definisce la gerarchia, è necessario pianificare e decidere come modellare l'organizzazione.  Una delle prime priorità consiste nel decidere quali gruppi dell'organizzazione devono pubblicare le attività in altri gruppi. Ogni nodo della gerarchia rappresenta un gruppo di lavoro o un gruppo di gruppi.

### <a name="permissions-to-publish"></a>Autorizzazioni per la pubblicazione

L'autorizzazione per la pubblicazione dipende dal fatto che un utente sia membro di qualsiasi team nella gerarchia e dalla relazione di tale team o set di team con altri team della gerarchia.

> [!NOTE]
> Al proprietario di un team vengono concesse anche le autorizzazioni di pubblicazione.

* Se un utente è membro di almeno un team con discendenti nella gerarchia, può pubblicare in tali discendenti senza essere membro di tutti i team in cui vuole pubblicare.
* Se un utente è membro di almeno un team nella gerarchia ma non è membro di un team con discendenti nella gerarchia, può visualizzare e ricevere contenuto pubblicato dall'organizzazione.
* Se un utente non è un membro di un team nella gerarchia, l'utente non visualizza alcuna funzionalità correlata alla pubblicazione.

### <a name="guidelines"></a>Linee guida

* Per ogni organizzazione può essere applicato un solo file di gerarchia. È tuttavia possibile includere parti diverse dell'organizzazione come gerarchie distinte di nodi all'interno di un file. Ad esempio, Contoso Pharmaceuticals ha un nodo radice Farmacia e un nodo radice Di vendita al dettaglio. Entrambi i nodi radice hanno più righe di discendenti e non ci sono sovrapposizioni tra di essi.
* Solo i nodi foglia possono essere destinatari di una pubblicazione. Gli altri nodi della gerarchia sono utili per selezionare i destinatari di una pubblicazione.
* Un team può essere rappresentato una sola volta in una gerarchia.
* Una gerarchia può contenere fino a 15.000 nodi. Microsoft prevede di collaborare con i clienti per aumentare questo limite per le organizzazioni più grandi.

### <a name="example-hierarchy"></a>Gerarchia di esempio

Ad esempio, nella gerarchia seguente, richiamo, comunicazioni e risorse umane possono pubblicare attività in ogni nodo inferiore (team) della gerarchia, ma l'area nord-orientale può pubblicare le attività solo nei team di New York Store e Boston Store. La gerarchia di esempio consente ai gruppi Di richiamo, Comunicazioni e Risorse umane di pubblicare attività che si applicano all'intera società, ad esempio informazioni sui vantaggi o messaggi del CEO. L'area nord-orientale può pubblicare attività come la pianificazione del personale, le informazioni meteo e così via, solo ai team di New York Store e Boston Store.

![Esempio gerarchico del team.](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>Creare la gerarchia

> [!NOTE]
> Nella parte restante di questo articolo viene illustrata la configurazione di una gerarchia di team nel contesto della pubblicazione di attività nei team dei destinatari. Vedere Gestire [l'app Attività per l'organizzazione in Teams](./manage-tasks-app.md) per una panoramica dell'app Attività, in cui la pubblicazione delle attività viene visualizzata quando è abilitata.

Lo schema che definisce la gerarchia si basa su un file csv (comma-separated values). Il file deve essere in formato UTF-8. Ogni riga del file CSV corrisponde a un nodo all'interno della gerarchia dei team. Ogni riga contiene informazioni che nominano il nodo all'interno della gerarchia, facoltativamente lo collegano a un team e includono attributi che possono essere usati per filtrare i team nelle app che lo supportano.

È anche possibile definire **contenitori,** ovvero categorie che il team di pubblicazione può usare per organizzare il contenuto inviato ai team dei destinatari per semplificare la visualizzazione, l'ordinamento e l'attenzione sul contenuto pertinente.

### <a name="add-required-columns"></a>Aggiungere colonne obbligatorie

Il file CSV deve contenere le tre colonne seguenti, nell'ordine seguente, a partire dalla prima colonna. Un nodo deve essere collegato a un team per poter ricevere le attività.

| Nome colonna   | Obbligatorio | Descrizione   |
----------------|----------|---------------|
| DisplayName    | Sì      | Questo campo è il nome del nodo. Il nome può contenere fino a 100 caratteri e contenere solo i caratteri A-Z, a-z e 0-9. I nomi dei nodi devono essere univoci. |
| ParentName    | Sì       | Questo è il nome del nodo padre. Il valore specificato qui deve corrispondere esattamente al valore nel **campo DisplayName** del nodo padre. Se si vogliono aggiungere più nodi padre, separare ogni nome di nodo padre con un punto e virgola (;). È possibile aggiungere fino a 25 nodi padre e ogni nome di nodo padre può contenere fino a 2500 caratteri. Un nodo può avere più nodi padre solo se i nodi padre sono nodi radice.   <br><br>**IMPORTANTE** Prestare attenzione a non creare un ciclo in cui un elemento padre più in alto nella gerarchia fa riferimento a un nodo figlio più in basso nella gerarchia. Questa opzione non è supportata. |
| TeamId        | Sì, se il team pubblica attività o riceve attività da un nodo padre       | Contiene l'ID del team a cui si vuole collegare un nodo. Ogni nodo deve fare riferimento a un team univoco, quindi ogni valore di TeamId può essere visualizzato una sola volta nel file di gerarchia. Per ottenere l'ID di un team a cui si vuole collegare un nodo, eseguire il comando di PowerShell seguente: `Get-Team | Export-Csv TeamList.csv` . Questo comando elenca i team dell'organizzazione e include il nome e l'ID di ogni team. Trovare il nome del team a cui si vuole creare un collegamento e quindi copiare l'ID in questo campo.|

> [!NOTE]
> Se un nodo non è un nodo radice o un nodo foglia e non è necessaria l'appartenenza al team per concedere le autorizzazioni corrispondenti per la pubblicazione e la creazione di report, è possibile lasciare vuoto l'ID team. Questo metodo può essere usato per aggiungere maggiore granularità quando si scelgono i team dei destinatari o per visualizzare i report di completamento senza avere un team corrispondente.

### <a name="add-attribute-columns"></a>Aggiungere colonne di attributi

Dopo aver aggiunto le tre colonne obbligatorie, è possibile aggiungere colonne di attributi facoltative. Questi attributi possono essere usati per filtrare i nodi in modo da poter selezionare più facilmente quelli in cui si vogliono pubblicare le attività. Esistono due modi per definire gli attributi, a seconda che i valori di tale attributo si escludono a vicenda.

|Modi per aggiungere attributi|Descrizione |Esempio  |
|---|---------|---------|
|Se i valori di un attributo si escludono a vicenda, il nome della colonna specificato diventa il nome dell'attributo.|Ogni riga può contenere un valore per l'attributo e ogni colonna dell'attributo può contenere fino a 50 valori univoci. Ogni valore può contenere fino a 100 caratteri. Il set di valori di attributo specificato nella colonna dell'attributo verrà visualizzato come valori di filtro per tale attributo quando si selezionano i team dei destinatari usando la gerarchia di destinazione del team.|Si vuole consentire agli utenti di filtrare gli archivi in base al layout. I valori di questo attributo si escludono a vicenda perché un archivio può avere un solo layout. <br><br>Per aggiungere un attributo per filtrare gli archivi in base al layout, aggiungere una colonna denominata Layout negozio. In questo esempio, i valori per l'attributo di layout Store sono Compact, Standard e Large.
|Se è necessario indicare più valori per un attributo e i valori non si escludono a vicenda, usare il formato **AttributeName:UniqueValue** per i nomi di colonna. <br><br>**IMPORTANTE** Assicurarsi di usare i due punti (due punti) solo in :) poiché unicode non è supportato come delimitatore di colonna attributo. |Stringa di testo prima dei due punti (:) diventa il nome dell'attributo. Tutte le colonne che contengono la stessa stringa di testo prima dei due punti (:) sono raggruppati in una sezione del menu di filtro. Ognuna delle stringhe dopo i due punti diventa il valore della sezione.<br><br>Ogni riga può avere un valore pari a 0 (zero) o 1 per l'attributo. Il valore 0 indica che l'attributo non è applicabile al nodo e il valore 1 indica che l'attributo si applica a tale nodo.|Si vuole consentire agli utenti di filtrare gli archivi in base al reparto. Un negozio può avere più reparti e quindi i valori per questo attributo non si escludono a vicenda.<br><br>In questo esempio vengono aggiunti Reparti:Abbigliamento, Reparti:Elettronica, Reparti:Alimenti, Reparti:Casa e Giardino, Reparti:Articoli sportivi come colonne di attributo. I reparti diventano il nome dell'attributo e gli utenti possono filtrare in base ai reparti Abbigliamento, Elettronica, Alimenti, Casa e Giardino e Articoli sportivi.|

Quando si aggiunge una colonna attributo, tenere presente quanto segue:

* Il nome della colonna specificato o il nome della colonna specificato prima dei due punti (:) diventa il nome dell'attributo. Questo valore verrà visualizzato nelle app Teams che usano la gerarchia.
* Nella gerarchia possono essere presenti fino a 50 colonne di attributi.
* Il nome della colonna può contenere fino a 100 caratteri e contenere solo i caratteri A-Z, a-z e 0-9 e gli spazi. I nomi di colonna devono essere univoci.

### <a name="add-bucket-columns"></a>Aggiungere colonne contenitore

È possibile aggiungere colonne di contenitori per creare bucket, ovvero raggruppamenti in cui è possibile organizzare le attività. Ogni contenitore ottiene la propria colonna nel file CSV. I bucket creati vengono resi disponibili per il team di pubblicazione. Il team di pubblicazione può quindi usare questi contenitori per categorizzare le attività per i team dei destinatari. Se un contenitore non esiste già in un team, i bucket vengono creati su richiesta quando le attività vengono pubblicate.

Categorizzando gli elementi di lavoro una sola volta centralmente, il team di pubblicazione può pre-organizzare l'elenco attività per tutte le decine, centinaia o migliaia di team destinatari che ricevono l'elenco attività. I team destinatari possono quindi ordinare e filtrare le attività per contenitore per concentrarsi sull'area più pertinente per il proprio lavoro.

Quando si aggiunge una colonna bucket, tenere presente quanto segue:

* Il nome della colonna diventa il nome del contenitore. Ogni contenitore specificato verrà visualizzato nell'elenco Contenitori Teams app che usano la gerarchia.
* È consigliabile non includere informazioni riservate nei nomi dei bucket. Al momento, i team di pubblicazione non possono rimuovere un bucket tramite la pubblicazione dopo la creazione.
* Il nome della colonna deve essere preceduto da un hashtag (#). Può contenere fino a 100 caratteri e contenere solo i caratteri A-Z, a-z e 0-9. Ad esempio, #Operations e #Frozen beni.
* Una gerarchia può contenere fino a 25 colonne di bucket. Microsoft prevede di collaborare con i clienti per aumentare questo limite per le organizzazioni più grandi.

### <a name="example"></a>Esempio

Ecco un esempio di file CSV dello schema che verrebbe creato per supportare la gerarchia illustrata nell'immagine precedente. Questo schema contiene quanto segue:

* Tre colonne obbligatorie denominate `TargetName` `ParentName` , e `TeamId`
* Tre colonne di attributi denominate `Store layout` `Departments:Clothing` , , e `Departments:Foods`
* Tre colonne bucket denominate `Fresh Foods` , `Frozen Foods` e `Women's Wear`

`Store layout`L'attributo contiene valori che includono , , e `Compact` `Standard` `Large` . Le `Departments` colonne degli attributi possono essere impostate su un valore pari a `0` (zero) o `1` . Il `Store` layout e gli attributi non vengono visualizzati `Departments` nell'immagine precedente. Vengono aggiunti qui per mostrare in che modo è possibile aggiungere attributi alle voci del nodo. Lo stesso vale per le tre colonne del contenitore.

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a>Applicare la gerarchia

> [!NOTE] 
> Per eseguire questo passaggio, è necessario installare e usare il Teams di anteprima pubblica di PowerShell dalla raccolta di PowerShell. Per la procedura di installazione del modulo, vedere Installare Teams PowerShell.

> [!NOTE]
> Government Community Cloud (GCC) i clienti devono usare l'anteprima del [cmdlet versione 2.4.0 o](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) successiva per assicurarsi che i dati siano instradati all'ambiente GCC, invece che all'ambiente cloud pubblico.

Dopo aver definito la gerarchia nel file CSV dello schema, è possibile caricarla in Teams. A questo scopo, eseguire il comando seguente. Per eseguire questo passaggio, è necessario essere un amministratore globale o Teams del servizio.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>Aggiornare la gerarchia

È possibile caricare una nuova gerarchia per sostituire quella precedente usando lo stesso comando di PowerShell riportato sopra. Ogni volta che si carica una nuova gerarchia, questa sostituisce la gerarchia precedente.

### <a name="check-the-status-of-your-hierarchy"></a>Controllare lo stato della gerarchia

È possibile eseguire il comando seguente per controllare lo stato del caricamento della gerarchia.

```powershell
Get-TeamTargetingHierarchyStatus
```

Il comando restituirà i campi seguenti:

Campo|Descrizione
-----|------------
ID | ID univoco per il caricamento.
Stato | Upload stato. I valori **includono Starting**, **Validating**, **Successful** e **Failed**
ErrorDetails | Dettagli se c'è un errore di caricamento. Per altre informazioni sui dettagli dell'errore, vedere la sezione Risoluzione dei problemi. Se non ci sono errori, questo campo è vuoto.
LastUpdatedAt | Data e ora dell'ultimo aggiornamento del file.
LastModifiedBy | ID dell'ultimo utente che ha modificato il file.
NomeFile | Nome file del file CSV.

## <a name="remove-your-hierarchy"></a>Rimuovere la gerarchia

Se si vuole disabilitare immediatamente la **scheda Elenchi** pubblicati per tutti gli utenti dell'organizzazione, è possibile rimuovere la gerarchia. Gli utenti non potranno accedere alla **scheda Elenchi** pubblicati o a tutte le funzionalità della scheda.  Ciò include la possibilità di creare nuovi elenchi di attività per pubblicare, accedere a bozze di elenchi, pubblicare, annullare la pubblicazione e duplicare elenchi e visualizzare i report. La rimozione della gerarchia non annulla la pubblicazione delle attività pubblicate in precedenza. Queste attività rimarranno disponibili per il completamento dei team dei destinatari.

Per rimuovere la gerarchia, eseguire il comando seguente. Per eseguire questo passaggio, è necessario essere un amministratore.

```powershell
Remove-TeamTargetingHierarchy
```

Quando si conferma l'eliminazione, il messaggio di stato continuerà a visualizzare lo schema precedente, anche se il tentativo di eliminazione restituisce un errore che indica che l'oggetto è Null.

## <a name="create-a-sample-hierarchy"></a>Creare una gerarchia di esempio

### <a name="install-the-teams-powershell-module"></a>Installare il modulo Teams PowerShell

> [!IMPORTANT]
> Per eseguire questo passaggio, è necessario installare e usare il modulo Teams di anteprima pubblica di PowerShell dalla [raccolta di PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/) Per la procedura di installazione del modulo, vedere Installare [Teams PowerShell.](teams-powershell-install.md)

### <a name="sample-script"></a>Script di esempio

Lo script seguente può essere usato per creare i team e caricare un file .csv nel tenant Microsoft Teams. Se si ha una gerarchia esistente, questo script la sostituirà.

#### <a name="create-teams-for-a-simple-hierarchy"></a>Creare team per una gerarchia semplice

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>Usare i dati del team per creare un output separato da virgole (DisplayName, ParentName, TeamId)

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>Salvare l'output in .csv file nella **cartella** Download

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>Upload gerarchia

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="how-to-view-error-details"></a>Come visualizzare i dettagli degli errori

È possibile eseguire il comando seguente per comprendere la causa di un errore e restituire i dettagli dell'errore.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Viene visualizzato un messaggio di errore quando si carica il file CSV dello schema

Prendere nota del messaggio di errore perché dovrebbe includere informazioni sulla risoluzione dei problemi per indicare il motivo per cui non è stato possibile caricare lo schema. Esaminare e modificare il file CSV dello schema in base alle informazioni nel messaggio di errore, quindi riprovare.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Viene visualizzato un messaggio di errore "Errore: InvalidTeamId" quando si carica il file CSV dello schema

Quando si prova a caricare il file CSV dello schema, viene visualizzato il messaggio di errore seguente:

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Verificare di usare l'ID team corretto per il team nel file CSV dello schema. L'ID Team deve essere uguale all'ID gruppo del gruppo Microsoft 365 che lo contiene. È possibile cercare l'ID gruppo del team nell'Microsoft Teams di amministrazione.

1. Nel riquadro di spostamento sinistro [dell'Microsoft Teams di amministrazione](https://admin.teams.microsoft.com/)passare a Teams Gestisci   >  **team**.
2. Se la **colonna ID** gruppo non è visualizzata nella tabella, selezionare Modifica colonne nell'angolo **in** alto a destra della tabella e quindi attivare **ID gruppo.**
3. Trovare il team nell'elenco e quindi individuare l'ID gruppo.

Verificare che l'ID team nel file CSV dello schema corrisponda all'ID gruppo visualizzato nell'interfaccia di amministrazione Microsoft Teams di amministrazione.

## <a name="related-topics"></a>Argomenti correlati

* [Gestire l'app Attività per l'organizzazione in Teams](manage-tasks-app.md)
* [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
