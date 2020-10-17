---
title: Configurare la gerarchia di destinazione del team
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: Informazioni su come configurare una gerarchia del team nell'organizzazione per pubblicare contenuto in un set di team di grandi dimensioni.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f78d507a7ab15cfa43e10d51e13f36749f11a7cb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526393"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurare la gerarchia di destinazione del team

> **Questa caratteristica è attualmente in anteprima privata.**

Per creare una gerarchia di team che può essere usata dall'organizzazione per pubblicare contenuto in un set di team di grandi dimensioni, è necessario configurare lo schema di destinazione del team. Lo schema definisce il modo in cui tutti i team della gerarchia sono correlati tra loro e gli attributi che possono essere usati per filtrare i team. Dopo aver creato lo schema, viene caricato in teams e la gerarchia viene applicata in tutta l'organizzazione. Dopo il caricamento dello schema, le app all'interno del client teams possono usarle. 

> [!IMPORTANT]
> Quando si esplorano team o canali al suo interno, non verrà visualizzata una gerarchia di team. Per visualizzare la gerarchia dei team, devi usare un'app che la supporta. Per la versione iniziale, solo l'app attività supporta i team gerarchici. Il resto di questo articolo descrive la configurazione di una gerarchia del team nel contesto delle attività di pubblicazione in teams destinatari. Prima di configurare la gerarchia di destinazione del team, vedere [gestire l'app attività per l'organizzazione in teams](manage-tasks-app.md) per una panoramica della pubblicazione delle attività.

Ecco un esempio di come viene rappresentata la gerarchia nell'app attività in teams. Dopo la creazione di un elenco di attività, i membri del team di pubblicazione possono quindi selezionare i team del destinatario a cui inviare (pubblicare) l'elenco attività. Quando si seleziona teams, il team di pubblicazione può filtrare in base alla gerarchia, agli attributi o a una combinazione di entrambi.<br>

