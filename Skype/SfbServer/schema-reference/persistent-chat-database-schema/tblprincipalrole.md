---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
ms.openlocfilehash: 6c9960c4eafc2d28a4710a8e4dded6bea19c841a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828529"
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
   

