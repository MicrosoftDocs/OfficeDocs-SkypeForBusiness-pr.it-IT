---
title: Tabella PayloadDescription
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
ms.localizationpriority: medium
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: La tabella PayloadDescription è una tabella di supporto. Ogni record rappresenta un codec, che viene utilizzato in una sessione audio o video.
ms.openlocfilehash: dedbf806c6cda1ce174e1a3282b81a409b63bced
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610563"
---
# <a name="payloaddescription-table"></a>Tabella PayloadDescription
 
La tabella PayloadDescription è una tabella di supporto. Ogni record rappresenta un codec, che viene utilizzato in una sessione audio o video.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Nome del codec.  <br/> |
   

