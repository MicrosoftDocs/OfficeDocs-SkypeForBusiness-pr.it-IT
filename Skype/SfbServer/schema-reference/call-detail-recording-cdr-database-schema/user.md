---
title: Visualizzazione utente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
---

# <a name="user-view"></a>Visualizzazione utente
 
Nella Visualizzazione utente sono archiviate le informazioni relative agli utenti che hanno partecipato a chiamate o sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Numero univoco che identifica l'utente.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |Uri dell'utente.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Tenant dell'utente. Per ulteriori [informazioni, vedere la tabella Tenants](tenants.md) . <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo dell'URI dell'utente. Per ulteriori [informazioni, vedere la tabella UriTypes](uritypes.md) . <br/> |
   

