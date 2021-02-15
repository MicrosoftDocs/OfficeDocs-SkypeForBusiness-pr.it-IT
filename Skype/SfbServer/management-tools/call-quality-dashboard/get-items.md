---
title: Get Items
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: "Riepilogo: informazioni sull'operazione Get Items, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832536"
---
# <a name="get-items"></a>Get Items
 
**Riepilogo:** Informazioni sull'operazione Get Items, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Items fa parte di Item Service nell'API repository per call quality dashboard.
  
## <a name="get-items"></a>Get Items

Il metodo Get Items restituisce tutti gli elementi nel repository.
  
|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni risposta** - Nessuna intestazione aggiuntiva.
  
 **Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.
  
> [!NOTE]
> Viene restituita una matrice di oggetti Item. Per informazioni dettagliate sull'oggetto Item, vedere Get Item. 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
