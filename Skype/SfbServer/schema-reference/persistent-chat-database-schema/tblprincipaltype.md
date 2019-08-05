---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194659"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint e non null  <br/> |ID tipo di entità.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), not null  <br/> |Descrizione del tipo.  <br/> |
|ptypeIsSystemUser  <br/> |bit, not null  <br/> |True se il tipo corrisponde alle entità usate per scopi interni.  <br/> |
|ptypeIsUser  <br/> |bit, not null  <br/> |True se il tipo è un tipo di utente.  <br/> |
   
**Chiave**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|ptypeID  <br/> |Chiave primaria.  <br/> |
   
**Valori principali**

|**ID**|**Ruolo**|**Descrizione**|**Utente**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Qualsiasi  <br/> |Entità generica con nessun tipo noto. Non usato nella tabella tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Oggetto Principal generico di tipo utente. Non usato nella tabella tblPrincipal.  <br/> |Sì  <br/> |
|3  <br/> |AnyGroup  <br/> |Entità generica con semantica di gruppo. Non usato nella tabella tblPrincipal.  <br/> ||
|4  <br/> |SystemUser  <br/> |Principal usato internamente dal server di chat persistente.  <br/> ||
|5  <br/> |Utente  <br/> |Utente normale.  <br/> |Sì  <br/> |
|8  <br/> |DC  <br/> |Controller di dominio Active Directory Domain Services.  <br/> ||
|9  <br/> |Gruppo  <br/> |Gruppo di sicurezza di Active Directory.  <br/> ||
|10  <br/> |Cartella  <br/> |Contenitore o unità organizzativa di Active Directory.  <br/> ||
   
## <a name="see-also"></a>Vedere anche

[tblPrincipal](tblprincipal.md)
