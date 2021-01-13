---
title: Tabella ErrorReport in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: Nella Tabella ErrorReport vengono archiviate informazioni sugli errori che si sono verificati. Ogni record corrisponde a un'occorrenza di un errore. Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.
ms.openlocfilehash: b2f81df1134294185124d78b90c2e4f639575ded
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821676"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabella ErrorReport in Skype for Business Server 2015
 
Nella Tabella ErrorReport vengono archiviate informazioni sugli errori che si sono verificati. Ogni record corrisponde a un'occorrenza di un errore. Gli errori vengono acquisiti dall'agente registrazione dettagli chiamata in esecuzione nel Front End Server o inviati dal client.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Principale  <br/> |Data e ora in cui si è verificato l'errore.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la segnalazione errori. Utilizzato insieme a **ErrorTime** per identificare in modo univoco un report di errore. <br/> |
|**ErrorId** <br/> |int  <br/> |Stranieri  <br/> |ID univoco del tipo di errore. Per ulteriori informazioni, vedere la [tabella ErrorDef in Skype for Business Server 2015](errordef.md) . <br/> |
|**FromUserId** <br/> |int  <br/> |Stranieri  <br/> |Utente che ha originato la richiesta che ha causato l'errore. Per ulteriori informazioni, vedere la [tabella users](users.md) . <br/> |
|**Touserid** <br/> |int  <br/> |Stranieri  <br/> |Utente di destinazione per la richiesta che ha causato l'errore. Per ulteriori informazioni, vedere la [tabella users](users.md) . <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Stranieri  <br/> |URI della conferenza relativo all'errore. Per ulteriori informazioni, vedere la [tabella ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . In genere, se ConferenceUriId non è null, FromUserId o touserid sarà null. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Stranieri  <br/> |Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la [tabella Dialogs in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Stranieri  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la [tabella Dialogs in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SourceId** <br/> |int  <br/> |Stranieri  <br/> |Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server). Per ulteriori informazioni, vedere la [tabella Servers](servers.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Stranieri  <br/> |Server che ha inviato la segnalazione errori (se il rapporto è stato inviato da un componente server). Per ulteriori informazioni, vedere la [tabella applicazioni in Skype for Business Server 2015](application.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |immagine  <br/> | <br/> |Ulteriori informazioni sull'errore.  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Stranieri  <br/> |La versione client di endpoint che invia la segnalazione errori. Per ulteriori informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**IsCapturedByServer** <br/> |po'  <br/> ||È la segnalazione errori acquisita dall'agente di registrazione dettagli chiamata in esecuzione nel server front-end o inviata dal client.  <br/> |
|**Bandiera** <br/> |smallint  <br/> ||Riservato per utilizzi futuri.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Tempo (in millisecondi) richiesto da un componente specifico per partecipare a una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Stranieri  <br/> |Rappresenta il nome di dominio completo del server che ha generato la segnalazione errori.  <br/> |
|**PoolId** <br/> |int  <br/> |Stranieri  <br/> |Rappresenta il nome di dominio completo del pool in cui è stato generato il report di errore.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

