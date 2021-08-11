---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene le modifiche di Servizi di dominio Active Directory non ancora elaborate dai passaggi successivi di sincronizzazione di Active Directory.
ms.openlocfilehash: 992834e0086df6ecbc0b8b1cf13a2feaca53cd6ed3f80b6a076abef31e362a6b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329430"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contiene le modifiche di Servizi di dominio Active Directory non ancora elaborate dai passaggi successivi di sincronizzazione di Active Directory.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |GUID di entità dell'oggetto modificato.  <br/> |
|prinADPath  <br/> |nvarchar (384), not null  <br/> |Nome distinto dell'oggetto.  <br/> |
|prinAttributesChanged  <br/> |bit, not null  <br/> |True se viene modificato almeno un attributo dell'oggetto.  <br/> |
|prinMembersChanged  <br/> |bit, not null  <br/> |True se l'appartenenza è stata modificata.  <br/> |
|prinAffiliationsChanged  <br/> |bit, not null  <br/> |Non utilizzata.  <br/> |
|prinDeleted  <br/> |bit, not null  <br/> |True se l'oggetto è stato modificato.  <br/> |
|lastUpdated  <br/> |datetime, not null  <br/> |Timestamp dell'inserimento della riga.  <br/> |
   

