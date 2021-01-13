---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Nella tabella tblPrincipalType sono inclusi i tipi di entità per classificare gli elementi contenuti nella tabella tblPrincipal.
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831536"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
Nella tabella tblPrincipalType sono inclusi i tipi di entità per classificare gli elementi contenuti nella tabella tblPrincipal.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, not null  <br/> |ID del tipo di entità.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), not null  <br/> |Descrizione del tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bit, not null  <br/> |True se il tipo corrisponde alle entità usate per scopi interni.  <br/> |
|ptypeIsUser  <br/> |bit, not null  <br/> |True se il tipo è un tipo utente.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|ptypeID  <br/> |Chiave primaria.  <br/> |
   
**Valori principali**

|**ID**|**Ruolo**|**Descrizione**|**Utente**|
|:-----|:-----|:-----|:-----|
|1   <br/> |Qualsiasi  <br/> |Entità generica senza tipo conosciuto. Non usata nella tabella tblPrincipal.  <br/> ||
|2   <br/> |AnyUser  <br/> |Entità generica di tipo utente. Non usate nella tabella tblPrincipal.  <br/> |Sì  <br/> |
|3   <br/> |AnyGroup  <br/> |Entità generica con semantica di gruppo. Non usata nella tabella tblPrincipal.  <br/> ||
|4   <br/> |SystemUser  <br/> |Entità utilizzata internamente dal server Chat persistente.  <br/> ||
|5   <br/> |Utente  <br/> |Utente normale.  <br/> |Sì  <br/> |
|8   <br/> |DC  <br/> |Controller di dominio di servizi di dominio Active Directory.  <br/> ||
|9   <br/> |Gruppo  <br/> |Gruppo di sicurezza di Active Directory.  <br/> ||
|10   <br/> |Cartella  <br/> |Contenitore o unità organizzativa di Active Directory.  <br/> ||
   
## <a name="see-also"></a>Vedere anche

[tblPrincipal](tblprincipal.md)
