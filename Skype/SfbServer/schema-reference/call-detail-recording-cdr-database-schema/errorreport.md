---
title: Tabella ErrorReport in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: La Tabella ErrorReport archivia le informazioni sugli errori che si sono verificati. Ogni record è un'occorrenza di errore. Gli errori vengono acquisiti dall'agente CDR in uso nel server front-end o inviati dal client.
ms.openlocfilehash: de103c61f74b50297f9c012ae7f4c6e1586e87d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815224"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Tabella ErrorReport in Skype for Business Server 2015
 
La Tabella ErrorReport archivia le informazioni sugli errori che si sono verificati. Ogni record è un'occorrenza di errore. Gli errori vengono acquisiti dall'agente CDR in uso nel server front-end o inviati dal client.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |DateTime  <br/> |Principale  <br/> |Data e ora in cui si è verificato l'errore.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare il report degli errori. Usato in combinazione con **ErrorTime** per identificare in modo univoco una segnalazione di errori. <br/> |
|**ErrorId** <br/> |int  <br/> |Esterna  <br/> |ID univoco del tipo di errore. Per altre informazioni, vedere la [tabella ErrorDef in Skype for Business Server 2015](errordef.md) . <br/> |
|**FromUserId** <br/> |int  <br/> |Esterna  <br/> |Utente che ha originato la richiesta che ha causato l'errore. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**Touserid** <br/> |int  <br/> |Esterna  <br/> |Utente di destinazione per la richiesta che ha causato l'errore. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Esterna  <br/> |URI della conferenza correlato all'errore. Per altre informazioni, vedere la [tabella ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . In genere, se ConferenceUriId non è null, FromUserId o touserid sarà null. <br/> |
|**SessionIdTime** <br/> |DateTime  <br/> |Esterna  <br/> |Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Esterna  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SourceId** <br/> |int  <br/> |Esterna  <br/> |Server che ha inviato il report degli errori (se il report viene inviato da un componente server). Per altre informazioni, vedere la [tabella server](servers.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Esterna  <br/> |Server che ha inviato il report degli errori (se il report viene inviato da un componente server). Per altre informazioni, vedere la [tabella delle applicazioni in Skype for Business Server 2015](application.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |Altre informazioni sull'errore.  <br/> Questi dati possono essere convertiti in formato testo usando la sintassi seguente:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Esterna  <br/> |Versione client di endpoint che invia il report di errore. Per altre informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**IsCapturedByServer** <br/> |po'  <br/> ||È il rapporto di errore acquisito dall'agente CDR in uso nel server front-end o inviato dal client.  <br/> |
|**Contrassegno** <br/> |smallint  <br/> ||Riservato per un uso futuro.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Esterna  <br/> |Rappresenta il nome di dominio completo del server che ha generato il report degli errori.  <br/> |
|**PoolId** <br/> |int  <br/> |Esterna  <br/> |Rappresenta il nome di dominio completo del pool in cui è stato generato il report di errore.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

