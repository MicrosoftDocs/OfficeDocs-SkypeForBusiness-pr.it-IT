---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene le preferenze client degli utenti. Questo viene in genere utilizzato dai client precedenti a Lync 2013.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815906"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contiene le preferenze client degli utenti. Questo viene in genere utilizzato dai client precedenti a Lync 2013.

**Colonne**


| **Colonna**            | **Tipo**                        | **Descrizione**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), non null  <br/> | Etichetta con un formato, ad esempio: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, not null  <br/>            | Numero sequenziale (per etichetta) ai fini del controllo delle versioni.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Contenuto codificato.  <br/>                                         |
| lastModifiedBy  <br/> | int, not null  <br/>            | ID dell'entità che ha aggiornato la preferenza.  <br/>         |

**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Chiave primaria.  <br/> |


