---
title: tblConfig
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene alcune configurazioni non supportate del server Chat persistente, in una riga.
ms.openlocfilehash: 344922f4ffb1cf172c154117c95491558f8e8905
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767364"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contiene alcune configurazioni non supportate del server Chat persistente, in una riga.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), non null  <br/> |Contiene "pool."  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Contenuto della configurazione.  <br/> |
|configPoolID  <br/> |GUID, not null  <br/> |ID univoco dell'istanza di database.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|configLabel  <br/> |Chiave primaria.  <br/> |
   

