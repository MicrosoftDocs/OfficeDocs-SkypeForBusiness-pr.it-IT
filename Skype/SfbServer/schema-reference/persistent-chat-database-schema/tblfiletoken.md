---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contiene token temporanei per scopi di trasferimento di file.
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814594"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken contiene token temporanei per scopi di trasferimento di file.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), not null  <br/> |Token univoco (GUID).  <br/> |
|fileTokenUserID  <br/> |int, not null  <br/> |ID dell'entità che sta trasferendo il file.  <br/> |
|fileTokenChannelID  <br/> |GUID, non null  <br/> |GUID del nodo della chat room.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, not null  <br/> |Data di scadenza. I token scadono dopo 30 minuti, a meno che non siano stati aggiunti (Vedi le descrizioni seguenti in questa colonna).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar (256)  <br/> |URL del file trasferito (per l'uso del servizio di conformità).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar (256)  <br/> |URL dell'anteprima del file trasferito (per l'uso del servizio di conformità).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Timestamp per l'effettiva operazione di trasferimento file (per l'uso del servizio di conformità).  <br/> |
|fileTokenComplianceIsUpload  <br/> |po'  <br/> |True se upload; False se il download (per l'uso del servizio di conformità).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, not null  <br/> |True se il token è bloccato. Viene usato per conservare il token nella tabella finché il servizio di conformità non ha la possibilità di recuperare i campi rilevanti.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|fileToken  <br/> |Chiave primaria.  <br/> |
|fileTokenChannelID  <br/> |Chiave esterna con ricerca nella tabella tblNode. nodeGuid.  <br/> |
   

