---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814704"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, non null  <br/> |GUID principale del dominio da monitorare.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Nome di dominio completo (FQDN) del controller di dominio corrente usato per la sincronizzazione dei servizi di dominio Active Directory. Ha un valore informativo.  <br/> |
|adcContent  <br/> |immagine (binario)  <br/> |Cookie di sincronizzazione di Active Directory.  <br/> |
|lastUpdated  <br/> |DateTime  <br/> |Indicatore di data e ora con il tempo di aggiornamento delle righe.  <br/> |
|lockedUntil  <br/> |DateTime  <br/> |Ora fino a quando la riga non viene bloccata per le modifiche. Questo fa parte di un meccanismo di blocco software che garantisce che solo uno dei servizi di chat esegue la sincronizzazione di Active Directory alla volta.  <br/> |
   
**Tasti**

|**Colonne**|**Descrizione**|
|:-----|:-----|
|prinGuid  <br/> |Chiave primaria.  <br/> |
|prinGuid  <br/> |Chiave esterna con ricerca nella tabella Principal. prinGuid.  <br/> |
   

