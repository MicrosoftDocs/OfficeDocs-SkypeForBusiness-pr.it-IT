---
title: Tabella Utenti
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
ms.openlocfilehash: 09706bf5b519ce85cd52898911ad6b878b6e5056246c47154f370ae8c75cc774
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302240"
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
   

