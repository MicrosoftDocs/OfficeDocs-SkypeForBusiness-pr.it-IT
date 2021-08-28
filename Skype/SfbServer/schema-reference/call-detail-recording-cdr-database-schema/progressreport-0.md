---
title: Visualizzazione ProgressReport
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: Nella visualizzazione ProgressReport vengono archiviate le informazioni relative alle sessioni completate. Tali rapporti sullo stato verranno scritti solo per le chiamate e le sessioni ritenute utili da Lync Server 2013 a fini diagnostici. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 8e21b83b1ca6c4856ba31a579e4a7999ba8b31a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623538"
---
# <a name="progressreport-view"></a>Visualizzazione ProgressReport
 
Nella visualizzazione ProgressReport vengono archiviate le informazioni relative alle sessioni completate. Tali rapporti sullo stato verranno scritti solo per le chiamate e le sessioni ritenute utili da Lync Server 2013 a fini diagnostici. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non fanno necessariamente riferimento a errori, ma a messaggi che indicano lo stato delle chiamate o dei messaggi. 
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Data/ora in cui si è verificato l'errore. Valore utilizzato con ErrorReportSeq per identificare in modo univoco un errore.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |ID che identifica l'errore. Questo valore viene utilizzato insieme a ErrorTime per identificare in modo univoco un errore.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |ID che identifica il rapporto sullo stato. Questo valore viene utilizzato per distinguere i rapporti sullo stato della stessa segnalazione di errore.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID diagnostica della segnalazione di errore.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nome del server che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).  <br/> |
|**Applicazione** <br/> |nvarchar(256)  <br/> |Nome dell'applicazione da cui ha avuto origine l'errore (se la segnalazione è stata inviata da un componente server).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Intervallo di tempo, in millisecondi, necessario a un componente specifico per partecipare a una conferenza.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Ulteriori informazioni sull'errore.  <br/> |
   

