---
title: Tabella ConferenceMessageCount in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194837"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabella ConferenceMessageCount in Skype for Business Server 2015
 
Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora dell'istanza di conferenza. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare l'istanza di conferenza. Usato in combinazione con **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**UserId** <br/> |int  <br/> |Esterna  <br/> |Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella utenti](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Numero di messaggi inviati dall'utente durante questa conferenza.  <br/> |
   

