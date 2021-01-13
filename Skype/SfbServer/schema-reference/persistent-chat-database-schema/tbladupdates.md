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
description: tblADUpdates contiene le modifiche ai servizi di dominio Active Directory che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory.
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821386"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contiene le modifiche ai servizi di dominio Active Directory che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory.
  
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
   

