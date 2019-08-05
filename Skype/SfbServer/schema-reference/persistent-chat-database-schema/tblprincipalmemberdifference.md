---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contiene le modifiche dell'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione dei servizi di dominio Active Directory.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194668"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference contiene le modifiche dell'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione dei servizi di dominio Active Directory.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principale del gruppo modificato.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Nome distinto del membro.  <br/> |
|memberRemoved  <br/> |bit, not null  <br/> |False se il membro è stato aggiunto. True se il membro è stato rimosso.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Chiave primaria.  <br/> |
   

