---
title: Tabella Dialogs in Skype for Business Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni relative a DialogIDs per le sessioni peer-to-peer.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816046"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabella Dialogs in Skype for Business Server 2015
 
La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni relative a DialogIDs per le sessioni peer-to-peer.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principale  <br/> |Ora della richiesta di sessione; utilizzato insieme a SessionIDSeq per identificare in modo univoco una sessione.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Utilizzato insieme a SessionIDTime per identificare in modo univoco una sessione.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum del ExternalID. Questo campo viene utilizzato per aumentare la velocità delle ricerche di database.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |ID finestra di dialogo SIP, memorizzato come binario. Il formato del file binario è:  <br/> finestra di dialogo; da-tag; to-Tag  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

