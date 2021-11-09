---
title: tblPreference
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene le preferenze client degli utenti. Questo viene in genere utilizzato dai client precedenti a Lync 2013.
ms.openlocfilehash: 8c719ba33196e32d48f045c07ea89ded317ab5ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846189"
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


