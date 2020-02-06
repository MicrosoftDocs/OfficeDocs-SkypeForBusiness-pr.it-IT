---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814684"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principale dell'oggetto modificato.  <br/> |
|prinADPath  <br/> |nvarchar (384), not null  <br/> |Nome distinto dell'oggetto.  <br/> |
|prinAttributesChanged  <br/> |bit, not null  <br/> |True se almeno un attributo dell'oggetto è cambiato.  <br/> |
|prinMembersChanged  <br/> |bit, not null  <br/> |True se l'appartenenza è cambiata.  <br/> |
|prinAffiliationsChanged  <br/> |bit, not null  <br/> |Non usato.  <br/> |
|prinDeleted  <br/> |bit, not null  <br/> |True se l'oggetto è stato eliminato.  <br/> |
|lastUpdated  <br/> |DateTime, not null  <br/> |Indicatore di data e ora di quando è stata inserita la riga.  <br/> |
   

