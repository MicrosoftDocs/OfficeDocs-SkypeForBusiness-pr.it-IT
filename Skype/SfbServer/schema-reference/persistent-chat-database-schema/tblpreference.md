---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene le preferenze client degli utenti. Questa operazione viene in genere usata dai client precedenti a Lync 2013.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814554"
---
# <a name="tblpreference"></a>tblPreference

tblPreference contiene le preferenze client degli utenti. Questa operazione viene in genere usata dai client precedenti a Lync 2013.

**Colonne**


| **Colonna**            | **Tipo**                        | **Descrizione**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), not null  <br/> | Etichetta con un formato, ad esempio \<: URI SIP utente\>                   |
| prefSeqID  <br/>      | int, not null  <br/>            | Un numero sequenziale (per etichetta) per scopi di controllo delle versioni.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Contenuto codificato.  <br/>                                         |
| lastModifiedBy  <br/> | int, not null  <br/>            | ID dell'entità che ha aggiornato la preferenza.  <br/>         |

**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Chiave primaria.  <br/> |


