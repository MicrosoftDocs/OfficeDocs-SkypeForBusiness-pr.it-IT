---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.
---

# <a name="tbladminlock"></a>tblAdminLock
 
La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, non null  <br/> |Data e ora di scadenza del blocco. Il proprietario può estendere questo valore periodicamente.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID del server proprietario del blocco.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID dell'entità proprietaria del blocco.  <br/> |
   

