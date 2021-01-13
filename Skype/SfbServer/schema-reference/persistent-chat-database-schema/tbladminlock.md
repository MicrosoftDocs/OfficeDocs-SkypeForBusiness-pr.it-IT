---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809886"
---
# <a name="tbladminlock"></a>tblAdminLock
 
La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, non null  <br/> |Data e ora di scadenza del blocco. Il proprietario può estendere questo valore periodicamente.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID del server proprietario del blocco.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID dell'entità proprietaria del blocco.  <br/> |
   

