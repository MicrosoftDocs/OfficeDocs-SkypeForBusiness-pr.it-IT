---
title: Visualizzazione ErrorReport
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: La visualizzazione ErrorReport archivia le informazioni sugli errori segnalati. Ogni record è un'occorrenza di errore. Gli errori vengono acquisiti dall'agente CDR in uso nel server front-end o inviati dal client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: a95d3d1e99fc41727c10ecef7beaafddc213dd17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194809"
---
# <a name="errorreport-view"></a>Visualizzazione ErrorReport
 
La visualizzazione ErrorReport archivia le informazioni sugli errori segnalati. Ogni record è un'occorrenza di errore. Gli errori vengono acquisiti dall'agente CDR in uso nel server front-end o inviati dal client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateTime  <br/> |Periodo di errore. Usato in combinazione con ErrorReportSeq per identificare in modo univoco un errore.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numero ID per identificare l'errore. Usato in combinazione con ErrorTime per identificare in modo univoco un errore.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID di diagnostica per il report degli errori.  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha originato l'errore.  <br/> |
|**FromUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha originato l'errore. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente che ha originato l'errore. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che era la destinazione della segnalazione errori.  <br/> |
|**ToUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha la destinazione della segnalazione errori. Per altre informazioni, vedere la tabella UriTypes.  <br/> |
|**Totenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente destinatario della segnalazione errori. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI della conferenza che era la destinazione della segnalazione errori.  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI della conferenza che era la destinazione della segnalazione errori. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**SessionIdTime** <br/> |DateTime  <br/> |Ora della richiesta di sessione che ha originato il rapporto di errore. Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la richiesta di sessione che ha originato il rapporto di errore. Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |ID finestra di dialogo SIP della sessione che ha originato l'errore. Il formato è:  <br/> finestra di dialogo; da-tag; to-Tag  <br/> Questi dati possono essere convertiti in formato testo usando la sintassi seguente:  <br/> Cast (ExternalId come varbinary (max)) come varchar (max))  <br/> |
|**ClientVersion** <br/> |nvarchar (256)  <br/> |Versione del client usata dall'utente che ha originato l'errore.  <br/> |
|**TipoClient** <br/> |int  <br/> |Client usato dall'utente che ha originato l'errore. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Nome della categoria del client usata dall'utente che ha originato l'errore.  <br/> |
|**Fonte** <br/> |nvarchar (256)  <br/> |Nome del server che ha originato l'errore (se il report è stato inviato da un componente server).  <br/> |
|**Applicazione** <br/> |nvarchar (256)  <br/> |Nome dell'applicazione che ha originato l'errore (se il report è stato inviato da un componente server).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Codice di risposta SIP nella sessione del messaggio SIP contenente il report di errore.  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |Tipo di richiesta non riuscita.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |Tipo di contenuto della richiesta non riuscita.  <br/> |
|**CallType** <br/> |nvarchar (256)  <br/> |Tipo di sessione. Per altre informazioni, vedere la [tabella CallType in Skype for Business Server 2015](calltype.md) . <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.  <br/> |
|**SetupTime** <br/> |int  <br/> |Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.  <br/> |
|**IsCapturedByServer** <br/> |po'  <br/> |Indica se il report di errore è stato acquisito dall'agente CDR in uso nel server front-end o inviato dal client.  <br/> |
|**Contrassegno** <br/> |smallint  <br/> |Riservato per un uso futuro.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Altre informazioni sull'errore.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nome di dominio completo del server front-end che ha inviato il report.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nome di dominio completo del pool che contiene il front end server che ha inviato il report.  <br/> |
   

