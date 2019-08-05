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
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La visualizzazione UserAgent archivia le informazioni sugli agenti utente coinvolti nelle sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194569"
---
# <a name="useragent-view"></a>Visualizzazione UserAgent
 
La visualizzazione UserAgent archivia le informazioni sugli agenti utente coinvolti nelle sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Numero univoco che identifica questo agente utente.  <br/> |
|UserAgent  <br/> |nvarchar (256)  <br/> |Stringa agente utente.  <br/> |
|UAType  <br/> |smallint  <br/> |Tipo di agente utente. Per altri dettagli, vedere la [tabella UserAgent](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Categoria a cui appartiene l'agente utente. Ad esempio, l'agente utente Conferencing_Attendant_ 1.0 appartiene alla UACategory CAA.  <br/> |
   

