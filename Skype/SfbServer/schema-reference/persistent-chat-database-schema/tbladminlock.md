---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene il blocco di amministratore necessario per eseguire alcuni comandi di amministratore.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814694"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contiene il blocco di amministratore necessario per eseguire alcuni comandi di amministratore.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, not null  <br/> |Bloccare la data e l'ora di scadenza. Il proprietario può estendere questo valore periodicamente.  <br/> |
|lockServerID  <br/> |int, not null  <br/> |ID del server che possiede il blocco.  <br/> |
|lockActorID  <br/> |int, not null  <br/> |ID dell'entità che possiede il blocco.  <br/> |
   

