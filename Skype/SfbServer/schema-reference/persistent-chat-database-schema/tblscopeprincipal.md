---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene gli ambiti assegnati ai nodi.
ms.openlocfilehash: 4f2bcb7734badde8f734c30f074ba6dda82cc7eb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745712"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contiene gli ambiti assegnati ai nodi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, not null  <br/> |ID di nodo a cui si applica l'ambito.  <br/> |
|scopePrinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|scopeIsDenied  <br/> |bit, not null  <br/> |True se il tipo di ambito è Deny; False se è Allow.  <br/> |
|scopeUpdatedBy  <br/> |int, not null  <br/> |ID dell'ultima entità che ha aggiornato questa voce.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Chiave primaria.  <br/> |
|scopeNodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
   

