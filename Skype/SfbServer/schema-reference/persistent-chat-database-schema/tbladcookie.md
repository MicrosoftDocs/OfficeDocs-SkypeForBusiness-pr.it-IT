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
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene i cookie di sincronizzazione LDAP (Lightweight Directory Access Protocol) correnti.
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194705"
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
   

