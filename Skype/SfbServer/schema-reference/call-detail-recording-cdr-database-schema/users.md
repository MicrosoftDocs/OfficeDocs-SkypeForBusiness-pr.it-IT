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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabella utenti è una tabella di supporto. Ogni record nella tabella archivia le informazioni relative a un utente coinvolto in chiamate o sessioni che includono record nel database.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814804"
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
   

