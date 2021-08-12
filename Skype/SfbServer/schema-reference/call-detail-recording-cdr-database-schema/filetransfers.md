---
title: Visualizzazione FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Nella visualizzazione FileTransfer sono archiviate informazioni sulle sessioni di trasferimento file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: e805b770038eb7fae93337c5d6c26d7059e5764436328f6321e65c948e40c88d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349688"
---
# <a name="filetransfers-view"></a>Visualizzazione FileTransfers
 
Nella visualizzazione FileTransfer sono archiviate informazioni sulle sessioni di trasferimento file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La visualizzazione FileTransfers contiene tutte le colonne nella visualizzazione [SessionDetails](sessiondetails-0.md) oltre alle colonne elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Nome del file trasferito.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Valore utilizzato per identificare ogni messaggio successivo come associato a questo.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome di file.  <br/> |
|**Accept** <br/> |bit  <br/> |Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.  <br/> |
|**Rifiuta** <br/> |bit  <br/> |Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.  <br/> |
|**Annulla** <br/> |bit  <br/> |Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.  <br/> |
   

