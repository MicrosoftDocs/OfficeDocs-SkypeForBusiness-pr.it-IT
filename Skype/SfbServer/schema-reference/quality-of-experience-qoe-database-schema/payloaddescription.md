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
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: La tabella PayloadDescription è una tabella di supporto. Ogni record rappresenta un codec, che viene utilizzato in una sessione audio o video.
ms.openlocfilehash: c9476aea28993a053096a095469d2d4e13251581
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806296"
---
# <a name="payloaddescription-table"></a>Tabella PayloadDescription
 
La tabella PayloadDescription è una tabella di supporto. Ogni record rappresenta un codec, che viene utilizzato in una sessione audio o video.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Nome del codec.  <br/> |
   

