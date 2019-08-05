---
title: Tabella ContentTypes in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto usati nelle sessioni peer-to-peer e nelle sessioni di conferenza. Ogni record nella tabella rappresenta un tipo di contenuto.
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194822"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tabella ContentTypes in Skype for Business Server 2015
 
La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto usati nelle sessioni peer-to-peer e nelle sessioni di conferenza. Ogni record nella tabella rappresenta un tipo di contenuto.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il tipo di contenuto.  <br/> |
|**ContentType** <br/> |nvarchar (256)  <br/> ||Nome tipo di contenuto.  <br/> |
   

