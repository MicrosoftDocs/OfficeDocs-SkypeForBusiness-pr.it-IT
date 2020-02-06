---
title: Tabella ErrorCategory in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione di diagnostica di Skype for Business Server 2015. Per impostazione predefinita, Skype for Business Server 2015 USA le classificazioni seguenti:'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815254"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabella ErrorCategory in Skype for Business Server 2015
 
La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione di diagnostica di Skype for Business Server 2015. Per impostazione predefinita, Skype for Business Server 2015 USA le classificazioni seguenti:
  
- 0--successo
    
- 1-errore previsto
    
- 2-errore imprevisto
    
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco per la classificazione.  <br/> |
|**Nome** <br/> |nvarchar (256)  <br/> || Valore e nome descrittivo assegnato alla classificazione. I valori consentiti sono: <br/>  0--successo <br/>  1-errore previsto <br/>  2-errore imprevisto <br/> |
   

