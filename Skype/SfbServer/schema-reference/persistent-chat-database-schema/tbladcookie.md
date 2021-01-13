---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814756"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |GUID entità del dominio da monitorare.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nome di dominio completo (FQDN) del controller di dominio corrente utilizzato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.  <br/> |
|adcContent  <br/> |image (binary)  <br/> |Cookie di sincronizzazione di Active Directory.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Timestamp con data e ora di aggiornamento della riga  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Data e ora fino a cui la riga è bloccata in modo da impedire eventuali modifiche. Fa parte di un meccanismo di blocco software che garantisce che un solo servizio chat alla volta esegua la sincronizzazione di Active Directory.  <br/> |
   
**Chiavi**

|**Colonne**|**Descrizione**|
|:-----|:-----|
|prinGuid  <br/> |Chiave primaria.  <br/> |
|prinGuid  <br/> |Chiave esterna con ricerca nella tabella Principal.prinGuid.  <br/> |
   

