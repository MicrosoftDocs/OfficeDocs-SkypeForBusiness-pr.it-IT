---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: La tabella Principal contiene tutte le entità, inclusi gli utenti, le cartelle e i gruppi.
ms.openlocfilehash: ee9e16d0fcd5d7206bb73ff8b13cdc9d930b6b97
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815896"
---
# <a name="tblprincipal"></a>tblPrincipal
 
La tabella Principal contiene tutte le entità, inclusi gli utenti, le cartelle e i gruppi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|prinGuid  <br/> |GUID, not null  <br/> |GUID dell'entità. Questa operazione viene ampiamente utilizzata come chiave primaria alternativa, in quanto il relativo significato viene attraversato nello spazio dei servizi di dominio Active Directory. Il GUID per un'entità memorizzata nella cache equivale al GUID oggetto Active Directory corrispondente.  <br/> |
|prinUri  <br/> |nvarchar (256), non null  <br/> |URI dell'entità. Lo schema SIP viene utilizzato per gli utenti, mentre ma-grp viene utilizzato per quasi tutte le altre entità.  <br/> |
|prinname  <br/> |nvarchar (256)  <br/> |Nome comune. Valore utilizzato solo dai tipi utente.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nome visualizzato. Valore utilizzato solo dai tipi utente.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nome della società. Valore utilizzato solo dai tipi utente.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Posta elettronica. Valore utilizzato solo dai tipi utente.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nome di dominio dell'oggetto Active Directory di cui l'entità è una versione memorizzata nella cache. Può essere Null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nome dell'entità utente (UPN) dell'utente. Valore utilizzato solo dai tipi utente normali.  <br/> |
|prinDisabled  <br/> |smallint, non null  <br/> | 0: Principale attivo. <br/>  1: l'entità è disabilitata perché le funzionalità SIP dell'utente sono disattivate. <br/>  2: Principale è eliminato poiché l'oggetto AD associato è stato eliminato. <br/> |
|prinTypeID  <br/> |smallint, not null  <br/> |Tipo di entità (dalla tabella PrincipalType).  <br/> |
|prinPoolID  <br/> |Soglia  <br/> |Assegnazione del pool client Skype for business per l'entità.  <br/> |
|prinPolicyID  <br/> |Soglia  <br/> |Valore dei criteri del server Chat persistente per l'utente, se è presente il criterio tipo di tag.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID entità del creatore.  <br/> |
|prinAddedOn  <br/> |bigint, non null  <br/> |Indicatore di data e ora per il momento della creazione.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID dell'entità che ha eseguito l'ultimo aggiornamento.  <br/> |
|prinUpdatedOn  <br/> |bigint, non null  <br/> |Indicatore di data e ora per l'ultimo aggiornamento.  <br/> |
|prinVerifiedOn  <br/> |datetime, non null  <br/> |Data e ora dell'ultimo aggiornamento di Sincronizzazione Active Directory per l'entità.  <br/> |
   
**Chiavi**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|prinID  <br/> |Chiave primaria.  <br/> |
|prinTypeID  <br/> |Chiave esterna con ricerca nella tabella PrincipalType.ptypeID.  <br/> |
   

