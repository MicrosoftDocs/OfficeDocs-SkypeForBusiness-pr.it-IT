---
title: Tabella FileTransfers in Skype for Business Server
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
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Ogni record rappresenta una sessione di trasferimento file.
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821696"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabella FileTransfers in Skype for Business Server
 
Ogni record rappresenta una sessione di trasferimento file.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md) <br/> |
|**FileName** <br/> |nvarchar(256)  <br/> ||Nome del file.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Identificatore univoco che distingue trasferimenti diversi che interessano lo stesso nome file.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Principale  <br/> |Valore utilizzato per identificare ogni messaggio successivo come associato a questo.  <br/> |
|**Accetta** <br/> |bit  <br/> ||Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.  <br/> |
|**Rifiuta** <br/> |bit  <br/> ||Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.  <br/> |
|**Annulla** <br/> |bit  <br/> ||Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

