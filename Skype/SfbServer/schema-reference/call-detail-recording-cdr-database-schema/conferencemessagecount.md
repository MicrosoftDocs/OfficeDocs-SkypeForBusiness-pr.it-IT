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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
ms.openlocfilehash: 66651f798d627ef4ea783c4ecf4e7cb8f1adab81
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815374"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Tabella ConferenceMessageCount in Skype for Business Server 2015
 
Ogni record in questa tabella rappresenta un utente in una conferenza di messaggistica istantanea e include il numero di messaggi inviati dall'utente. Ogni conferenza è rappresentata da più record in questa tabella. un record per ogni utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora dell'istanza di conferenza. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare l'istanza di conferenza. Usato in combinazione con **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**UserId** <br/> |int  <br/> |Esterna  <br/> |Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella utenti](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Numero di messaggi inviati dall'utente durante questa conferenza.  <br/> |
   

