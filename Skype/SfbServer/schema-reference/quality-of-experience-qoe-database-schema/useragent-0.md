---
title: Visualizzazione UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Nella visualizzazione UserAgent vengono archiviate le informazioni relative agli agenti utente coinvolti in sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: d6ed446c429c3e055d3b5387f4675eaed7fb1f9e992d7211346309254549b66d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282988"
---
# <a name="useragent-view"></a>Visualizzazione UserAgent
 
Nella visualizzazione UserAgent vengono archiviate le informazioni relative agli agenti utente coinvolti in sessioni con record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Numero univoco che identifica l'agente utente.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Stringa dell'agente utente.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo di agente utente. Per ulteriori dettagli, vedere la tabella [UserAgent.](useragent.md) <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Categoria a cui appartiene l'agente utente. Ad esempio, l'agente utente Conferencing_Attendant_1.0 appartiene alla categoria (UACategory) CAA.  <br/> |
   

