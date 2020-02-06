---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene gli ambiti assegnati ai nodi.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812444"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contiene gli ambiti assegnati ai nodi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, not null  <br/> |ID nodo a cui si applica l'ambito.  <br/> |
|scopePrinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|scopeIsDenied  <br/> |bit, not null  <br/> |True se il tipo di ambito è Deny; False se Consenti.  <br/> |
|scopeUpdatedBy  <br/> |int, not null  <br/> |ID dell'entità che ha aggiornato l'ultima voce.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Chiave primaria.  <br/> |
|scopeNodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode. nodeID.  <br/> |
|scopePrinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal. prinID.  <br/> |
   

