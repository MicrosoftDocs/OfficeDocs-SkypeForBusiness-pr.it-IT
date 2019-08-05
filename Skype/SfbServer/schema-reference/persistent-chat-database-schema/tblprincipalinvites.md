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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene gli inviti per tutti gli utenti con provisioning per tutti i nodi con l'invito automatico attivato.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194669"
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
   

