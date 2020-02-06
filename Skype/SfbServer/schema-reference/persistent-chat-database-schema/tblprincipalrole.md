---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813364"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, not null  <br/> |ID nodo a cui si applica il ruolo.  <br/> |
|prinRolePrinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|prinRoleTypeID  <br/> |int, not null  <br/> |ID tipo di ruolo (da tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, not null  <br/> |ID dell'entità che ha aggiornato l'ultima voce.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Chiave primaria.  <br/> |
|prinRoleNodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode. nodeID.  <br/> |
|prinRolePrinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal. prinID.  <br/> |
|prinRoleTypeID  <br/> |Chiave esterna con ricerca nella tabella tblRoleType. rtypeID.  <br/> |
   

