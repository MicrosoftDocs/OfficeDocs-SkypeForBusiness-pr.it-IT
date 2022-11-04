---
title: Configurare la gerarchia di destinazione del team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: Informazioni su come configurare una gerarchia di team nell'organizzazione per pubblicare contenuto in un ampio set di team.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: dc4e7e88e855432f17c7daed9584e20e0e4739f1
ms.sourcegitcommit: fcbbc197e43bcd63bf95cb329df9cb52e06ee356
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2022
ms.locfileid: "68842114"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurare la gerarchia di destinazione del team

L'impostazione di una gerarchia di assegnazione del team consentirà all'organizzazione di pubblicare contenuti in un ampio set di team. La gerarchia di assegnazione team definisce in che modo tutti i team della gerarchia sono correlati tra loro, in quali utenti possono pubblicare attività e in quali team gli utenti hanno le autorizzazioni per la pubblicazione. Le caratteristiche di pubblicazione sono disabilitate per tutti gli utenti, a meno che non sia configurata una gerarchia di assegnazione del team per l'organizzazione. Per impostare una gerarchia di assegnazione del team, è necessario creare un file che definisce la gerarchia e quindi caricarlo in Teams per applicarlo all'organizzazione. Dopo aver caricato lo schema, le app all'interno di Teams possono usarlo.

> [!IMPORTANT]
> Per la versione iniziale, solo l'app Attività supporta i team gerarchici.  L'applicazione di una gerarchia di assegnazione team all'organizzazione consente la [pubblicazione delle attività](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) nell'app Attività. Non verrà visualizzata una gerarchia di team in altre aree di Microsoft Teams.

Ecco un esempio di come la gerarchia è rappresentata nell'app Attività in Teams. Dopo aver creato un elenco attività, i membri del team di pubblicazione possono quindi selezionare i team di destinatari a cui inviare (pubblicare) l'elenco attività. Quando si selezionano i team, il team di pubblicazione può filtrare in base alla gerarchia, agli attributi o a una combinazione di entrambi.<br>