![Screenshot della pubblicazione delle attività](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>Pianificare la gerarchia

Prima di creare lo schema che definisce la gerarchia, è necessario eseguire alcune operazioni di pianificazione e decidere come modellare l'organizzazione. Questo include la scelta dei gruppi di organizzazione che devono pubblicare le attività in altri gruppi. Ogni nodo della gerarchia rappresenta un gruppo di lavoro o un gruppo di gruppi. I nodi nella parte inferiore della gerarchia (quelli senza elementi figlio) sono team che possono ricevere attività mentre altri nodi (genitori) sono gruppi di organizzazione con l'autorizzazione per pubblicare le attività verso il basso. Un team può essere rappresentato una sola volta nella gerarchia.

Ad esempio, nella gerarchia seguente, richiamo, comunicazioni al dettaglio e HR possono pubblicare attività in tutti i nodi inferiori (Team) nella gerarchia, mentre l'area nord est può pubblicare le attività solo nei team di New York Store e Boston Store. Questa gerarchia consente alle comunicazioni di richiamo, al dettaglio e ai gruppi HR di pubblicare attività che si applicano all'intera società, ad esempio le informazioni sui vantaggi o i messaggi del CEO. La zona nord-est può pubblicare attività, ad esempio pianificazione del personale, informazioni meteo e così via, solo per i team di New York Store e Boston Store.

![Esempio gerarchico del team](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>Creare la gerarchia

Lo schema che definisce la gerarchia si basa su un file con valori delimitati da virgole (CSV). Ogni riga del file CSV corrisponde a un nodo all'interno della gerarchia di teams. Ogni riga contiene informazioni che denominano il nodo all'interno della gerarchia, lo collega facoltativamente a un team e include attributi che possono essere usati per filtrare i team nelle app che la supportano.

È anche possibile definire i bucket, ovvero le categorie che il team di pubblicazione può usare per organizzare i contenuti inviati ai team del destinatario per semplificare la visualizzazione, l'ordinamento e lo stato attivo sul contenuto pertinente.

### <a name="add-required-columns"></a>Aggiungere colonne obbligatorie

Il file CSV deve contenere le tre colonne seguenti, nell'ordine seguente, a partire dalla prima colonna. Un nodo deve essere collegato a un team per ricevere le attività. Durante l'anteprima privata supportiamo i nodi di 500. All'avvio prevediamo di supportare almeno i nodi di 2.000 per impostazione predefinita. Intendiamo collaborare con i clienti per aumentare questo limite per le organizzazioni di grandi dimensioni.

| Nome colonna   | Obbligatorio | Descrizione   |
----------------|----------|---------------|
| TargetName    | Sì      | Questo è il nome del nodo. Il nome può contenere fino a 100 caratteri di lunghezza e contiene solo i caratteri A-Z, a-z e 0-9. I nomi dei nodi devono essere univoci. |
| ParentName    | Sì       | Questo è il nome del nodo padre. Il valore specificato in questa posizione deve corrispondere esattamente al valore nel campo TargetName del nodo padre. Se si vogliono aggiungere più nodi padre, separare ogni nome di nodo padre con un punto e virgola (;). È possibile aggiungere fino a 25 nodi padre e ogni nome di nodo padre può contenere fino a 2500 caratteri di lunghezza. Un nodo può avere più nodi padre solo se i nodi padre sono nodi radice.   <br><br>**Importante** Prestare attenzione a non creare un ciclo in cui un elemento padre più in alto nella gerarchia fa riferimento a un nodo figlio inferiore nella gerarchia. Questo non è supportato. |
| TeamId        | Sì, se il team pubblica attività o riceve attività da un nodo padre       | Contiene l'ID del team a cui si vuole collegare un nodo. Un nodo deve essere collegato a un team se si trova nella parte inferiore della gerarchia, se si vuole che gli utenti possano pubblicare da tale nodo o se si vuole che gli utenti possano vedere la creazione di report per il nodo e i relativi discendenti. Ad esempio, se il tuo Manager per l'area della West Region vuole visualizzare i report di completamento delle attività per i nodi che appartengono all'area geografica.<br><br>Se si vuole aggiungere un nodo solo per il raggruppamento di altri nodi nella gerarchia, non è necessario collegare tale nodo a un team e non è possibile lasciarlo vuoto. È possibile collegare ogni nodo a un solo team.<br>Per ottenere l'ID di un team a cui si vuole collegare un nodo, eseguire il comando di PowerShell seguente: `Get-Team | Export-Csv TeamList.csv` . In questo articolo vengono elencati i team dell'organizzazione e sono inclusi il nome e l'ID per ogni team. Individuare il nome del team a cui si vuole creare il collegamento e quindi copiare l'ID in questo campo.|

### <a name="add-attribute-columns"></a>Aggiungere colonne di attributi

Dopo aver aggiunto le tre colonne obbligatorie, è possibile aggiungere colonne di attributi facoltative. Questi attributi possono essere usati per filtrare i nodi in modo da poter selezionare più facilmente quelli a cui si vogliono pubblicare le attività. Esistono due modi per definire gli attributi, a seconda che i valori per tale attributo si escludano a vicenda.

|Modalità di aggiunta di attributi|Descrizione |Esempio  |
|---|---------|---------|
|Se i valori di un attributo si escludono a vicenda, il nome della colonna specificato diventa il nome dell'attributo.|Ogni riga può contenere un valore per tale attributo e ogni valore può avere una lunghezza di 100 caratteri. Il set di valori di attributo specificato nella colonna Attribute verrà visualizzato come valori di filtro disponibili per tale attributo nelle app teams che usano la gerarchia. Ogni colonna Attribute può avere fino a 50 valori univoci. |Si vuole consentire agli utenti di filtrare gli archivi in base al layout. I valori per questo attributo si escludono a vicenda perché uno Store può avere un solo layout. <br><br>Per aggiungere un attributo per filtrare gli archivi in base al layout, aggiungere una colonna denominata layout archivio. In questo esempio i valori per l'attributo di layout dello Store sono Compact, standard e large.
|Se devi indicare più valori per un attributo e i valori non si escludono a vicenda, usa il formato **attributeName: UniqueValue** per i nomi di colonna. |Stringa di testo prima dei due punti (:) diventa il nome dell'attributo. Tutte le colonne che contengono la stessa stringa di testo prima dei due punti (:) vengono raggruppati in una sezione del menu filtro. Ognuna delle stringhe dopo che i due punti diventano i valori per la sezione.<br><br>Ogni riga può avere un valore pari a 0 (zero) o 1 per tale attributo. Il valore 0 indica che l'attributo non si applica al nodo e il valore 1 indica che l'attributo si applica a tale nodo.|Si vuole consentire agli utenti di filtrare gli archivi per reparto. Un archivio può avere più reparti e quindi i valori per questo attributo non si escludono a vicenda.<br><br>In questo esempio aggiungiamo reparti: Abbigliamento, reparti: elettronica, reparti: Foods, reparti: Home and Garden, reparti: articoli sportivi come colonne attributo. I reparti diventano il nome dell'attributo e gli utenti possono filtrare in base ai reparti abbigliamento, elettronica, alimenti, casa e giardino e articoli sportivi.|

Quando si aggiunge una colonna attributo, tieni presente quanto segue:

- Il nome della colonna specificato o il nome della colonna specificato prima dei due punti (:) diventa il nome dell'attributo. Questo valore verrà visualizzato nelle app team che usano la gerarchia.
- Il nome della colonna può essere lungo fino a 100 caratteri e contiene solo i caratteri A-Z, a-z e 0-9 e gli spazi. I nomi di colonna devono essere univoci.
- All'avvio, prevediamo di consentire le colonne attributo 50.

### <a name="add-bucket-columns"></a>Aggiungere colonne del bucket

È possibile aggiungere colonne del bucket per creare bucket, che sono raggruppamenti in cui le attività possono essere organizzate. Ogni bucket ottiene la propria colonna nel file CSV. I bucket creati vengono resi disponibili per il team di pubblicazione. Il team di pubblicazione può quindi usare questi bucket per categorizzare le attività per i team del destinatario. Se un bucket non è già presente in un team, i bucket vengono creati su richiesta quando le attività vengono pubblicate.

Categorizzando il lavoro una volta al centro, il team di pubblicazione può preorganizzare l'elenco attività per tutte le decine, centinaia o migliaia di team di destinatari che ricevono l'elenco attività. I team dei destinatari possono quindi ordinare e filtrare le attività in base al bucket per concentrarsi sull'area più rilevante per il lavoro.

Quando si aggiunge una colonna bucket, tenere presente quanto segue:

- Il nome della colonna diventa il nome del bucket. Ogni bucket specificato verrà visualizzato nell'elenco bucket nelle app teams che usano la gerarchia. È consigliabile non includere informazioni riservate nei nomi dei bucket. Al momento, i team di pubblicazione non possono rimuovere un bucket tramite la pubblicazione dopo la creazione.
- Il nome della colonna deve essere preceduto da un hashtag (#). Può contenere fino a 100 caratteri di lunghezza e contiene solo i caratteri A-Z, a-z e 0-9. Ad esempio, #Operations e #Frozen beni.
- All'avvio prevediamo di supportare le 25 colonne del bucket. Intendiamo collaborare con i clienti per aumentare questo limite per le organizzazioni di grandi dimensioni.

### <a name="example"></a>Esempio

Ecco un esempio di file CSV dello schema che verrebbe creato per supportare la gerarchia visualizzata nell'immagine precedente. Questo schema contiene gli elementi seguenti:

- Tre colonne obbligatorie denominate `TargetName` `ParentName` e `TeamId`
- Tre colonne attributo denominate `Store layout` `Departments:Clothing` e `Departments:Foods`
- Tre colonne del bucket denominate `Fresh Foods` `Frozen Foods` e `Womenswear`

L' `Store layout` attributo contiene valori che includono `Compact` , `Standard` e `Large` . Le `Departments` colonne dell'attributo possono essere impostate su un valore `0` (zero) o `1` . Il `Store` layout e `Departments` gli attributi non vengono visualizzati nell'immagine precedente. Sono stati aggiunti qui per mostrare come aggiungere attributi alle voci di nodo. Lo stesso vale per le tre colonne del bucket.


| TargetName             | ParentName                      | TeamId                       | Layout dello Store|Reparti: Abbigliamento|Reparti: alimenti|#Fresh alimenti|#Frozen alimenti|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| Richiamare                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| Comunicazioni         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| Risorse umane                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| Ufficio della regione est   |                         |                                      |||||||
| Ufficio regionale occidentale   |                         |                                      |||||||
| Zona nord-est        | Ufficio della regione est    |                                      |||||||
| Zona sud-est        | Ufficio della regione est    |                                      |||||||
| New York Store         | Zona nord-est         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |Grande|1|1||||
| Boston Store           | Zona nord-est         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| Negozio di Miami            | Zona sud-est         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |Compatta|0|1||||
| New Orleans Store      | Zona sud-est         | 6be960b8-72af-4561-A343-9ac4711874eb |Compatta|0|1||||
| Archivio di Seattle          | Ufficio regionale occidentale    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| Negozio di Los Angeles      | Ufficio regionale occidentale    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |Grande|1|1||||

## <a name="apply-your-hierarchy"></a>Applicare la gerarchia

> [!IMPORTANT]
> Per eseguire questo passaggio, è necessario installare e usare il modulo di anteprima pubblica di PowerShell teams dalla [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Per istruzioni su come installare il modulo, vedere [installare teams PowerShell](teams-powershell-install.md).

Dopo aver definito la gerarchia nel file CSV dello schema, si è pronti per caricarla in teams. A tale scopo, eseguire il comando seguente. Per eseguire questa procedura è necessario essere un amministratore globale o un amministratore del servizio teams.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>Rimuovere la gerarchia

> [!IMPORTANT]
> Per eseguire questo passaggio, è necessario installare e usare il modulo di anteprima pubblica di PowerShell teams dalla [raccolta di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Per istruzioni su come installare il modulo, vedere [installare teams PowerShell](teams-powershell-install.md).

Se si vuole disabilitare immediatamente la scheda **elenchi pubblicati** per tutti gli utenti dell'organizzazione, è possibile rimuovere la gerarchia. Gli utenti non avranno accesso alla scheda **elenchi pubblicati** o a nessuna delle funzionalità nella scheda.  Questo include la possibilità di creare nuovi elenchi di attività da pubblicare, accedere a elenchi di bozze, pubblicare, annullare la pubblicazione e duplicare elenchi e visualizzare i report. La rimozione della gerarchia non annulla la pubblicazione delle attività pubblicate in precedenza. Queste attività rimarranno disponibili per il completamento dei team destinatari. 

Per rimuovere la gerarchia, eseguire il comando seguente. Per eseguire questo passaggio, è necessario essere un amministratore. 

```powershell
Remove-TeamTargetingHierarchy
```

## <a name="troubleshooting"></a>Risoluzione dei problemi

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

- [Gestire l'app attività per l'organizzazione in teams](manage-tasks-app.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
