---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene modifiche all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione di Servizi di dominio Active Directory.
ms.openlocfilehash: 884f1450b74300ad2915c27b524dc0419c97062d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743162"
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
   