![Screenshot della pubblicazione delle attività.](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>Terminologia

I termini seguenti saranno importanti durante l'esplorazione delle gerarchie. I team verranno definiti **nodi**.

* **I nodi radice** sono i nodi più alti della gerarchia. Nell'esempio, Retail Communications è un nodo radice.
* **I nodi padre** e **i nodi figlio** sono termini che rappresentano una relazione tra due nodi connessi. Nell'esempio, District 01 è un nodo figlio di Area 1.
* Più livelli di figli sono definiti **discendenti**. District 01, Store 01, Store 03, Store 07, District 02 e District 03 sono tutti discendenti dell'Area 1.
* Un nodo senza figli è chiamato **nodo foglia**. Sono in fondo a una gerarchia.
* **I team destinatari** sono team che sono stati selezionati per ricevere un set specifico di contenuti da pubblicare. Devono essere nodi fogliari.

## <a name="plan-your-hierarchy"></a>Pianificare la gerarchia

Prima di creare lo schema che definisce la gerarchia, è necessario eseguire una pianificazione e decidere come modellare l'organizzazione.  Una delle prime priorità è decidere quali gruppi dell'organizzazione devono pubblicare attività in altri gruppi. Ogni nodo della gerarchia rappresenta un gruppo di lavoro o un gruppo di gruppi.

### <a name="permissions-to-publish"></a>Autorizzazioni per la pubblicazione

L'autorizzazione per la pubblicazione dipende dal fatto che un utente sia un membro di qualsiasi team nella gerarchia oltre alla relazione del team o del set di team con altri team della gerarchia.

> [!NOTE]
> Al proprietario di un team vengono concesse anche le autorizzazioni di pubblicazione.

* Se un utente è membro di almeno un team che dispone di discendenti nella gerarchia, l'utente può pubblicare in tali discendenti senza essere un membro di tutti i team in cui vuole pubblicare.
* Se un utente è membro di almeno un team della gerarchia, ma non è membro di alcun team con discendenti nella gerarchia, l'utente può visualizzare e ricevere contenuto pubblicato dall'organizzazione.
* Se un utente non è un membro di alcun team nella gerarchia, non vedrà alcuna funzionalità correlata alla pubblicazione.

### <a name="guidelines"></a>Linee guida

* Per ogni organizzazione può essere applicato un solo file gerarchico. Tuttavia, è possibile includere diverse parti dell'organizzazione come gerarchie distinte di nodi all'interno di un file. Ad esempio, Contoso Pharmaceuticals ha un nodo radice farmacia e un nodo radice retail. Entrambi i nodi radice hanno più righe di discendenti e non vi è alcuna sovrapposizione tra di essi.
* Solo i nodi foglia possono essere destinatari di una pubblicazione. Altri nodi nella gerarchia sono utili per selezionare i destinatari di una pubblicazione.
* Un team può essere rappresentato una sola volta in una gerarchia.
* Una gerarchia può contenere fino a 15.000 nodi. Prevediamo di collaborare con i clienti per aumentare questo limite per le organizzazioni più grandi.

### <a name="example-hierarchy"></a>Gerarchia di esempio

Ad esempio, nella gerarchia seguente, Recall, Communications e HR possono pubblicare attività in ogni nodo inferiore (team) della gerarchia, ma La zona nord-est può pubblicare attività solo nei team di New York Store e Boston Store. La gerarchia di esempio consente ai gruppi Richiamo, Comunicazioni e Risorse umane di pubblicare attività che si applicano all'intera società, ad esempio informazioni sui vantaggi o messaggi dal CEO. La zona nord-est può pubblicare attività come la pianificazione del personale, le informazioni meteo e così via, solo nei team di New York Store e Boston Store.

![Esempio gerarchico del team.](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>Creare la gerarchia

> [!NOTE]
> Il resto di questo articolo descrive l'impostazione di una gerarchia di team nel contesto della pubblicazione di attività ai team dei destinatari. Vedere [Gestire l'app Attività per l'organizzazione in Teams](./manage-tasks-app.md) per una panoramica dell'app Attività, in cui la pubblicazione delle attività viene visualizzata quando è abilitata.

Lo schema che definisce la gerarchia si basa su un file con valori delimitati da virgole (CSV). Il file deve essere in formato UTF-8. Ogni riga nel file CSV corrisponde a un nodo nella gerarchia dei team. Ogni riga contiene informazioni che denominano il nodo all'interno della gerarchia, lo collega facoltativamente a un team e include attributi che possono essere usati per filtrare i team nelle app che lo supportano.

È anche possibile definire **i contenitori**, ovvero le categorie che il team di pubblicazione può usare per organizzare il contenuto inviato ai team dei destinatari, in modo da facilitarne la visualizzazione, l'ordinamento e l'attenzione sul contenuto pertinente.

### <a name="add-required-columns"></a>Aggiungere colonne obbligatorie

Il file CSV deve contenere le tre colonne seguenti, nell'ordine seguente, a partire dalla prima colonna. Per ricevere le attività, un nodo deve essere collegato a un team.

| Nome colonna   | Obbligatorio | Descrizione   |
----------------|----------|---------------|
| Displayname    | Sì      | Questo campo è il nome del nodo. Il nome può contenere fino a 100 caratteri e contenere solo i caratteri A-Z, a-z e 0-9. I nomi dei nodi devono essere univoci. |
| NomeMaschera    | Sì       | Questo è il nome del nodo padre. Il valore specificato qui deve corrispondere esattamente al valore nel campo **DisplayName** del nodo padre. Se si desidera aggiungere più nodi padre, separare ogni nome di nodo padre con un punto e virgola (;). È possibile aggiungere fino a 25 nodi padre e ogni nome di nodo padre può contenere fino a 2500 caratteri. Un nodo può avere più nodi padre solo se i nodi padre sono nodi radice.   <br><br>**IMPORTANTE** Prestare attenzione a non creare un ciclo in cui un elemento padre più in alto nella gerarchia faccia riferimento a un nodo figlio più in basso nella gerarchia. Questa funzionalità non è supportata. |
| TeamId        | Sì, se il team pubblica attività o riceve attività da un nodo padre       | Contiene l'ID del team a cui si vuole collegare un nodo. Ogni nodo deve fare riferimento a un team univoco, quindi ogni valore TeamId può essere visualizzato una sola volta nel file della gerarchia. Per ottenere l'ID di un team a cui vuoi collegare un nodo, esegui il comando di PowerShell seguente: `Get-Team | Export-Csv TeamList.csv`. Questo comando elenca i team dell'organizzazione e include il nome e l'ID di ogni team. Trovare il nome del team a cui si vuole creare un collegamento e quindi copiare l'ID in questo campo.|

> [!NOTE]
> Se un nodo non è un nodo radice o un nodo foglia e non è necessaria l'appartenenza al team per concedere le autorizzazioni corrispondenti per la pubblicazione e la creazione di report, è possibile lasciare vuoto TeamId. Questo metodo può essere usato per aggiungere maggiore granularità quando si scelgono i team dei destinatari o per visualizzare i report di completamento senza avere un team corrispondente.

### <a name="add-attribute-columns"></a>Aggiungere colonne di attributi

Dopo aver aggiunto le tre colonne obbligatorie, è possibile aggiungere colonne attributo facoltative. Questi attributi possono essere usati per filtrare i nodi in modo da poter selezionare più facilmente quelli in cui pubblicare le attività. Esistono due modi per definire gli attributi, a seconda che i valori per l'attributo si escludono a vicenda.

|Modi per aggiungere attributi|Descrizione |Esempio  |
|---|---------|---------|
|Se i valori di un attributo si escludono a vicenda, il nome di colonna specificato diventa il nome dell'attributo.|Ogni riga può contenere un valore per l'attributo e ogni colonna dell'attributo può avere fino a 50 valori univoci. Ogni valore può contenere fino a 100 caratteri. Il set di valori di attributo specificato nella colonna degli attributi verrà visualizzato come valori di filtro per l'attributo quando si selezionano i team destinatari usando la gerarchia di assegnazione team.|Si vuole consentire agli utenti di filtrare gli archivi in base al layout. I valori per questo attributo si escludono a vicenda perché un archivio può avere un solo layout. <br><br>Per aggiungere un attributo per filtrare gli archivi in base al layout, aggiungere una colonna denominata Layout archivio. In questo esempio i valori per l'attributo di layout Store sono Compact, Standard e Large.
|Se è necessario indicare più valori per un attributo e i valori non si escludono a vicenda, usare il formato **AttributeName:UniqueValue** per i nomi di colonna. <br><br>**IMPORTANTE** Assicurarsi di usare i due punti solo in inglese (:) poiché unicode non è supportato come delimitatore di colonna degli attributi. |Stringa di testo prima dei due punti (:) diventa il nome dell'attributo. Tutte le colonne che contengono la stessa stringa di testo prima dei due punti (:) vengono raggruppati in una sezione del menu di filtro. Ognuna delle stringhe dopo i due punti diventa i valori per tale sezione.<br><br>Ogni riga può avere un valore pari a 0 (zero) o 1 per l'attributo. Un valore pari a 0 indica che l'attributo non si applica al nodo e un valore pari a 1 indica che l'attributo si applica a tale nodo.|Si vuole consentire agli utenti di filtrare gli archivi in base al reparto. Un archivio può avere più reparti e quindi i valori per questo attributo non si escludono a vicenda.<br><br>In questo esempio vengono aggiunti reparti:abbigliamento, reparti:elettronica, reparti:alimenti, reparti:casa e giardino, reparti:articoli sportivi come colonne attributo. I reparti diventano il nome dell'attributo e gli utenti possono filtrare in base ai reparti abbigliamento, elettronica, cibi, casa e giardino e articoli sportivi.|

Quando si aggiunge una colonna di attributi, tenere presente quanto segue:

* Nome di colonna specificato o nome di colonna specificato prima dei due punti (:) diventa il nome dell'attributo. Questo valore verrà visualizzato nelle app di Teams che usano la gerarchia.
* Nella gerarchia possono essere presenti fino a 50 colonne di attributi.
* Il nome della colonna può contenere fino a 100 caratteri e contenere solo i caratteri A-Z, a-z, 0-9 e spazi. I nomi di colonna devono essere univoci.

### <a name="add-bucket-columns"></a>Aggiungere colonne bucket

È possibile aggiungere colonne contenitore per creare contenitori, ovvero raggruppamenti in cui organizzare le attività. Ogni contenitore ottiene la propria colonna nel file CSV. I contenitori creati vengono resi disponibili al team di pubblicazione. Il team di pubblicazione può quindi usare questi contenitori per categorizzare le attività per i team dei destinatari. Se un contenitore non esiste già in un team, i contenitori vengono creati su richiesta quando vengono pubblicate le attività.

Categorizzando centralmente gli elementi di lavoro, il team di pubblicazione può pre-organizzare l'elenco attività per tutte le decine, le centinaia o le migliaia di team destinatari che ricevono l'elenco attività. I team destinatari possono quindi ordinare e filtrare le attività per contenitore per concentrarsi sull'area più rilevante per il proprio lavoro.

Quando si aggiunge una colonna bucket, tenere presente quanto segue:

* Il nome della colonna diventa il nome del contenitore. Ogni contenitore specificato verrà visualizzato nell'elenco Contenitori nelle app di Teams che usano la gerarchia.
* È consigliabile non includere informazioni riservate nei nomi dei bucket. Al momento, i team di pubblicazione non possono rimuovere un contenitore tramite la pubblicazione dopo la creazione.
* Il nome della colonna deve essere preceduto da un hashtag (#). Può contenere fino a 100 caratteri e contenere solo i caratteri A-Z, a-z e 0-9. Ad esempio, #Operations e #Frozen Prodotti.
* Una gerarchia può contenere fino a 25 colonne bucket. Prevediamo di collaborare con i clienti per aumentare questo limite per le organizzazioni più grandi.

### <a name="example"></a>Esempio

Ecco un esempio di file CSV dello schema che verrà creato per supportare la gerarchia mostrata nell'immagine precedente. Questo schema contiene quanto segue:

* Tre colonne obbligatorie denominate `TargetName`, `ParentName`e `TeamId`
* Tre colonne di attributi denominate `Store layout`, `Departments:Clothing`e `Departments:Foods`
* Tre colonne del contenitore denominate `Fresh Foods`, `Frozen Foods`e `Women's Wear`

L'attributo `Store layout` include valori che includono `Compact`, `Standard`e `Large`. Le `Departments` colonne degli attributi possono essere impostate su un valore pari `0` a (zero) o `1`. Il `Store` layout e `Departments` gli attributi non sono visualizzati nell'immagine precedente. Vengono aggiunti qui per mostrare in che modo gli attributi possono essere aggiunti alle voci del nodo. Lo stesso vale per le tre colonne del contenitore.

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
> Per eseguire questo passaggio, è necessario usare i cmdlet di Microsoft Teams PowerShell. È consigliabile usare la versione 4.6.0 o successiva dei cmdlet di Microsoft Teams. Questo requisito si applica anche ai clienti di Government Community Cloud (GCC).

Dopo aver definito la gerarchia nel file CSV dello schema, è possibile caricarla in Teams. A questo scopo, eseguire il comando seguente. Per eseguire questo passaggio, è necessario essere un amministratore globale o un amministratore dei servizi di Teams.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>Aggiornare la gerarchia

È possibile caricare una nuova gerarchia per sostituire quella precedente usando lo stesso comando di PowerShell riportato sopra. Ogni volta che si carica una nuova gerarchia, questa sostituisce quella precedente.

### <a name="check-the-status-of-your-hierarchy"></a>Controllare lo stato della gerarchia

È possibile eseguire il comando seguente per controllare lo stato del caricamento della gerarchia.

```powershell
Get-TeamTargetingHierarchyStatus
```

Il comando restituirà i campi seguenti:

Campo|Descrizione
-----|------------
Id | ID univoco per il caricamento.
Stato | Stato caricamento. I valori includono **Avvio**, **Convalida**, **Esito positivo** e **Non riuscito**
ErrorDetails | Dettagli in caso di errore di caricamento. Per altre informazioni sui dettagli dell'errore, vedere la sezione Risoluzione dei problemi. Se non si verificano errori, questo campo è vuoto.
LastUpdatedAt | Data e ora dell'ultimo aggiornamento del file.
LastModifiedBy | ID dell'ultimo utente che ha modificato il file.
Filename | Nome file del file CSV.

## <a name="remove-your-hierarchy"></a>Rimuovere la gerarchia

Se si vuole disabilitare immediatamente la scheda **Elenchi pubblicati** per tutti gli utenti dell'organizzazione, è possibile rimuovere la gerarchia. Gli utenti non avranno accesso alla scheda **Elenchi pubblicati** o alle funzionalità della scheda.  È inclusa la possibilità di creare nuovi elenchi attività per pubblicare, accedere alle bozze di elenchi, pubblicare, annullare la pubblicazione e duplicare elenchi e visualizzare i report. La rimozione della gerarchia non annulla la pubblicazione di attività pubblicate in precedenza. Queste attività rimarranno disponibili per il completamento dei team dei destinatari.

Per rimuovere la gerarchia, eseguire il comando seguente. Per eseguire questo passaggio, è necessario essere un amministratore.

```powershell
Remove-TeamTargetingHierarchy
```

Quando si conferma l'eliminazione, il messaggio di stato continuerà a visualizzare lo schema precedente, anche se il tentativo di eliminare nuovamente restituisce un errore che indica che l'oggetto è Null.

## <a name="create-a-sample-hierarchy"></a>Creare una gerarchia di esempio

### <a name="install-the-teams-powershell-module"></a>Installare il modulo Di Teams PowerShell

> [!IMPORTANT]
> Per eseguire questo passaggio, è necessario installare e usare il modulo Di Teams PowerShell dal [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/). Per la procedura di installazione del modulo, vedere [Installare il modulo PowerShell di Microsoft Teams](teams-powershell-install.md).

### <a name="sample-script"></a>Script di esempio

Lo script seguente può essere usato per creare i team e caricare un file .csv nel tenant di Microsoft Teams. Se si dispone di una gerarchia esistente, questo script la sostituirà.

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

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>Usare i dati del team per creare output separato da virgole (DisplayName, ParentName, TeamId)

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

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>Salvare l'output in un file di .csv nella cartella **Download**

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>Caricare la gerarchia

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="how-to-view-error-details"></a>Come visualizzare i dettagli degli errori

È possibile eseguire il comando seguente per comprendere la causa dell'errore e restituire i dettagli dell'errore.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Viene visualizzato un messaggio di errore quando si carica il file CSV dello schema

Prendere nota del messaggio di errore perché dovrebbe includere informazioni sulla risoluzione dei problemi per indicare il motivo per cui non è stato possibile caricare lo schema. Rivedere e modificare il file CSV dello schema in base alle informazioni nel messaggio di errore e quindi riprovare.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Viene visualizzato un messaggio di errore "Errore: InvalidTeamId" quando si carica il file CSV dello schema

Quando si prova a caricare il file CSV dello schema, viene visualizzato il messaggio di errore seguente:

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Verificare di usare l'ID Team corretto per il team nel file CSV dello schema. L'ID team deve essere uguale all'ID gruppo del gruppo di Microsoft 365 a supporto del team. È possibile cercare l'ID gruppo del team nell'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra [dell'interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/), passare a **Gestione team di Teams** > .
2. Se la colonna **ID gruppo** non è visualizzata nella tabella, selezionare **Modifica colonne** nell'angolo in alto a destra della tabella e quindi attivare **ID gruppo**.
3. Trovare il team nell'elenco e quindi individuare l'ID gruppo.

Assicurarsi che TeamId nel file CSV dello schema corrisponda all'ID gruppo visualizzato nell'interfaccia di amministrazione di Microsoft Teams.

## <a name="related-topics"></a>Argomenti correlati

* [Gestire l'app Attività per l'organizzazione in Teams](manage-tasks-app.md)
* [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
