---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
ms.openlocfilehash: 28e639a4894b89e449a70fc527b7c4315be57403e15bb582bcdae3933e3790a7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336386"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, not null  <br/> |ID nodo a cui si applica il ruolo.  <br/> |
|prinRolePrinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|prinRoleTypeID  <br/> |int, not null  <br/> |ID del tipo di ruolo (da tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, not null  <br/> |ID dell'ultima entità che ha aggiornato questa voce.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Chiave primaria.  <br/> |
|prinRoleNodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Chiave esterna con ricerca nella tabella tblRoleType.rtypeID.  <br/> |
   

