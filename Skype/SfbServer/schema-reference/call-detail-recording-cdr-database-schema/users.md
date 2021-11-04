---
title: Tabella Utenti
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabella Users è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un utente coinvolto in chiamate o sessioni con record nel database.
ms.openlocfilehash: 7f3fb7fc015da4f96ab458a4ad40ccd1b2addbee
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741912"
---
# <a name="users-table"></a>Tabella Utenti
 
La tabella Users è una tabella di supporto. In ogni record della tabella sono archiviate informazioni su un utente coinvolto in chiamate o sessioni con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Timestamp per uso interno.  <br/> |
|**UserId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica l'utente.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI dell'utente.  <br/> |
|**TenantId** <br/> |int  <br/> |Foreign  <br/> |ID tenant dell'utente. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Tipo DI URI dell'utente. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
   

