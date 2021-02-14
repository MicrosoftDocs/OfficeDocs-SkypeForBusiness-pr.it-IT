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
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809736"
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
   

