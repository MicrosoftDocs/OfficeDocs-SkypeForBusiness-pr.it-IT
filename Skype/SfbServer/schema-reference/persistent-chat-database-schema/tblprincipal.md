---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: La tabella Principal contiene tutte le entità, inclusi gli utenti, le cartelle e i gruppi.
ms.openlocfilehash: 6cd47f3f58d7c68f26b5b8d35eb71db64d4d5131
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776136"
---
# <a name="tblprincipal"></a>tblPrincipal
 
La tabella Principal contiene tutte le entità, inclusi gli utenti, le cartelle e i gruppi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|prinGuid  <br/> |GUID, not null  <br/> |GUID dell'entità. Viene ampiamente utilizzato come chiave primaria alternativa perché il suo significato si trova nello spazio di Servizi di dominio Active Directory. Il GUID per un'entità memorizzata nella cache equivale al GUID oggetto Active Directory corrispondente.  <br/> |
|prinUri  <br/> |nvarchar (256), non null  <br/> |URI dell'entità. Lo schema SIP viene utilizzato per gli utenti, mentre ma-grp viene utilizzato per quasi tutte le altre entità.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Nome comune. Valore utilizzato solo dai tipi utente.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nome visualizzato. Valore utilizzato solo dai tipi utente.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nome della società. Valore utilizzato solo dai tipi utente.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Posta elettronica. Valore utilizzato solo dai tipi utente.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nome di dominio dell'oggetto Active Directory di cui l'entità è una versione memorizzata nella cache. Può essere Null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nome dell'entità utente (UPN) dell'utente. Valore utilizzato solo dai tipi utente normali.  <br/> |
|prinDisabled  <br/> |smallint, non null  <br/> | 0: Principale attivo. <br/>  1: l'entità è disabilitata perché le funzionalità SIP dell'utente sono disabilitate. <br/>  2: Principale è eliminato poiché l'oggetto AD associato è stato eliminato. <br/> |
|prinTypeID  <br/> |smallint, not null  <br/> |Tipo di entità (dalla tabella PrincipalType).  <br/> |
|prinPoolID  <br/> |Soglia  <br/> |Skype for Business'assegnazione del pool client per l'entità.  <br/> |
|prinPolicyID  <br/> |Soglia  <br/> |Valore dei criteri del server Chat persistente per l'utente, se è presente un criterio tipo di tag.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID entità del creatore.  <br/> |
|prinAddedOn  <br/> |bigint, non null  <br/> |Indicatore di data e ora per il momento della creazione.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID dell'entità che ha eseguito l'ultimo aggiornamento.  <br/> |
|prinUpdatedOn  <br/> |bigint, non null  <br/> |Indicatore di data e ora per l'ultimo aggiornamento.  <br/> |
|prinVerifiedOn  <br/> |datetime, non null  <br/> |Data e ora dell'ultimo aggiornamento di Sincronizzazione Active Directory per l'entità.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|prinID  <br/> |Chiave primaria.  <br/> |
|prinTypeID  <br/> |Chiave esterna con ricerca nella tabella PrincipalType.ptypeID.  <br/> |
   

