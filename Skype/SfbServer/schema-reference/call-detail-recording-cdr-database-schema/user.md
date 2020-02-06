---
title: Visualizzazione utente
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La visualizzazione utente archivia le informazioni sugli utenti che hanno partecipato a chiamate o sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814834"
---
# <a name="user-view"></a>Visualizzazione utente
 
La visualizzazione utente archivia le informazioni sugli utenti che hanno partecipato a chiamate o sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Numero univoco che identifica questo utente.  <br/> |
|UserUri  <br/> |nvarchar (450)  <br/> |URI dell'utente.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Tenant dell'utente. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|UriType  <br/> |nvarchar (256)  <br/> |Tipo di URI utente. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
   

