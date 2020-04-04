---
title: Aggiungere e aggiornare etichette di reporting
author: tonysmit
ms.author: tonysmit
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come aggiungere e aggiornare le etichette dei report caricando un file di testo contenente un elenco di percorsi fisici e subnet associate.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.locations.reportinglabels.overview
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.location
- ms.teamsadmincenter.locations.overview
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b245566c0920604dac0e10e6a6cfe49937570bc2
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137116"
---
<a name="add-and-update-reporting-labels"></a>Aggiungere e aggiornare etichette di reporting
============================

Le etichette dei report vengono usate nell'organizzazione per indicare le posizioni fisiche di uffici, edifici o siti organizzativi. La pagina delle etichette dei report nell'interfaccia di amministrazione di Microsoft teams consente di specificare un file di testo (CSV o TSV) contenente un elenco di percorsi fisici e le subnet di rete associate. Questo file viene usato da Call Analytics e Call Quality dashboard per la generazione di report. Quando si carica il mapping della subnet, i report forniti da questi servizi conterranno anche i nomi della posizione, semplificando la comprensione e l'uso dei report per risolvere eventuali problemi potenziali.

Le etichette dei report e i dati relativi alle posizioni che fornisci sono una singola struttura di dati, attualmente non è disponibile alcuna interfaccia per apportare singole modifiche ai dati.

**Per modificare la tabella delle subnet e delle posizioni**

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **posizioni** > che**segnalano etichette**.
2. Fare clic su **Sostituisci dati percorsi**.
3. Nel riquadro **Sostituisci dati posizione** fare clic su **Seleziona un file**e quindi selezionare e caricare il file CSV o TSV modificato.
4. Fare clic su **carica**.

È possibile scaricare un modello di esempio [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Usare l'esempio seguente per creare il file di dati.

> [!IMPORTANT]
> Il file di dati non deve contenere intestazioni di colonna, ad esempio rete, nome rete e così via. Questi vengono usati solo a scopo informativo. <br>

|Rete|Nome rete|Intervallo di rete|Nome dell'edificio|Tipo di proprietà|Tipo di edificio|Tipo di Office Building|Città|CAP|Paese|Stato|Area|All'interno di Corp|Route Express|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso leased ri&F|Office|RI&F|Visualizzazione Mountain|94043|NOI|CA|NOI|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso leased ri&F|Office|RI&F|Visualizzazione Mountain|94043|NOI|CA|NOI|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso leased ri&F|Office|RI&F|Visualizzazione Mountain|94043|NOI|CA|NOI|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso leased ri&F|Office|RI&F|Visualizzazione Mountain|94043|NOI|CA|NOI|1|1|

Per altre informazioni sulla formattazione del file di dati, vedere [formato di file di dati tenant e struttura del file di dati dell'edificio](turning-on-and-using-call-quality-dashboard.md#tenant-data-file-format-and-structure).

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)
