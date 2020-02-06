---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene un server di chat persistente che non supporta la configurazione, in una riga.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814624"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig contiene un server di chat persistente che non supporta la configurazione, in una riga.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), not null  <br/> |Contiene "pool".  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Contenuto della configurazione.  <br/> |
|configPoolID  <br/> |GUID, non null  <br/> |ID univoco dell'istanza del database.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|configLabel  <br/> |Chiave primaria.  <br/> |
   

