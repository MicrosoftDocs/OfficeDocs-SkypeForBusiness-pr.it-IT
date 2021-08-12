---
title: Tabella CodecDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabella CodecDescription associa identificatori codec univoci al codec corrispondente. I codec vengono usati per codificare i segnali digitali per la trasmissione, quindi per decodificare tali segnali per la riproduzione. Questa tabella è stata introdotta in Microsoft Lync Server 2013
ms.openlocfilehash: 9facaa9ddf29024a731f9e199b5cf749d91bc6671c320ded510d693755640f38
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309175"
---
# <a name="codecdescription-table"></a>Tabella CodecDescription
 
La tabella CodecDescription associa identificatori codec univoci al codec corrispondente. I codec vengono usati per codificare i segnali digitali per la trasmissione, quindi per decodificare tali segnali per la riproduzione. Questa tabella è stata introdotta in Microsoft Lync Server 2013
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Principale  <br/> |Identificatore univoco assegnato al codec.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Univoco  <br/> |Descrizione univoca del codec corrispondente a CodecDescriptionKey.  <br/> |
   

