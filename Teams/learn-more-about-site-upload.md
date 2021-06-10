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
description: Informazioni su come aggiungere e aggiornare le etichette dei report caricando un file di testo che contiene un elenco di posizioni fisiche e subnet associate.
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
ms.openlocfilehash: 481e087a6cfe2b641f6b81fcfc893d50f27cbf47
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237486"
---
<a name="add-and-update-reporting-labels"></a>Aggiungere e aggiornare etichette di reporting
============================

Le etichette dei report vengono usate nell'organizzazione per indicare le posizioni fisiche di uffici, edifici o siti dell'organizzazione. La pagina Etichette report nell'interfaccia di amministrazione di Microsoft Teams consente di fornire un file di testo (.csv o tsv) contenente un elenco delle posizioni fisiche e delle subnet di rete associate. Questo file viene usato da Call Analytics per la generazione di report. Quando si carica il mapping della subnet, i report forniti da questi servizi conterranno anche i nomi delle località, semplificando la comprensione e l'uso dei report per correggere eventuali problemi potenziali.

> [!IMPORTANT]
> Le etichette di segnalazione caricate verranno gestite come dati di supporto ai sensi  del contratto per Office 365, incluse eventuali informazioni che altrimenti verrebbero considerate Dati dei clienti *o Dati personali.*  Non includere dati che non si desidera fornire a Microsoft come dati di *supporto,* in quanto queste informazioni saranno visibili ai tecnici Microsoft per scopi di supporto.

I dati relativi alle etichette e alle posizioni dei report forniti sono un'unica struttura di dati: attualmente non è disponibile un'interfaccia per apportare singole modifiche ai dati.

**Per modificare la tabella delle subnet e delle posizioni**

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su **Etichette**  >  **report posizioni.**
2. Fare **clic Upload dati**.
3. Nel riquadro **Upload dati** fare clic su Seleziona **un file** e quindi individuare e caricare il file .csv o tsv modificato.
4. Fare **clic Upload**.

È possibile scaricare un modello di esempio [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).

Usare l'esempio seguente per creare il file di dati.

> [!IMPORTANT]
> Il file di dati non deve contenere intestazioni di colonna, ad esempio Rete, Nome rete e così via. Vengono usati qui solo a scopo informativo. <br>

|Rete|Nome rete|Intervallo di rete|Nome edificio|Tipo di proprietà|Tipo di edificio|Tipo Office edificio|Città|CAP|Paese|Stato|Area geografica|Inside Corp|Express Route|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|10.0.128.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|Stati Uniti|CA|Stati Uniti|1|1|
|10.0.130.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|Stati Uniti|CA|Stati Uniti|1|1|
|10.0.131.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|Stati Uniti|CA|Stati Uniti|1|1|
|10.0.132.0    |SVC-1|32|USCAMTV001|Contoso Leased RE&F|Office|RE&F|Mountain View|94043|Stati Uniti|CA|Stati Uniti|1|1|

Per altre informazioni sulla formattazione del file di dati, vedere Formato del file di [dati tenant e Struttura del file di dati.](CQD-upload-tenant-building-data.md#upload-building-data-file)

## <a name="related-topics"></a>Argomenti correlati

[Configurare l'analisi delle chiamate](set-up-call-analytics.md)

[Usare l'analisi delle chiamate per risolvere i problemi relativi alla scarsa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)
