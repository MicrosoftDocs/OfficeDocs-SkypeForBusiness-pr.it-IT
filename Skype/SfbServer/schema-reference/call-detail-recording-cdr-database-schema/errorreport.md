---
title: Tabella ErrorReport in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: Nella tabella ErrorReport sono archiviate informazioni sugli errori che si sono verificati. Ogni record corrisponde a un'occorrenza di un errore. Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.
ms.openlocfilehash: 3047ede92ec248f612249a27b7c04fc3c9f046c1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849639"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabella ErrorReport in Skype for Business Server 2015
 
Nella tabella ErrorReport sono archiviate informazioni sugli errori che si sono verificati. Ogni record corrisponde a un'occorrenza di un errore. Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Principale  <br/> |Data e ora in cui si è verificato l'errore.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la segnalazione errori. Utilizzato insieme a **ErrorTime per** identificare in modo univoco una segnalazione errori. <br/> |
|**ErrorId** <br/> |int  <br/> |Foreign  <br/> |ID univoco del tipo di errore. Per ulteriori informazioni, vedere [la tabella ErrorDef Skype for Business Server 2015.](errordef.md) <br/> |
|**FromUserId** <br/> |int  <br/> |Foreign  <br/> |Utente che ha originato la richiesta che ha causato l'errore. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**ToUserId** <br/> |int  <br/> |Foreign  <br/> |Utente di destinazione per la richiesta che ha causato l'errore. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI conferenza correlato all'errore. Per ulteriori informazioni, vedere la tabella [ConferenceUris Skype for Business Server 2015.](conferenceuris.md) In genere, se ConferenceUriId non è null, FromUserId o ToUserId sarà null. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SourceId** <br/> |int  <br/> |Foreign  <br/> |Server che ha inviato la segnalazione errori (se il report viene inviato da un componente server). Per ulteriori [informazioni, vedere](servers.md) la tabella Servers. <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Foreign  <br/> |Server che ha inviato la segnalazione errori (se il report viene inviato da un componente server). Per ulteriori [informazioni, vedere la tabella Application Skype for Business Server 2015.](application.md) <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |Ulteriori informazioni sull'errore.  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Versione client dell'endpoint che invia la segnalazione errori. Per ulteriori informazioni, vedere la tabella [ClientVersions Skype for Business Server 2015.](clientversions.md) <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||È la segnalazione errori acquisita dall'agente di registrazione dei dati in esecuzione sul server front-end o inviata dal client.  <br/> |
|**Contrassegno** <br/> |smallint  <br/> ||Riservato per utilizzi futuri.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (in millisecondi) richiesto da un componente specifico per partecipare a una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |Rappresenta il nome di dominio completo del server che ha generato la segnalazione errori.  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |Rappresenta il nome di dominio completo del pool in cui è stata generata la segnalazione errori.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto Skype for Business Server 2015.  <br/> |
   

