---
title: Tabella finestre di dialogo in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni su DialogIDs per le sessioni peer-to-peer.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194817"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Tabella finestre di dialogo in Skype for Business Server 2015
 
La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni su DialogIDs per le sessioni peer-to-peer.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Principale  <br/> |Ora della richiesta di sessione; usato in combinazione con SessionIDSeq per identificare in modo univoco una sessione.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Usato in combinazione con SessionIDTime per identificare in modo univoco una sessione.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum della ExternalID. Questo campo viene usato per aumentare la velocità delle ricerche di database.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |ID finestra di dialogo SIP, archiviato come binario. Il formato del file binario è:  <br/> finestra di dialogo; da-tag; to-Tag  <br/> Questi dati possono essere convertiti in formato testo usando la sintassi seguente:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

