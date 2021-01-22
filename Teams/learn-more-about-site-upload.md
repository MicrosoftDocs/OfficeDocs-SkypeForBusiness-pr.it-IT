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
description: Informazioni su come aggiungere e aggiornare le etichette dei report caricando un file di testo contenente un elenco di posizioni fisiche e subnet associate.
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
ms.openlocfilehash: 4a1af7f14695d1f933a9c3902b373eb668044e24
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918642"
---
<a name="add-and-update-reporting-labels"></a>Aggiungere e aggiornare etichette di reporting
============================

Le etichette dei report vengono usate nell'organizzazione per indicare la posizione fisica di uffici, edifici o siti dell'organizzazione. La pagina Etichette report nell'interfaccia di amministrazione di Microsoft Teams consente di fornire un file di testo (con estensione csv o tsv) contenente un elenco di posizioni fisiche e le subnet di rete associate. Questo file viene utilizzato da Call Analytics per la generazione di report. Quando si carica la mappatura della subnet, i report forniti da questi servizi conterranno anche i nomi delle località, semplificando la comprensione e l'uso dei report per la risoluzione di potenziali problemi.

> [!IMPORTANT]
> Le etichette per le relazioni  caricate verranno gestite come Dati di supporto ai sensi del contratto per Office 365, incluse eventuali informazioni che verrebbero altrimenti *considerate* dati dei clienti o *dati personali.* Non includere dati che non desideri fornire a Microsoft come dati di supporto *perché* queste informazioni saranno visibili ai tecnici Microsoft a scopo di supporto.

I dati relativi alle etichette e alle posizioni dei report forniti costituiscono un'unica struttura di dati e al momento non è disponibile alcuna interfaccia per apportare singole modifiche ai dati.

**Per modificare l'indice delle subnet e delle posizioni**

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams fare clic su **Etichette** per la  >  **creazione di rapporti sulle posizioni.**
2. Fare clic **su Sostituisci dati posizione.**
3. Nel riquadro **dei dati Sostituisci** posizioni fare clic su Seleziona un **file** e quindi individuare e caricare il file con estensione csv o tsv modificato.
4. Fare clic **su Carica.**

È possibile scaricare un modello di [esempio qui.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)

Usare l'esempio seguente per creare il file di dati.

> [!IMPORTANT]
> Il file di dati non deve contenere intestazioni di colonna, ad esempio Rete, Nome rete e così via. Qui vengono usate solo a scopo informativo. <br>

|Rete|Nome rete|Intervallo di rete|Nome edificio|Tipo di proprietà|Tipo di edificio|Building Office Type|Città|CAP|Paese|Stato|Area geografica|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Vista delle montagne|94043|Stati Uniti|CA|Stati Uniti|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Vista delle montagne|94043|Stati Uniti|CA|Stati Uniti|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Vista delle montagne|94043|Stati Uniti|CA|Stati Uniti|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Vista delle montagne|94043|Stati Uniti|CA|Stati Uniti|1|1|

Per altre informazioni sulla formattazione del file di dati, vedere Formato del file di [dati tenant e Struttura del file di dati.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Usare i dati analitici delle chiamate per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)
