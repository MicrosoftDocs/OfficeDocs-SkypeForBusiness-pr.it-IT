---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: In tblPrincipalInvites sono inclusi gli inviti per tutti gli utenti di cui è stato eseguito il provisioning per tutti i nodi con l'invito automatico attivato.
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815856"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
In tblPrincipalInvites sono inclusi gli inviti per tutti gli utenti di cui è stato eseguito il provisioning per tutti i nodi con l'invito automatico attivato.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID dell'entità.  <br/> |
|invID  <br/> |int, not null  <br/> |Numero sequenziale univoco (per ID dell'entità) generato da tblLastInviteId.  <br/> |
|nodeID  <br/> |int, not null  <br/> |ID del nodo (solo chat).  <br/> |
|createdOn  <br/> |datetime, not null  <br/> |Data e ora di creazione.  <br/> |
   
**Chiavi**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode.nodeID.  <br/> |
   

