---
title: Tabella CodecDescription
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabella CodecDescription associa identificatori codec univoci al codec corrispondente. I codec vengono usati per codificare i segnali digitali per la trasmissione, quindi per decodificare tali segnali per la riproduzione. Questa tabella è stata introdotta in Microsoft Lync Server 2013
ms.openlocfilehash: 0f5601847458f7ce59e0cd691b573ec77605b667
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763244"
---
# <a name="codecdescription-table"></a>Tabella CodecDescription
 
La tabella CodecDescription associa identificatori codec univoci al codec corrispondente. I codec vengono usati per codificare i segnali digitali per la trasmissione, quindi per decodificare tali segnali per la riproduzione. Questa tabella è stata introdotta in Microsoft Lync Server 2013
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Principale  <br/> |Identificatore univoco assegnato al codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Univoco  <br/> |Descrizione univoca del codec corrispondente a CodecDescriptionKey.  <br/> |
   

