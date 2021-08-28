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
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene alcune configurazioni non supportate del server Chat persistente, in una riga.
ms.openlocfilehash: 8cf1fc53087d3fc786ac47e848a21dbd2a8f5549
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595308"
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
   

