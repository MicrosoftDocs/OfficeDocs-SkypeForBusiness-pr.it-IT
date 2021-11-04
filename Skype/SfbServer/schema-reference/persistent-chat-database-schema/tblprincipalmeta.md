---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene le entità che devono essere aggiornate da Servizi di dominio Active Directory.
ms.openlocfilehash: c5e8a4464b025b2e1d1b5775ca139b76a95ce633
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756185"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta contiene le entità che devono essere aggiornate da Servizi di dominio Active Directory.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|prinAffiliationsDirty  <br/> |bit, non null  <br/> |True se le affiliazioni delle entità devono essere aggiornate.  <br/> |
|prinAttributesDirty  <br/> |bit, non null  <br/> |True se gli attributi delle entità devono essere aggiornati.  <br/> |
|prinDeleted  <br/> |bit, non null  <br/> |True se l'entità è stata eliminata.  <br/> |
|tryCount  <br/> |int  <br/> |Numero di tentativi di aggiornamento dell'entità eseguiti fino a questo momento da Servizi di dominio Active Directory.  <br/> |
|lastTry  <br/> |datetime  <br/> |Indicatore di data e ora del tentativo più recente di aggiornamento dell'entità. Può essere Null se non è ancora stato eseguito alcun tentativo di aggiornamento.  <br/> |
|nextTry  <br/> |datetime  <br/> |Indicatore di data e ora del successivo aggiornamento pianificato. Può essere Null se non sono stati pianificati ulteriori aggiornamenti.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|prinID  <br/> |Chiave primaria.  <br/> |
|prinID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipal.prinID.  <br/> |
   

