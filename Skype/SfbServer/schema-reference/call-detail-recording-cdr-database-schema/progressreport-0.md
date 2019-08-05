---
title: Visualizzazione ProgressReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La Visualizzazione ProgressReport archivia le informazioni sulle sessioni completate. I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Lync Server 2013 determina può essere utile per scopi diagnostici. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: e5ad388c2845be63926f2172f944abc08f58481e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194758"
---
# <a name="progressreport-view"></a>Visualizzazione ProgressReport
 
La Visualizzazione ProgressReport archivia le informazioni sulle sessioni completate. I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Lync Server 2013 determina può essere utile per scopi diagnostici. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non si riferiscono necessariamente agli errori, ma ai messaggi che indicano lo stato delle chiamate o dei messaggi. 
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateTime  <br/> |Periodo di errore. Usato in combinazione con ErrorReportSeq per identificare in modo univoco un errore.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numero ID per identificare l'errore. Usato in combinazione con ErrorTime per identificare in modo univoco un errore.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID per identificare il report di stato. Usato per distinguere i report sullo stato dello stesso rapporto di errore.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID di diagnostica per il report degli errori.  <br/> |
|**Fonte** <br/> |nvarchar (256)  <br/> |Nome del server che ha originato l'errore (se il report è stato inviato da un componente server).  <br/> |
|**Applicazione** <br/> |nvarchar (256)  <br/> |Nome dell'applicazione che ha originato l'errore (se il report è stato inviato da un componente server).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Altre informazioni sugli errori.  <br/> |
   

