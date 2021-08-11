---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene le entità che devono essere aggiornate da Servizi di dominio Active Directory.
ms.openlocfilehash: a2cc7ef5313be8abdf50c6cebc5bb8999bf153eeeba0a188cd2d34d2c4608546
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289424"
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
   

