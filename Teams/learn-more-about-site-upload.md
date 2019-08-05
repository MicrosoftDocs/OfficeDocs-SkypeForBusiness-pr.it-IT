---
title: Aggiunta e aggiornamento dei dati delle posizioni
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Informazioni su come caricare un sito.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.locations.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e7e9211b207c008de22fe86ae0c7bb6c9f9ac51
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "36184024"
---
<a name="adding-and-updating-locations-data"></a>Aggiunta e aggiornamento dei dati delle posizioni
============================

I percorsi vengono usati nell'organizzazione per indicare le posizioni fisiche di uffici, edifici o siti organizzativi. La pagina posizioni offre agli amministratori la possibilità di fornire un file di testo (CSV o TSV) contenente un elenco di percorsi fisici e le subnet di rete associate. Questo file viene usato da Call Analytics e Call Quality dashboard per la generazione di report. Quando i clienti caricano il mapping della subnet, i report forniti da questi servizi conterranno anche i nomi di località, rendendo i report più comprensibili e usati per correggere eventuali problemi.

I dati relativi alle posizioni fornite sono una singola struttura di dati, ma attualmente non è disponibile alcuna interfaccia per apportare singole modifiche ai dati della posizione. 

**Per modificare la tabella delle subnet e delle posizioni**

1. Fare clic su **Sostituisci dati percorsi**.
2. Nel riquadro **Sostituisci dati posizione** fare clic su **Seleziona un file**e quindi selezionare e caricare il file CSV o TSV modificato. 
3. Fare clic su **carica**. 


È possibile scaricare un modello di esempio [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Puoi usare l'esempio seguente per facilitare la creazione del file di dati. 

> [!IMPORTANT]
> Il file di dati non deve contenere intestazioni di colonna, ad esempio rete, nome rete e così via. Questi vengono usati solo a scopo informativo. </br>

|Rete|Nome rete|Intervallo di rete|Nome dell'edificio|Tipo di proprietà|Tipo di edificio|Tipo di Office Building|Città|CAP|Paese|Stato|Area geografica|All'interno di Corp|Route Express|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0 |SVC-1|32|USCAMTV001|Contoso leased ri&F|Ufficio|RI&F|Visualizzazione Mountain|94043|NOI|CA|NOI|1|1|
|10.0.130.0 |SVC-1|32|USCAMTV001|Contoso leased ri&F|Ufficio|RI&F|Visualizzazione Mountain|94043|NOI|CA|NOI|1|1|
|10.0.131.0 |SVC-1|32|USCAMTV001|Contoso leased ri&F|Ufficio|RI&F|Visualizzazione Mountain|94043|NOI|CA|NOI|1|1|
|10.0.132.0 |SVC-1|32|USCAMTV001|Contoso leased ri&F|Ufficio|RI&F|Visualizzazione Mountain|94043|NOI|CA|NOI|1|1|


Per altre informazioni sulla formattazione del file di dati, vedere [formato di file di dati tenant e struttura del file di dati dell'edificio](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).


## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)
