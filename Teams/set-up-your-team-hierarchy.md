---
title: Configurare la gerarchia di destinazione del team
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: Informazioni su come configurare una gerarchia del team nell'organizzazione per pubblicare contenuto in un set di team di grandi dimensioni.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c5a0fcdce1218bc32eac8b28e7a8c1f41e87cb0
ms.sourcegitcommit: 9787b84ab15ee2e14890151e966c81b4a4d43e62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868341"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurare la gerarchia di destinazione del team

La configurazione di una gerarchia di destinazione del team consentirà all'organizzazione di pubblicare contenuto in un set di team di grandi dimensioni. La gerarchia di destinazione del team definisce il modo in cui tutti i team della gerarchia sono correlati tra loro, che gli utenti possono pubblicare attività e a quali utenti del team sono assegnate le autorizzazioni per la pubblicazione. Le funzionalità di pubblicazione sono disabilitate per tutti gli utenti, a meno che non sia stata configurata una gerarchia di destinazione del team per l'organizzazione. Per configurare una gerarchia di destinazione del team, è necessario creare un file che definisce la gerarchia e quindi caricarlo in teams per applicarlo all'organizzazione. Dopo il caricamento dello schema, le app all'interno dei team possono usarle.

> [!IMPORTANT]
> Per la versione iniziale, solo l'app attività supporta i team gerarchici.  L'applicazione di una gerarchia di destinazione del team all'organizzazione consentirà la [pubblicazione delle attività](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) nell'app attività. Non verrà visualizzata una gerarchia di team in altre aree di Microsoft teams.

Ecco un esempio di come viene rappresentata la gerarchia nell'app attività in teams. Dopo la creazione di un elenco di attività, i membri del team di pubblicazione possono quindi selezionare i team del destinatario a cui inviare (pubblicare) l'elenco attività. Quando si seleziona teams, il team di pubblicazione può filtrare in base alla gerarchia, agli attributi o a una combinazione di entrambi.<br>

