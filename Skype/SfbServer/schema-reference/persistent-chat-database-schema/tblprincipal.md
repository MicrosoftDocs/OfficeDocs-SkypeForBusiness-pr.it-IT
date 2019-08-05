---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal contiene tutte le entità, inclusi utenti, cartelle e gruppi.
ms.openlocfilehash: 5a0b6535ace344951b75f7c5c9488f56a18564ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194674"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal contiene tutte le entità, inclusi utenti, cartelle e gruppi.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ID entità.  <br/> |
|prinGuid  <br/> |GUID, non null  <br/> |GUID principale. Questa operazione viene ampiamente usata come chiave primaria alternativa perché il relativo significato viene attraversato nello spazio dei servizi di dominio Active Directory. Il GUID di un'entità memorizzata nella cache è uguale al GUID dell'oggetto Active Directory corrispondente.  <br/> |
|prinUri  <br/> |nvarchar (256), not null  <br/> |URI principale. Lo schema SIP viene usato per gli utenti e ma-GRP viene usato per quasi tutto il resto.  <br/> |
|prinname  <br/> |nvarchar (256)  <br/> |Nome comune. Usato solo dai tipi di utente.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Nome visualizzato. Usato solo dai tipi di utente.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Nome società. Usato solo dai tipi di utente.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Posta elettronica. Usato solo dai tipi di utente.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Nome di dominio dell'oggetto Active Directory in cui l'entità è una versione memorizzata nella cache. Può essere null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Nome dell'entità utente (UPN) dell'utente. Usato solo dai normali tipi di utente.  <br/> |
|prinDisabled  <br/> |smallint e non null  <br/> | 0: Principal è attivo. <br/>  1: Principal è disabilitato perché le funzionalità SIP dell'utente sono disabilitate. <br/>  2: Principal viene eliminato perché l'oggetto Active Directory associato è stato eliminato. <br/> |
|prinTypeID  <br/> |smallint e non null  <br/> |Tipo di entità (dalla tabella tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Assegnazione del pool client Skype for business per l'entità.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Valore dei criteri del server di chat persistente per l'utente, se è presente il criterio tipo di tag.  <br/> |
|prinAddedBy  <br/> |int  <br/> |ID principale del creatore.  <br/> |
|prinAddedOn  <br/> |bigint e non null  <br/> |Indicatore di data e ora per la creazione.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |ID dell'oggetto Principal che ha aggiornato l'ultimo aggiornamento.  <br/> |
|prinUpdatedOn  <br/> |bigint e non null  <br/> |Indicatore di data e ora per l'ultimo aggiornamento.  <br/> |
|prinVerifiedOn  <br/> |DateTime, not null  <br/> |Data e ora dell'ultimo aggiornamento della sincronizzazione di Active Directory per l'entità.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|prinID  <br/> |Chiave primaria.  <br/> |
|prinTypeID  <br/> |Chiave esterna con ricerca nella tabella tblPrincipalType. ptypeID.  <br/> |
   

