---
title: Tabella FocusJoinsAndLeaves in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Ogni record in questa tabella contiene le informazioni di registrazione dettagli chiamata relative alle informazioni di partecipazione e di congedo di un utente per una conferenza. Ogni conferenza è rappresentata in questa tabella da un record ogni volta che un utente partecipa e abbandona la conferenza.
ms.openlocfilehash: ea3af4da259fe4186a3fa3937fd2977779dafeaa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821626"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabella FocusJoinsAndLeaves in Skype for Business Server 2015
 
Ogni record in questa tabella contiene le informazioni di registrazione dettagli chiamata relative alle informazioni di partecipazione e di congedo di un utente per una conferenza. Ogni conferenza è rappresentata in questa tabella da un record ogni volta che un utente partecipa e abbandona la conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora dell'istanza di conferenza. Utilizzato insieme a **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la tabella Conferenze [in Skype for Business Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare l'istanza di conferenza. Utilizzato insieme a **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la tabella Conferenze [in Skype for Business Server 2015.](conferences.md) <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |int  <br/> |Esterna  <br/> |Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella Utenti.](users.md)  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Se un utente è connesso contemporaneamente a più computer o dispositivi, **UserInstance** viene usato per identificare in modo univoco la combinazione utente/dispositivo. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Indica se l'utente ha eseguito l'accesso da interno o meno.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Ruolo di questo utente nella conferenza, ad esempio Relatore o Partecipante.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |Ora in cui l'utente partecipa alla conferenza.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Ora in cui l'utente lascia la conferenza.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Esterna  <br/> |Versione del software client dell'utente, a cui si fa riferimento nella [tabella ClientVersions in Skype for Business Server 2015.](clientversions.md)  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificatore univoco globale (GUID) dell'endpoint utilizzato nella conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

