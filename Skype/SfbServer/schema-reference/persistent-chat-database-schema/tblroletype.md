---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType è una tabella di ricerca statica con i tipi di ruoli e i relativi set di autorizzazioni associati.
ms.openlocfilehash: 9771d18dda2f10b1e75aa3ea4058f60ed2b5cc76
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844049"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType è una tabella di ricerca statica con i tipi di ruoli e i relativi set di autorizzazioni associati.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, not null  <br/> |ID del tipo di ruolo.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), not null  <br/> | Descrizione del tipo di ruolo. Sono disponibili quattro ruoli: <br/>  Member: membro della chat. <br/>  Manager: responsabile della chat. <br/>  Voiced: relatore per una chat. auditorium <br/>  Creator: creazione di chat room <br/> |
|rtypeAllowedPermSet  <br/> |bigint, not null  <br/> | Set di autorizzazioni per il ruolo. I bit utilizzati sono: <br/>  2: true se il ruolo può gestire i nodi. <br/>  4: true se il ruolo può creare nodi figlio. <br/>  7: true se il ruolo può partecipare a una chat (o a chat figlio di una categoria). <br/>  8: true se il ruolo può eseguire chat in una chat (o in chat figlio di una categoria). <br/>  10: true se il ruolo può leggere la cronologia delle chat anche se non partecipa a una chat. <br/>  11: true se il ruolo può visualizzare la chat (ulteriormente definito da fattori come l'ambito e la visibilità). <br/>  12: true se il ruolo può eseguire chat in una chat auditorium. <br/>  13: true se il ruolo può ignorare le regole di visibilità quando visualizza i nodi. <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|rtypeID  <br/> |Chiave primaria.  <br/> |
   

