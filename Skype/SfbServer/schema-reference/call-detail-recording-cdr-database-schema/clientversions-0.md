---
title: Visualizzazione ClientVersions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La Visualizzazione ClientVersions archivia le informazioni sui diversi tipi e versioni di client che hanno partecipato alle sessioni registrate nel database. Ogni record della visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194845"
---
# <a name="clientversions-view"></a>Visualizzazione ClientVersions
 
La Visualizzazione ClientVersions archivia le informazioni sui diversi tipi e versioni di client che hanno partecipato alle sessioni registrate nel database. Ogni record della visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> Per alcune colonne possono essere presenti più record. 
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Numero univoco che identifica questo tipo di client e la versione.  <br/> |
|**Versione** <br/> |nvarchar (256)  <br/> |Rappresenta l'agente utente.  <br/> |
|**TipoClient** <br/> |int  <br/> |Tipo di client.  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Categoria a cui appartiene il client. Ad esempio, il client Conferencing_Attendant_ 1.0 appartiene alla ClientCategory CAA.  <br/> |
   

