---
title: Visualizzazione utente
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
ms.localizationpriority: medium
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 59b7371336ec900d6474016bb366407d4ffb7c14
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616382"
---
# <a name="user-view"></a>Visualizzazione utente
 
Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Numero univoco che identifica l'utente.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |Uri dell'utente.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Tenant dell'utente. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo dell'URI dell'utente. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
   

