---
title: Tabella ClientVersions in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei diversi tipi di client e delle versioni che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta una versione client.
---

# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Tabella ClientVersions in Skype for Business Server 2015
 
La tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei diversi tipi di client e delle versioni che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta una versione client.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Principale  <br/> |Numero univoco che identifica il tipo di client e la versione.  <br/> |
|**Versione** <br/> |**nvarchar(256)** <br/> ||Nome della versione.  <br/> |
|**ClientType** <br/> |int  <br/> ||Specifica il tipo di client usato nella sessione. Per ulteriori [informazioni, vedere la tabella UserAgentDef](useragentdef.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
   

