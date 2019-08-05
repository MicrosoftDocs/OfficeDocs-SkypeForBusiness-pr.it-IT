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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene il blocco di amministratore necessario per eseguire alcuni comandi di amministratore.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194702"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contiene il blocco di amministratore necessario per eseguire alcuni comandi di amministratore.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, not null  <br/> |Bloccare la data e l'ora di scadenza. Il proprietario può estendere questo valore periodicamente.  <br/> |
|lockServerID  <br/> |int, not null  <br/> |ID del server che possiede il blocco.  <br/> |
|lockActorID  <br/> |int, not null  <br/> |ID dell'entità che possiede il blocco.  <br/> |
   

