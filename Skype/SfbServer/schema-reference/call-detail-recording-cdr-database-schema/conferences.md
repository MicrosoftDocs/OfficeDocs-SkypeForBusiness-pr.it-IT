---
title: Tabella conferenze in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Ogni record in questa tabella contiene i dettagli sulle chiamate di una conferenza.
ms.openlocfilehash: 41a2a25e80b073b568152422defeee1ca3e2ac19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194831"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabella conferenze in Skype for Business Server 2015
 
Ogni record in questa tabella contiene i dettagli sulle chiamate di una conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Principale  <br/> |Ora in cui la richiesta di conferenza è stata acquisita dall'agente CDR. Usato solo come chiave primaria per identificare in modo univoco un'istanza di conferenza.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Esterna  <br/> |URI conferenza. Per altre informazioni, vedere la [tabella ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Utile per le conferenze periodiche; ogni istanza di una conferenza ricorrente ha lo stesso **ConferenceUri**, ma avrà un **ConfInstance**diverso. <br/> |
|**ConferenceStartTime** <br/> |DateTime  <br/> | <br/> |Ora di inizio conferenza.  <br/> |
|**ConferenceEndTime** <br/> |DateTime  <br/> | <br/> |Ora di inizio conferenza.  <br/> |
|**PoolId** <br/> |int  <br/> |Esterna  <br/> |Numero ID per identificare il pool in cui è stata acquisita la conferenza. Per altre informazioni, vedere la [tabella pool](pools.md) . <br/> |
|**OrganizerId** <br/> |Int  <br/> |Esterna  <br/> |Numero ID per identificare l'URI dell'organizzatore di questa conferenza. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**Contrassegno** <br/> |smallint  <br/> || Maschera di bit che contiene gli attributi della conferenza. I valori possibili sono: <br/>  0X01 <br/>  Sintetico <br/>  Transazione <br/> |
|**Elaborate** <br/> |po'  <br/> ||Campo interno usato dal servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   
\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se due sessioni iniziano esattamente nello stesso momento, il SessionIdSeq per uno sarà 1 e per l'altro sarà 2 e così via.
  

