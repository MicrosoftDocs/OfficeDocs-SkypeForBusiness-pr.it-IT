---
title: Tabella conferenze in Skype for Business Server 2015
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
description: Ogni record di questa tabella contiene i dettagli sulle chiamate relative a una conferenza.
ms.openlocfilehash: 85da16807d6f314fb4f9239601c77a7aed2842ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813216"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tabella conferenze in Skype for Business Server 2015
 
Ogni record di questa tabella contiene i dettagli sulle chiamate relative a una conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principale  <br/> |Ora in cui la richiesta di conferenza è stata acquisita dall'agente di registrazione dettagli chiamata. Viene utilizzata solo come chiave primaria per identificare in modo univoco un'istanza di conferenza.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Utilizzato insieme a **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Stranieri  <br/> |URI della conferenza. Per ulteriori informazioni, vedere la [tabella ConferenceUris in Skype for Business Server 2015](conferenceuris.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Utile per le conferenze ricorrenti; ogni istanza di una conferenza ricorrente ha lo stesso **ConferenceUri**, ma avrà una **ConfInstance** diversa. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Ora di inizio della conferenza.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Ora di inizio della conferenza.  <br/> |
|**PoolId** <br/> |int  <br/> |Stranieri  <br/> |Numero ID per identificare il pool in cui è stata acquisita la conferenza. Per ulteriori informazioni, vedere la [Tabella Pools](pools.md) . <br/> |
|**OrganizerId** <br/> |Soglia  <br/> |Stranieri  <br/> |Numero ID per identificare l'URI dell'organizzatore della conferenza. Per ulteriori informazioni, vedere la [tabella users](users.md) . <br/> |
|**Bandiera** <br/> |smallint  <br/> || Una maschera di bit che contiene gli attributi di conferenza. I valori possibili sono: <br/>  0X01 <br/>  Sintetico <br/>  Transazione <br/> |
|**Elaborati** <br/> |po'  <br/> ||Campo interno utilizzato dal servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   
\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se due sessioni si avviano esattamente nello stesso momento, l'SessionIdSeq per uno sarà 1 e per l'altro sarà 2 e così via.
  

