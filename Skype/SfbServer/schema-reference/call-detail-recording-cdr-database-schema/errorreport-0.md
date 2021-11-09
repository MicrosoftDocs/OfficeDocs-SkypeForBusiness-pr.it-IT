---
title: Visualizzazione ErrorReport
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: Nella visualizzazione ErrorReport vengono archiviate informazioni sugli errori segnalati. Ogni record corrisponde a un'occorrenza di un errore. Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 5a35cc8b3a726549be7de10259c7e59a67ca5500
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852930"
---
# <a name="errorreport-view"></a>Visualizzazione ErrorReport
 
Nella visualizzazione ErrorReport vengono archiviate informazioni sugli errori segnalati. Ogni record corrisponde a un'occorrenza di un errore. Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Data/ora in cui si è verificato l'errore. Valore utilizzato con ErrorReportSeq per identificare in modo univoco un errore.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Numero ID per identificare l'errore. Valore utilizzato con ErrorTime per identificare in modo univoco un errore.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ID diagnostica della segnalazione errori.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che ha dato origine all'errore.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che ha dato origine all'errore. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente che ha dato origine all'errore. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI dell'utente di destinazione della segnalazioni errori.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente di destinazione della segnalazione errori. Per ulteriori informazioni, vedere la tabella UriTypes.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente di destinazione della segnalazione errori. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI della conferenza di destinazione della segnalazioni errori.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI della conferenza di destinazione della segnalazioni errori. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Data/ora della richiesta di sessione che ha dato origine alla segnalazione errori. Valore utilizzato con SessionIDSeq per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la richiesta di sessione che ha dato origine alla segnalazione errori. Valore utilizzato con SessionIDTime per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID dialogo SIP della sessione che ha dato origine all'errore. Il formato è il seguente:  <br/> dialog;from-tag;to-tag  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versione del client utilizzato dall'utente che ha dato origine all'errore.  <br/> |
|**ClientType** <br/> |int  <br/> |Client utilizzato dall'utente che ha dato origine all'errore. Per ulteriori dettagli, vedere la [tabella UserAgentDef.](useragentdef.md) <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Nome della categoria del client utilizzato dall'utente che ha dato origine all'errore.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Nome del server che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).  <br/> |
|**Applicazione** <br/> |nvarchar(256)  <br/> |Nome dell'applicazione che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Codice di risposta SIP per la sessione del messaggio SIP contenente la segnalazione errori.  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |Tipo della richiesta non riuscita.  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |Tipo di contenuto della richiesta non riuscita.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |Tipo di sessione. Per ulteriori informazioni, vedere la tabella [CallType Skype for Business Server 2015.](calltype.md) <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.  <br/> |
|**SetupTime** <br/> |int  <br/> |Tempo (in millisecondi) richiesto da un componente specifico per partecipare a una conferenza.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |Indica se la segnalazione errori è stata acquisita dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o è stata inviata dal client.  <br/> |
|**Contrassegno** <br/> |smallint  <br/> |Riservato per utilizzi futuri.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Informazioni aggiuntive sull'errore.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |Nome di dominio completo del server Front End che ha inviato il report.  <br/> |
|**Pool** <br/> |nvarchar  <br/> |Nome di dominio completo del pool contenente il Front End Server che ha inviato il report.  <br/> |
   

