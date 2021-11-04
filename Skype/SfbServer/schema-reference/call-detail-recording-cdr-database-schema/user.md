---
title: Visualizzazione utente
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 6508bac1b40ca88429cc0504982ed9d2464ee5d2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777736"
---
# <a name="user-view"></a>Visualizzazione utente
 
Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Numero univoco che identifica l'utente.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |Uri dell'utente.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Tenant dell'utente. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo dell'URI dell'utente. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
   

