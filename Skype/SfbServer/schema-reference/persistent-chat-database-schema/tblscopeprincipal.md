---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene gli ambiti assegnati ai nodi.
ms.openlocfilehash: e86b259126ee58c26246e78e1afd44a5e5122cbdbaaabb7f0967bb2bba7e5d39
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337594"
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
   

