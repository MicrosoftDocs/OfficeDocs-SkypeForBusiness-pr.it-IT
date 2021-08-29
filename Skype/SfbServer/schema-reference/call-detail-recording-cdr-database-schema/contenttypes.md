---
title: Tabella ContentTypes in Skype for Business Server 2015
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
ms.localizationpriority: medium
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto utilizzati sia nelle sessioni peer-to-peer che nelle sessioni di conferenze. Ogni record della tabella rappresenta un tipo di contenuto.
ms.openlocfilehash: 04c28a39d95ac9c2252f6c2f400649d3d74ef654
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627788"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Tabella ContentTypes in Skype for Business Server 2015
 
La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto utilizzati sia nelle sessioni peer-to-peer che nelle sessioni di conferenze. Ogni record della tabella rappresenta un tipo di contenuto.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il tipo di contenuto.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Nome del tipo di contenuto.  <br/> |
   

