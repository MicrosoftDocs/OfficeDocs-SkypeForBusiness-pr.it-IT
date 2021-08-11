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
ms.openlocfilehash: fa90d112ce7b3397f055023034888b45bc5b8bcabc7948f7c4af0bb59788c2d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318689"
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
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode.nodeID.  <br/> |
   

