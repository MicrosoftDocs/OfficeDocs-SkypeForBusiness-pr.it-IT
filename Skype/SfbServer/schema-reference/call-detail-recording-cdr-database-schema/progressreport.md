---
title: Tabella ProgressReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: I report sullo stato di avanzamento si basano sui dati caricati dal client nel database dopo il completamento di una chiamata o di una sessione. I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Skype for Business Server 2015 determina può essere utile per scopi diagnostici.
ms.openlocfilehash: a6cd89d7ba7f8cc03b25dc9310bdb408c85b50cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814974"
---
# <a name="progressreport-table"></a>Tabella ProgressReport
 
I report sullo stato di avanzamento si basano sui dati caricati dal client nel database dopo il completamento di una chiamata o di una sessione. I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Skype for Business Server 2015 determina può essere utile per scopi diagnostici.
  
I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non si riferiscono necessariamente agli errori, ma ai messaggi che indicano lo stato delle chiamate o dei messaggi.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Data e ora del report sugli errori di stato che contiene il report sullo stato di avanzamento. Per altre informazioni, vedere la [Tabella ErrorReport in Skype for Business Server 2015](errorreport.md) . <br/> |
|**ErrorId** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID usato in combinazione con ErrorTime, ProgressReportSeq per identificare in modo univoco un report di stato. Per altre informazioni, vedere la [Tabella ErrorReport in Skype for Business Server 2015](errorreport.md) . <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID che identifica il report degli errori. ErrorReporSeq viene usato in combinazione con ErrorTime per identificare in modo univoco una segnalazione di errori. Per altre informazioni, vedere la [Tabella ErrorReport in Skype for Business Server 2015](errorreport.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare il rapporto di stato. Usato in combinazione con ErrorTime e ErrorReportSeq per identificare in modo univoco un report di stato.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID di diagnostica del report sullo stato di avanzamento.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Esterna  <br/> |Server che ha inviato il report degli errori (se il report è stato inviato da un componente server). Per altre informazioni, vedere la [tabella server](servers.md) . Questo campo è stato introdotto in Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Processo del server Lync in cui si trova il report. Per altre informazioni, vedere la tabella delle applicazioni.  <br/> |
|**Dettaglio** <br/> |image  <br/> ||Dettagli del report sullo stato di avanzamento, archiviati in formato binario per risparmiare spazio. Questi dati possono essere convertiti in formato testo usando la sintassi seguente:  <br/> Cast (cast (dettaglio come varbinary (max)) come varchar (max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificatore univoco che correla le informazioni sull'ora di join per i diversi componenti coinvolti in una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Ora (in millisecondi) per un componente specifico per partecipare a una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

