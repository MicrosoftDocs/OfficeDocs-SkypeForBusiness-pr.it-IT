---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene gli inviti per tutti gli utenti con provisioning per tutti i nodi con l'invito automatico attivato.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814184"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contiene gli inviti per tutti gli utenti con provisioning per tutti i nodi con l'invito automatico attivato.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|invID  <br/> |int, not null  <br/> |Numero sequenziale univoco (per ID entità) generato dalla tabella tblLastInviteId.  <br/> |
|nodeID  <br/> |int, not null  <br/> |ID nodo (solo chat room).  <br/> |
|createdOn  <br/> |DateTime, not null  <br/> |Ora della creazione.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal. prinID.  <br/> |
|nodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode. nodeID.  <br/> |
   

