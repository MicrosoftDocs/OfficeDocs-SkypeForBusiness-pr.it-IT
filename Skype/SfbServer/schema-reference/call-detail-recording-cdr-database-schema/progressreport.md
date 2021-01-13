---
title: Tabella ProgressReport
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: I rapporti sullo stato sono basati sui dati caricati dal client nel database al termine di una chiamata o di una sessione. I report sullo stato saranno scritti solo per le chiamate e le sessioni che Skype for Business Server 2015 determina potrebbe essere utile a fini diagnostici.
ms.openlocfilehash: 4169ab029c0ce491b77b39735e309e102ac6e356
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823176"
---
# <a name="progressreport-table"></a>Tabella ProgressReport
 
I rapporti sullo stato sono basati sui dati caricati dal client nel database al termine di una chiamata o di una sessione. I report sullo stato saranno scritti solo per le chiamate e le sessioni che Skype for Business Server 2015 determina potrebbe essere utile a fini diagnostici.
  
I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non si riferiscono necessariamente a errori, bensì a messaggi che indicano lo stato delle chiamate o dei messaggi.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora della segnalazione degli errori di stato inclusa nel rapporto sullo stato. Per ulteriori informazioni, vedere la [Tabella ErrorReport in Skype for Business Server 2015](errorreport.md) . <br/> |
|**ErrorId** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID utilizzato insieme a ErrorTime e ProgressReportSeq per identificare in modo univoco un rapporto sullo stato. Per ulteriori informazioni, vedere la [Tabella ErrorReport in Skype for Business Server 2015](errorreport.md) . <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primaria/o, esterna/o  <br/> |Numero ID che identifica la segnalazione errori. ErrorReporSeq viene utilizzato insieme a ErrorTime per identificare in modo univoco un rapporto di errore. Per ulteriori informazioni, vedere la [Tabella ErrorReport in Skype for Business Server 2015](errorreport.md) <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare il rapporto sullo stato. Utilizzato insieme a ErrorTime ed ErrorReportSeq per identificare in modo univoco un rapporto sullo stato.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||ID diagnostica del rapporto sullo stato.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Stranieri  <br/> |Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server). Per ulteriori informazioni, vedere la [tabella Servers](servers.md) . Questo campo è stato introdotto in Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Processo di Lync Server a cui fa riferimento il rapporto. Per ulteriori informazioni, vedere la tabella Application.  <br/> |
|**Dettagli** <br/> |immagine  <br/> ||Dettagli del rapporto sullo stato archiviati in formato binario per non occupare troppo spazio. I dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificatore univoco che correla informazioni relative al tempo di partecipazione per i diversi componenti coinvolti in una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (in millisecondi) necessario per un componente specifico per partecipare a una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

