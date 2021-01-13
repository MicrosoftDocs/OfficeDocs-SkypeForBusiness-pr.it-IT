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
description: 'La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione diagnostica di Skype for Business Server 2015. Per impostazione predefinita, Skype for Business Server 2015 utilizza le classificazioni seguenti:'
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813146"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabella ErrorCategory in Skype for Business Server 2015
 
La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione diagnostica di Skype for Business Server 2015. Per impostazione predefinita, Skype for Business Server 2015 utilizza le classificazioni seguenti:
  
- 0 -- Esito positivo
    
- 1--errore previsto
    
- 2-errore imprevisto
    
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco della classificazione.  <br/> |
|**Nome** <br/> |nvarchar (256)  <br/> || Valore e nome descrittivo assegnati alla classificazione. I valori consentiti sono: <br/>  0 -- Esito positivo <br/>  1--errore previsto <br/>  2-errore imprevisto <br/> |
   

