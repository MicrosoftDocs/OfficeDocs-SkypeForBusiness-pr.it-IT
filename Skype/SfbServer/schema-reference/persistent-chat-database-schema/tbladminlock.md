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
ms.openlocfilehash: ad3b2543e2715462b953c611c8b5f24ea7885a6cb910931aa5b832b8196856eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351945"
---
# <a name="tbladminlock"></a>tblAdminLock
 
La tabella AdminLock contiene il blocco dell'amministratore necessario per eseguire alcuni comandi di amministrazione.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, non null  <br/> |Data e ora di scadenza del blocco. Il proprietario può estendere questo valore periodicamente.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID del server proprietario del blocco.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID dell'entità proprietaria del blocco.  <br/> |
   

