---
title: tblFileToken
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: In tblFileToken sono inclusi i token temporanei ai fini del trasferimento di file.
ms.openlocfilehash: 73958e48814a27e5871b2a0af73d77a55531e49b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831780"
---
# <a name="tblfiletoken"></a>tblFileToken
 
In tblFileToken sono inclusi i token temporanei ai fini del trasferimento di file.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), not null  <br/> |Token univoco (un GUID).  <br/> |
|fileTokenUserID  <br/> |int, not null  <br/> |ID dell'entità che sta trasferendo il file.  <br/> |
|fileTokenChannelID  <br/> |GUID, not null  <br/> |GUID del nodo della chat.  <br/> |
|fileTokenExpireDate  <br/> |datetime, not null  <br/> |Ora di scadenza. I token scadono dopo 30 minuti, se non sono stati bloccati (vedere le descrizioni che seguono in questa colonna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL del file trasferito (per l'uso con il servizio Conformità).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL dell'anteprima del file trasferito (per l'uso con il servizio Conformità).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Timestamp dell'effettiva operazione di trasferimento del file (per l'uso con il servizio Conformità).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True se si tratta di un caricamento, False se si tratta di un download (per l'uso con il servizio Conformità).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, not null  <br/> |True se il token è bloccato. Viene usato per mantenere il token nella tabella fino a quando il servizio di conformità non ha la possibilità di recuperare i campi rilevanti da esso.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|fileToken  <br/> |Chiave primaria.  <br/> |
|fileTokenChannelID  <br/> |Chiave esterna con ricerca nella tabella tblNode.nodeGuid.  <br/> |
   

