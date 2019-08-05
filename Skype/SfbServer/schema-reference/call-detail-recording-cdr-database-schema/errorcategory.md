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
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione di diagnostica di Skype for Business Server 2015. Per impostazione predefinita, Skype for Business Server 2015 USA le classificazioni seguenti:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194811"
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
   

