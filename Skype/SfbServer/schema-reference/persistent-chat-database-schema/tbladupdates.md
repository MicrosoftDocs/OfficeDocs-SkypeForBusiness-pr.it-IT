---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194700"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principale dell'oggetto modificato.  <br/> |
|prinADPath  <br/> |nvarchar (384), not null  <br/> |Nome distinto dell'oggetto.  <br/> |
|prinAttributesChanged  <br/> |bit, not null  <br/> |True se almeno un attributo dell'oggetto è cambiato.  <br/> |
|prinMembersChanged  <br/> |bit, not null  <br/> |True se l'appartenenza è cambiata.  <br/> |
|prinAffiliationsChanged  <br/> |bit, not null  <br/> |Non usato.  <br/> |
|prinDeleted  <br/> |bit, not null  <br/> |True se l'oggetto è stato eliminato.  <br/> |
|lastUpdated  <br/> |DateTime, not null  <br/> |Indicatore di data e ora di quando è stata inserita la riga.  <br/> |
   

