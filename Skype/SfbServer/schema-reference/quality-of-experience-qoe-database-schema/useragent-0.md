---
title: Visualizzazione UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La visualizzazione UserAgent archivia le informazioni sugli agenti utente coinvolti nelle sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805084"
---
# <a name="useragent-view"></a>Visualizzazione UserAgent
 
La visualizzazione UserAgent archivia le informazioni sugli agenti utente coinvolti nelle sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Numero univoco che identifica questo agente utente.  <br/> |
|UserAgent  <br/> |nvarchar (256)  <br/> |Stringa agente utente.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo di agente utente. Per altri dettagli, vedere la [tabella UserAgent](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Categoria a cui appartiene l'agente utente. Ad esempio, l'agente utente Conferencing_Attendant_1 .0 appartiene alla UACategory CAA.  <br/> |
   

