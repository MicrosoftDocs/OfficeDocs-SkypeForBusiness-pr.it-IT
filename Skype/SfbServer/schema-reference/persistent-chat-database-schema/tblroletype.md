---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType è una tabella di ricerca statica con i tipi di ruolo e i set di autorizzazioni associati.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812904"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType è una tabella di ricerca statica con i tipi di ruolo e i set di autorizzazioni associati.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, not null  <br/> |ID tipo di ruolo.  <br/> |
|rtypeDesc  <br/> |nvarchar (256), not null  <br/> | Descrizione del tipo di ruolo. Esistono quattro ruoli disponibili: <br/>  Membro: membro della chat room <br/>  Manager: gestione chat room <br/>  Voiced: relatore per una chat room dell'Auditorium <br/>  Creatore: può creare chat room <br/> |
|rtypeAllowedPermSet  <br/> |bigint e non null  <br/> | Set di autorizzazioni per il ruolo. I bit usati sono: <br/>  2: true se il ruolo può gestire i nodi. <br/>  4: true se il ruolo può creare nodi figlio. <br/>  7: vero se il ruolo può partecipare a una chat room (o chat room per bambini di una categoria). <br/>  8: true se il ruolo può essere chattato in una chat room o in chat per bambini di una categoria. <br/>  10: true se il ruolo può leggere la cronologia chat anche quando non è stato aggiunto a una chat room. <br/>  11: vero se il ruolo può vedere la chat room. (Questa operazione viene ulteriormente affinata da fattori come l'ambito e la visibilità). <br/>  12: vero se il ruolo può chattare in una chat room di un auditorium. <br/>  13: true se il ruolo può ignorare le regole di visibilità durante la visualizzazione dei nodi. <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|rtypeID  <br/> |Chiave primaria.  <br/> |
   