![Screenshot della pubblicazione delle attività](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>Terminologia

I termini seguenti saranno importanti durante l'esplorazione delle gerarchie. I team verranno chiamati **nodi**.

* I nodi radice sono i nodi di **primo livello** nella gerarchia. Nell'esempio le comunicazioni al dettaglio sono un nodo radice.
* I nodi **padre** e i **nodi figlio** sono termini che rappresentano una relazione tra due nodi connessi. Nell'esempio, il distretto 01 è un nodo figlio dell'area 1.
* Più livelli di elementi figlio sono denominati **discendenti**. Il distretto 01, lo Store 01, lo Store 03, il Store 07, il distretto 02 e il distretto 03 sono tutti discendenti dell'area 1.
* Un nodo senza elementi figlio è detto **nodo foglia**. Sono nella parte inferiore di una gerarchia.
* I **team dei destinatari** sono team selezionati per ricevere un set specifico di contenuto da pubblicare. Devono essere nodi foglia.

## <a name="plan-your-hierarchy"></a>Pianificare la gerarchia

Prima di creare lo schema che definisce la gerarchia, è necessario eseguire alcune operazioni di pianificazione e decidere come modellare l'organizzazione.  Una delle prime priorità consiste nel decidere quali gruppi di organizzazione devono pubblicare attività in altri gruppi. Ogni nodo della gerarchia rappresenta un gruppo di lavoro o un gruppo di gruppi.

### <a name="permissions-to-publish"></a>Autorizzazioni per la pubblicazione

Le autorizzazioni per la pubblicazione variano a seconda che un utente sia un membro di qualsiasi team nella gerarchia, più la relazione di tale team o gruppo di teams ad altri team nella gerarchia.

> [!NOTE]
> Al proprietario di un team sono concesse anche le autorizzazioni di pubblicazione.

* Se un utente è un membro di almeno un team con discendenti nella gerarchia, l'utente può pubblicare tali discendenti senza essere un membro di tutti i team a cui vogliono pubblicare.
* Se un utente è un membro di almeno un team nella gerarchia, ma non è un membro di un team con discendenti nella gerarchia, l'utente può vedere e ricevere contenuto pubblicato dall'organizzazione.
* Se un utente non è un membro di un team nella gerarchia, l'utente non vedrà alcuna funzionalità correlata alla pubblicazione.

### <a name="guidelines"></a>Linee guida

* Per ogni organizzazione può essere applicato un solo file gerarchico. È tuttavia possibile includere insieme diverse parti dell'organizzazione come gerarchie distinte di nodi all'interno di un file CSV. Ad esempio, Contoso Pharmaceuticals ha un nodo radice della farmacia e un nodo radice al dettaglio. Entrambi i nodi radice hanno più righe di discendenti e non c'è sovrapposizione tra di essi.
* Solo i nodi foglia possono essere destinatari di una pubblicazione. Altri nodi della gerarchia sono utili per selezionare i destinatari di una pubblicazione.
* Un team può essere rappresentato una sola volta in una gerarchia.
* Una gerarchia può contenere fino a 15.000 nodi. Intendiamo collaborare con i clienti per aumentare questo limite per le organizzazioni di grandi dimensioni.

### <a name="example-hierarchy"></a>Gerarchia di esempio

Nella gerarchia seguente, ad esempio, richiamo, comunicazioni e HR può pubblicare attività in ogni nodo inferiore (Team) nella gerarchia, ma la zona nord-est può pubblicare le attività solo nei team di New York Store e Boston Store. La gerarchia di esempio consente ai gruppi di richiamo, comunicazioni e HR di pubblicare attività che si applicano all'intera società, ad esempio informazioni sui vantaggi o messaggi del CEO. La zona nord-est può pubblicare attività come la pianificazione del personale, le informazioni meteo e così via, solo per i team di New York Store e Boston Store.

![Esempio gerarchico del team](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>Creare la gerarchia

> [!NOTE]
> Il resto di questo articolo descrive la configurazione di una gerarchia del team nel contesto delle attività di pubblicazione in teams destinatari. Vedere [gestire l'app attività per l'organizzazione in teams](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) per una panoramica dell'app attività, in cui viene visualizzata la pubblicazione delle attività quando è abilitata.

Lo schema che definisce la gerarchia si basa su un file con valori delimitati da virgole (CSV). Ogni riga del file CSV corrisponde a un nodo all'interno della gerarchia di teams. Ogni riga contiene informazioni che denominano il nodo all'interno della gerarchia, lo collega facoltativamente a un team e include attributi che possono essere usati per filtrare i team nelle app che la supportano.

È anche possibile definire i **bucket**, ovvero le categorie che il team di pubblicazione può usare per organizzare i contenuti inviati ai team del destinatario per semplificare la visualizzazione, l'ordinamento e lo stato attivo sul contenuto pertinente.

### <a name="add-required-columns"></a>Aggiungere colonne obbligatorie

Il file CSV deve contenere le tre colonne seguenti, nell'ordine seguente, a partire dalla prima colonna. Un nodo deve essere collegato a un team per ricevere le attività.

| Nome colonna   | Obbligatorio | Descrizione   |
----------------|----------|---------------|
| DisplayName    | Sì      | Questo campo è il nome del nodo. Il nome può contenere fino a 100 caratteri di lunghezza e contiene solo i caratteri A-Z, a-z e 0-9. I nomi dei nodi devono essere univoci. |
| ParentName    | Sì       | Questo è il nome del nodo padre. Il valore specificato in questa posizione deve corrispondere esattamente al valore nel campo **DisplayName** del nodo padre. Se si vogliono aggiungere più nodi padre, separare ogni nome di nodo padre con un punto e virgola (;). È possibile aggiungere fino a 25 nodi padre e ogni nome di nodo padre può contenere fino a 2500 caratteri di lunghezza. Un nodo può avere più nodi padre solo se i nodi padre sono nodi radice.   <br><br>**Importante** Prestare attenzione a non creare un ciclo in cui un elemento padre più in alto nella gerarchia fa riferimento a un nodo figlio inferiore nella gerarchia. Questo non è supportato. |
| TeamId        | Sì, se il team pubblica attività o riceve attività da un nodo padre       | Contiene l'ID del team a cui si vuole collegare un nodo. Ogni nodo deve fare riferimento a un team univoco, quindi ogni valore TeamId può essere visualizzato una sola volta nel file della gerarchia. Per ottenere l'ID di un team a cui si vuole collegare un nodo, eseguire il comando di PowerShell seguente: `Get-Team | Export-Csv TeamList.csv` . Questo comando elenca i team dell'organizzazione e include il nome e l'ID per ogni team. Individuare il nome del team a cui si vuole creare il collegamento e quindi copiare l'ID in questo campo.|

> [!NOTE]
> Se un nodo non è un nodo radice o un nodo foglia e non è necessario che l'appartenenza del team conceda le autorizzazioni appropriate per la pubblicazione e la creazione di report, è possibile abbandonare il TeamId vuoto. Questo metodo può essere usato per aggiungere maggiore granularità quando si sceglie team destinatari o per visualizzare i report di completamento senza avere un team corrispondente.

### <a name="add-attribute-columns"></a>Aggiungere colonne di attributi

Dopo aver aggiunto le tre colonne obbligatorie, è possibile aggiungere colonne di attributi facoltative. Questi attributi possono essere usati per filtrare i nodi in modo da poter selezionare più facilmente quelli a cui si vogliono pubblicare le attività. Esistono due modi per definire gli attributi, a seconda che i valori per tale attributo si escludano a vicenda.

|Modalità di aggiunta di attributi|Descrizione |Esempio  |
|---|---------|---------|
|Se i valori di un attributo si escludono a vicenda, il nome della colonna specificato diventa il nome dell'attributo.|Ogni riga può contenere un valore per tale attributo e ogni colonna attributo può avere fino a 50 valori univoci. Ogni valore può contenere fino a 100 caratteri di lunghezza. Il set di valori di attributi specificati nella colonna Attribute verrà visualizzato come valori di filtro per tale attributo quando si seleziona team di destinatari che usano la gerarchia di destinazione del team.|Si vuole consentire agli utenti di filtrare gli archivi in base al layout. I valori per questo attributo si escludono a vicenda perché uno Store può avere un solo layout. <br><br>Per aggiungere un attributo per filtrare gli archivi in base al layout, aggiungere una colonna denominata layout archivio. In questo esempio i valori per l'attributo di layout dello Store sono Compact, standard e large.
|Se devi indicare più valori per un attributo e i valori non si escludono a vicenda, usa il formato **attributeName: UniqueValue** per i nomi di colonna. <br><br>**Importante** Assicurarsi di usare i due punti solo in lingua inglese (:) Poiché Unicode non è supportato come delimitatore di colonna attributo. |Stringa di testo prima dei due punti (:) diventa il nome dell'attributo. Tutte le colonne che contengono la stessa stringa di testo prima dei due punti (:) vengono raggruppati in una sezione del menu filtro. Ognuna delle stringhe dopo che i due punti diventano i valori per la sezione.<br><br>Ogni riga può avere un valore pari a 0 (zero) o 1 per tale attributo. Il valore 0 indica che l'attributo non si applica al nodo e il valore 1 indica che l'attributo si applica a tale nodo.|Si vuole consentire agli utenti di filtrare gli archivi per reparto. Un archivio può avere più reparti e quindi i valori per questo attributo non si escludono a vicenda.<br><br>In questo esempio aggiungiamo reparti: Abbigliamento, reparti: elettronica, reparti: Foods, reparti: Home and Garden, reparti: articoli sportivi come colonne attributo. I reparti diventano il nome dell'attributo e gli utenti possono filtrare in base ai reparti abbigliamento, elettronica, alimenti, casa e giardino e articoli sportivi.|

Quando si aggiunge una colonna attributo, tieni presente quanto segue:

* Il nome della colonna specificato o il nome della colonna specificato prima dei due punti (:) diventa il nome dell'attributo. Questo valore verrà visualizzato nelle app team che usano la gerarchia.
* Puoi avere fino a 50 colonne di attributi nella gerarchia.
* Il nome della colonna può essere lungo fino a 100 caratteri e contiene solo i caratteri A-Z, a-z e 0-9 e gli spazi. I nomi di colonna devono essere univoci.

### <a name="add-bucket-columns"></a>Aggiungere colonne del bucket

È possibile aggiungere colonne del bucket per creare bucket, che sono raggruppamenti in cui le attività possono essere organizzate. Ogni bucket ottiene la propria colonna nel file CSV. I bucket creati vengono resi disponibili per il team di pubblicazione. Il team di pubblicazione può quindi usare questi bucket per categorizzare le attività per i team del destinatario. Se un bucket non è già presente in un team, i bucket vengono creati su richiesta quando le attività vengono pubblicate.

Categorizzando gli elementi di lavoro una volta al centro, il team di pubblicazione può preorganizzare l'elenco attività per tutte le decine, centinaia o migliaia di team di destinatari che ricevono l'elenco attività. I team dei destinatari possono quindi ordinare e filtrare le attività in base al bucket per concentrarsi sull'area più rilevante per il lavoro.

Quando si aggiunge una colonna bucket, tenere presente quanto segue:

* Il nome della colonna diventa il nome del bucket. Ogni bucket specificato verrà visualizzato nell'elenco bucket nelle app teams che usano la gerarchia.
* È consigliabile non includere informazioni riservate nei nomi dei bucket. Al momento, i team di pubblicazione non possono rimuovere un bucket tramite la pubblicazione dopo la creazione.
* Il nome della colonna deve essere preceduto da un hashtag (#). Può contenere fino a 100 caratteri di lunghezza e contiene solo i caratteri A-Z, a-z e 0-9. Ad esempio, #Operations e #Frozen beni.
* Una gerarchia può contenere fino a 25 colonne del bucket. Intendiamo collaborare con i clienti per aumentare questo limite per le organizzazioni di grandi dimensioni.

### <a name="example"></a>Esempio

Ecco un esempio di file CSV dello schema che verrebbe creato per supportare la gerarchia visualizzata nell'immagine precedente. Questo schema contiene gli elementi seguenti:

* Tre colonne obbligatorie denominate `TargetName` `ParentName` e `TeamId`
* Tre colonne attributo denominate `Store layout` `Departments:Clothing` e `Departments:Foods`
* Tre colonne del bucket denominate `Fresh Foods` `Frozen Foods` e `Women's Wear`

L' `Store layout` attributo contiene valori che includono `Compact` , `Standard` e `Large` . Le `Departments` colonne dell'attributo possono essere impostate su un valore `0` (zero) o `1` . Il `Store` layout e `Departments` gli attributi non vengono visualizzati nell'immagine precedente. Sono stati aggiunti qui per mostrare come aggiungere attributi alle voci di nodo. Lo stesso vale per le tre colonne del bucket.

```CSV
"TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear"
"Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,"
"Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,"
"HR,,,,,,,,,,"
"East Regional Office,,,,,,,,,,"
"West Regional Office,,,,,,,,,,"
"Northeast Zone,East Regional Office,,,,,,,,"
"Southeast Zone,East Regional Office,,,,,,,,"
"New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,"
"Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,"
"Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,"
"New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,"
"Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,"
"Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,"
```

## <a name="apply-your-hierarchy"></a>Applicare la gerarchia

Dopo aver definito la gerarchia nel file CSV dello schema, si è pronti per caricarla in teams. A tale scopo, eseguire il comando seguente. Per eseguire questa procedura è necessario essere un amministratore globale o un amministratore del servizio teams.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>Aggiornare la gerarchia

È possibile caricare una nuova gerarchia per sostituire quella precedente usando lo stesso comando di PowerShell come indicato sopra. Ogni volta che si carica una nuova gerarchia, sostituisce la gerarchia precedente.

### <a name="check-the-status-of-your-hierarchy"></a>Controllare lo stato della gerarchia

Per controllare lo stato del caricamento della gerarchia, è possibile eseguire il comando seguente.

```powershell
Get-TeamTargetingHierarchyStatus
```

Il comando restituirà i campi seguenti:

Campo|Descrizione
-----|------------
ID | ID univoco per il caricamento.
Stato | Carica stato. I valori includono l' **avvio**, la **convalida**, l' **esito positivo** e il **errore**
ErrorDetails | Dettagli se si verifica un errore di caricamento. Per altre informazioni sui dettagli dell'errore, vedere la sezione risoluzione dei problemi. Se non c'è un errore, questo campo è vuoto.
LastUpdatedAt | Timestamp e data in cui il file è stato aggiornato per ultimo.
LastModifiedBy | ID dell'ultimo utente che ha modificato il file.
Nome file | Il nome del file CSV.

## <a name="remove-your-hierarchy"></a>Rimuovere la gerarchia

Se si vuole disabilitare immediatamente la scheda **elenchi pubblicati** per tutti gli utenti dell'organizzazione, è possibile rimuovere la gerarchia. Gli utenti non avranno accesso alla scheda **elenchi pubblicati** o a nessuna delle funzionalità nella scheda.  Questo include la possibilità di creare nuovi elenchi di attività da pubblicare, accedere a elenchi di bozze, pubblicare, annullare la pubblicazione e duplicare elenchi e visualizzare i report. La rimozione della gerarchia non annulla la pubblicazione delle attività pubblicate in precedenza. Queste attività rimarranno disponibili per il completamento dei team destinatari.

Per rimuovere la gerarchia, eseguire il comando seguente. Per eseguire questo passaggio, è necessario essere un amministratore.

```powershell
Remove-TeamTargetingHierarchy
```

Quando si conferma l'eliminazione, il messaggio di stato continuerà a visualizzare lo schema precedente, anche se il tentativo di eliminare restituisce nuovamente un errore che indica che l'oggetto è null.

## <a name="create-a-sample-hierarchy"></a>Creare una gerarchia di esempio

### <a name="install-the-teams-powershell-module"></a>Installare il modulo di PowerShell Teams

> [!IMPORTANT]
> Per eseguire questo passaggio, è necessario installare e usare il modulo di anteprima pubblica di PowerShell teams dalla [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Per istruzioni su come installare il modulo, vedere [installare teams PowerShell](teams-powershell-install.md).

### <a name="sample-script"></a>Script di esempio

Lo script seguente può essere usato per creare i team e caricare un file CSV nel tenant di Microsoft teams. Se si ha una gerarchia esistente, questo script lo sostituirà.

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

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>Usare i dati del team per creare un output separato da virgola (DisplayName, ParentName, TeamId)

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

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>Salvare l'output in un file CSV nella cartella **Downloads**

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

Puoi eseguire il comando seguente per capire cosa sta causando un errore e restituire i dettagli dell'errore.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Viene visualizzato un messaggio di errore quando si carica il file CSV dello schema

Tenere presente che il messaggio di errore dovrebbe includere informazioni sulla risoluzione dei problemi per indicare il motivo per cui non è stato possibile caricare lo schema. Rivedere e modificare il file CSV dello schema in base alle informazioni contenute nel messaggio di errore e quindi riprovare.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Viene visualizzato un messaggio di errore "errore: InvalidTeamId" quando si carica il file CSV dello schema

Quando si prova a caricare il file CSV dello schema, viene visualizzato il messaggio di errore seguente:

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Verificare che si stia usando la TeamId corretta per il team nel file CSV dello schema. Il TeamId deve essere uguale all'ID del gruppo Microsoft 365 che appoggia il team. Puoi cercare l'ID gruppo del team nell'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com/), passa a **Teams**  >  **Manage teams**.
2. Se la colonna **ID gruppo** non viene visualizzata nella tabella, selezionare **modifica colonne** nell'angolo in alto a destra della tabella e quindi attivare l' **ID gruppo**.
3. Trovare il team nell'elenco e quindi individuare l'ID del gruppo.

Verificare che il TeamId nel file CSV dello schema corrisponda all'ID del gruppo visualizzato nell'interfaccia di amministrazione di Microsoft teams.

## <a name="related-topics"></a>Argomenti correlati

* [Gestire l'app attività per l'organizzazione in teams](manage-tasks-app.md)
* [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
