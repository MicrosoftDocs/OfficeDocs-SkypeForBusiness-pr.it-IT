---
title: Visualizzazione ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Nella visualizzazione ClientVersions vengono archiviate informazioni sui vari tipi di client e versioni che hanno partecipato a sessioni registrate nel database. Ogni record nella visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
---

# <a name="clientversions-view"></a>Visualizzazione ClientVersions
 
Nella visualizzazione ClientVersions vengono archiviate informazioni sui vari tipi di client e versioni che hanno partecipato a sessioni registrate nel database. Ogni record nella visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> Possono essere presenti più record per determinate colonne. 
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Numero univoco che identifica il tipo di client e la versione.  <br/> |
|**Versione** <br/> |nvarchar(256)  <br/> |Rappresenta l'agente utente.  <br/> |
|**ClientType** <br/> |int  <br/> |Tipo di client.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoria a cui appartiene il client. Ad esempio, il client Conferencing_Attendant_1.0 appartiene all'autorità di certificazione ClientCategory.  <br/> |
   

