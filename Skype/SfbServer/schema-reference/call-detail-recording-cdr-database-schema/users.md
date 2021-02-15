---
title: Tabella Users
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabella Users è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un utente coinvolto in chiamate o sessioni con record nel database.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831616"
---
# <a name="users-table"></a>Tabella Users
 
La tabella Users è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un utente coinvolto in chiamate o sessioni con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Timestamp per uso interno.  <br/> |
|**UserId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'utente.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI dell'utente.  <br/> |
|**TenantId** <br/> |int  <br/> |Esterna  <br/> |ID tenant dell'utente. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**UriTypeId** <br/> |int  <br/> |Esterna  <br/> |Tipo di URI dell'utente. Per altre [informazioni, vedi la tabella UriTypes.](uritypes.md) <br/> |
   

