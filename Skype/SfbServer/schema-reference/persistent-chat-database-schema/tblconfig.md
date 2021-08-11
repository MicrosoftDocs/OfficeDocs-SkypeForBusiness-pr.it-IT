---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene alcune configurazioni non supportate del server Chat persistente, in una riga.
ms.openlocfilehash: 0e9cc0a0c4686432032591aa0c380b303fc5251a56a6c983a1e10b009e0eb28a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278354"
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
   

