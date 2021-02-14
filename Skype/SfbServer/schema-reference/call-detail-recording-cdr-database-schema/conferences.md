---
title: Tabella Conferences in Skype for Business Server 2015
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
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Ogni record in questa tabella contiene i dettagli delle chiamate su una conferenza.
ms.openlocfilehash: 85da16807d6f314fb4f9239601c77a7aed2842ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813216"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabella Conferences in Skype for Business Server 2015
 
Ogni record in questa tabella contiene i dettagli delle chiamate su una conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principale  <br/> |Ora in cui la richiesta di conferenza è stata acquisita dall'agente cdR. Utilizzato solo come chiave primaria per identificare in modo univoco un'istanza di conferenza.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Utilizzato insieme a **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Esterna  <br/> |URI della conferenza. Per ulteriori informazioni, vedere la tabella [ConferenceUris in Skype for Business Server 2015.](conferenceuris.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Utile per conferenze ricorrenti; Ogni istanza di una conferenza ricorrente ha lo stesso **ConferenceUri,** ma avrà una **ConfInstance diversa.** <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Ora di inizio della conferenza.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Ora di inizio della conferenza.  <br/> |
|**PoolId** <br/> |int  <br/> |Esterna  <br/> |Numero ID per identificare il pool in cui è stata acquisita la conferenza. Per ulteriori [informazioni, vedere](pools.md) la tabella Pools. <br/> |
|**OrganizerId** <br/> |Soglia  <br/> |Esterna  <br/> |Numero ID per identificare l'URI dell'organizzatore della conferenza. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**Flag** <br/> |smallint  <br/> || Maschera di bit che contiene gli attributi della conferenza. I valori possibili sono: <br/>  0X01 <br/>  Sintetico <br/>  Transazione <br/> |
|**Elaborata** <br/> |bit  <br/> ||Campo interno utilizzato dal servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   
\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se due sessioni iniziano esattamente contemporaneamente, sessionIdSeq per una sarà 1 e per l'altra sarà 2 e così via.
  

