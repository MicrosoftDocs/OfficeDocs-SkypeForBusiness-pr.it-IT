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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194661"
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
   

