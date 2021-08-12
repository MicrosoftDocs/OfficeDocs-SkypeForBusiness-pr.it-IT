---
title: Tabella ErrorCategory in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabella ErrorCategory contiene il nome descrittivo per ogni Skype for Business Server di diagnostica 2015. Per impostazione predefinita, Skype for Business Server 2015 usa le classificazioni seguenti:'
ms.openlocfilehash: 68114e96e04ca8e2cb45fbb2b9ba0b3934df4e363700f8a872f05cb1aa0e8a37
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347771"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabella ErrorCategory in Skype for Business Server 2015
 
La tabella ErrorCategory contiene il nome descrittivo per ogni Skype for Business Server di diagnostica 2015. Per impostazione predefinita, Skype for Business Server 2015 usa le classificazioni seguenti:
  
- 0 -- Esito positivo
    
- 1 - Errore previsto
    
- 2 - Errore imprevisto
    
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco della classificazione.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> || Valore e nome descrittivo assegnati alla classificazione. I valori consentiti sono: <br/>  0 -- Esito positivo <br/>  1 - Errore previsto <br/>  2 - Errore imprevisto <br/> |
   

