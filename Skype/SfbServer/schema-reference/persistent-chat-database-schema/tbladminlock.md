---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.
ms.openlocfilehash: df040a4a6d503e4ea8f7327e6ac50b5ae411cf60
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746532"
---
# <a name="tbladminlock"></a>tblAdminLock
 
La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, non null  <br/> |Data e ora di scadenza del blocco. Il proprietario può estendere questo valore periodicamente.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID del server proprietario del blocco.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID dell'entità proprietaria del blocco.  <br/> |
   

