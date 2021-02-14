---
title: Tabella ClientVersions in Skype for Business Server 2015
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
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei diversi tipi di client e delle versioni che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta una versione client.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813316"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabella ClientVersions in Skype for Business Server 2015
 
La tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei diversi tipi di client e delle versioni che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta una versione client.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Principale  <br/> |Numero univoco che identifica il tipo di client e la versione.  <br/> |
|**Versione** <br/> |**nvarchar(256)** <br/> ||Nome della versione.  <br/> |
|**ClientType** <br/> |int  <br/> ||Specifica il tipo di client usato nella sessione. Per ulteriori informazioni, vedere la tabella [UserAgentDef.](useragentdef.md) <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

