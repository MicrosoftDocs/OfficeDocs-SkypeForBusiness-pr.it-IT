---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Nella tabella tblPrincipalType sono inclusi i tipi di entità per classificare gli elementi contenuti nella tabella tblPrincipal.
ms.openlocfilehash: cf55ba04afe3688d3ecfd397dc4ffcbe50da2c19
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844069"
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
|1  <br/> |Qualsiasi  <br/> |Entità generica senza tipo conosciuto. Non usata nella tabella tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Entità generica di tipo utente. Non usate nella tabella tblPrincipal.  <br/> |Sì  <br/> |
|3   <br/> |AnyGroup  <br/> |Entità generica con semantica di gruppo. Non usata nella tabella tblPrincipal.  <br/> ||
|4   <br/> |SystemUser  <br/> |Entità utilizzata internamente dal server Chat persistente.  <br/> ||
|5  <br/> |User  <br/> |Utente normale.  <br/> |Sì  <br/> |
|8   <br/> |DC  <br/> |Controller di dominio Servizi di dominio Active Directory.  <br/> ||
|9   <br/> |Gruppo  <br/> |Gruppo di sicurezza di Active Directory.  <br/> ||
|10   <br/> |Cartella  <br/> |Contenitore o unità organizzativa di Active Directory.  <br/> ||
   
## <a name="see-also"></a>Vedere anche

[tblPrincipal](tblprincipal.md)
