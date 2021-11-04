---
title: Tabella ConferenceMessageCount in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati da tale utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
ms.openlocfilehash: 3504a7cb9affbd4c9e26518dbf9d7e404ad9d90e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754409"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabella ConferenceMessageCount in Skype for Business Server 2015
 
Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati da tale utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora dell'istanza di conferenza. Utilizzato insieme a **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la tabella [Conferenze Skype for Business Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare l'istanza di conferenza. Utilizzato insieme a **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la tabella [Conferenze Skype for Business Server 2015.](conferences.md) <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella Utenti](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Numero di messaggi inviati dall'utente durante questa conferenza.  <br/> |
   

