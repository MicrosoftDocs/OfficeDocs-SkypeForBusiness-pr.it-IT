---
title: Tabella ErrorCategory in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabella ErrorCategory contiene il nome descrittivo per ogni Skype for Business Server diagnostica 2015. Per impostazione predefinita, Skype for Business Server 2015 usa le classificazioni seguenti:'
---

# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Tabella ErrorCategory in Skype for Business Server 2015
 
La tabella ErrorCategory contiene il nome descrittivo per ogni Skype for Business Server diagnostica 2015. Per impostazione predefinita, Skype for Business Server 2015 usa le classificazioni seguenti:
  
- 0 -- Esito positivo
    
- 1 - Errore previsto
    
- 2 - Errore imprevisto
    
Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Principale  <br/> |Identificatore univoco della classificazione.  <br/> |
|**Nome** <br/> |nvarchar(256)  <br/> || Valore e nome descrittivo assegnati alla classificazione. I valori consentiti sono: <br/>  0 -- Esito positivo <br/>  1 - Errore previsto <br/>  2 - Errore imprevisto <br/> |
   

