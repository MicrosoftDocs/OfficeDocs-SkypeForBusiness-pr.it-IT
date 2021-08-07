---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene modifiche all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione di Servizi di dominio Active Directory.
ms.openlocfilehash: c1d5a0d492d228b5a8292fde608fbd66c3b586c393aba8eb5bc0fbbddd45a5e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276581"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contiene modifiche all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione di Servizi di dominio Active Directory.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |GUID entità del gruppo modificato.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nome distinto del membro.  <br/> |
|memberRemoved  <br/> |bit, not null  <br/> |False se il membro è stato aggiunto. True se il membro è stato rimosso.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Chiave primaria.  <br/> |
   

