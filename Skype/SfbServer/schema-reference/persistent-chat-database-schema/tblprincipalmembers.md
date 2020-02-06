---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene le appartenenze principali.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813944"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers contiene le appartenenze principali.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|memberADPath  <br/> |nvarchar (384), not null  <br/> |Nome distinto di un membro. Un membro non deve essere un oggetto Principal (nella tabella tblPrincipal).  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca in tblPrincipal. prinID.  <br/> |
   

