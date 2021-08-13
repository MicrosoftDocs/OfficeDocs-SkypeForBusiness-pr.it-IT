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
ms.openlocfilehash: 698976f3f98b939578787a0f8a2c0aeb8167888ad09ea20a09d0d7e4d83e900c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315432"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contiene le preferenze client degli utenti. Questo viene in genere utilizzato dai client precedenti a Lync 2013.

**Colonne**


| **Colonna**            | **Tipo**                        | **Descrizione**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), non null  <br/> | Etichetta con un formato, ad esempio: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, not null  <br/>            | Numero sequenziale (per etichetta) per il controllo delle versioni.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Contenuto codificato.  <br/>                                         |
| lastModifiedBy  <br/> | int, not null  <br/>            | ID dell'entità che ha aggiornato la preferenza.  <br/>         |

**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Chiave primaria.  <br/> |


