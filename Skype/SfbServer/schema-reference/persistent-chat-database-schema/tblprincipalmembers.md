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
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contiene le appartenenze principali.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194662"
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
   

