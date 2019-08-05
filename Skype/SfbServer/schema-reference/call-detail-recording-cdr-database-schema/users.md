---
title: Tabella Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabella utenti è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un utente coinvolto in chiamate o sessioni che includono record nel database.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194725"
---
# <a name="users-table"></a>Tabella Users
 
La tabella utenti è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un utente coinvolto in chiamate o sessioni che includono record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |DateTime  <br/> ||Indicatore di data e ora per uso interno.  <br/> |
|**UserId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo utente.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |URI utente.  <br/> |
|**ID tenant** <br/> |int  <br/> |Esterna  <br/> |ID tenant di questo utente. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**UriTypeId** <br/> |int  <br/> |Esterna  <br/> |Tipo di URI di questo utente. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
   

