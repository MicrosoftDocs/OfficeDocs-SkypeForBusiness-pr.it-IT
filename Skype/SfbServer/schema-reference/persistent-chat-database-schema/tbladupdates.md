---
title: tblADUpdates
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene le modifiche di Servizi di dominio Active Directory non ancora elaborate dai passaggi successivi di sincronizzazione di Active Directory.
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
   

