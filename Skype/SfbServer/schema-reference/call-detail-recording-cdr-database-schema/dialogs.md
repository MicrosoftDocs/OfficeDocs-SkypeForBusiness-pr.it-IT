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
description: La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni sui DialogID per le sessioni peer-to-peer.
ms.openlocfilehash: 368abb6131367434edbdf1fe142a376fe9a155277eec8b369482545146dbdc3b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302280"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabella Dialogs in Skype for Business Server 2015
 
La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni sui DialogID per le sessioni peer-to-peer.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principale  <br/> |Ora della richiesta di sessione; utilizzato insieme a SessionIDSeq per identificare in modo univoco una sessione.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Utilizzato insieme a SessionIDTime per identificare in modo univoco una sessione.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum di ExternalID. Questo campo viene utilizzato per aumentare la velocità delle ricerche nel database.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |ID finestra di dialogo SIP, archiviato come binario. Il formato del file binario è:  <br/> dialog;from-tag;to-tag  <br/> Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

