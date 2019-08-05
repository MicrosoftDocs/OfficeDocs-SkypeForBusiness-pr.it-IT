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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene le preferenze client degli utenti. Questa operazione viene in genere usata dai client precedenti a Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194675"
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


