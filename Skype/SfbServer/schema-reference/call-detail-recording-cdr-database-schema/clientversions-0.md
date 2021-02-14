---
title: Visualizzazione ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Nella visualizzazione ClientVersions vengono archiviate informazioni sui diversi tipi di client e versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813356"
---
# <a name="clientversions-view"></a>Visualizzazione ClientVersions
 
Nella visualizzazione ClientVersions vengono archiviate informazioni sui diversi tipi di client e versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> È possibile che siano presenti più record per determinate colonne. 
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Numero univoco che identifica il tipo di client e la versione.  <br/> |
|**Versione** <br/> |nvarchar(256)  <br/> |Rappresenta l'agente utente.  <br/> |
|**ClientType** <br/> |int  <br/> |Tipo di client.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoria a cui appartiene il client. Ad esempio, il client Conferencing_Attendant_1.0 appartiene alla CAA ClientCategory.  <br/> |
   

