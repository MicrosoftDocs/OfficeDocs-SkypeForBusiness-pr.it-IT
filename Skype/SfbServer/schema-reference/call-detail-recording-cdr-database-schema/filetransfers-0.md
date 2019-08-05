---
title: Tabella FileTransfers in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Ogni record rappresenta una sessione di trasferimento file.
ms.openlocfilehash: ada437eacfa9a532a4875c3ce1837ccd9d8aed17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194806"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Tabella FileTransfers in Skype for Business Server 2015
 
Ogni record rappresenta una sessione di trasferimento file.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora della richiesta della sessione. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**Nome file** <br/> |nvarchar (256)  <br/> ||Nome del file.  <br/> |
|**Fileidentity** <br/> |uniqueidentifier  <br/> ||Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Principale  <br/> |Usato per identificare ogni messaggio di follow-up associato a questo.  <br/> |
|**Accettare** <br/> |po'  <br/> ||Può essere TRUE o NULL. Se TRUE, quindi Reject e Cancel saranno NULL.  <br/> |
|**Rifiutare** <br/> |po'  <br/> ||Può essere TRUE o NULL. Se TRUE, accetta e Annulla sarà NULL.  <br/> |
|**Annulla** <br/> |po'  <br/> ||Può essere TRUE o NULL. Se TRUE, accetta e rifiuta sarà NULL.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

