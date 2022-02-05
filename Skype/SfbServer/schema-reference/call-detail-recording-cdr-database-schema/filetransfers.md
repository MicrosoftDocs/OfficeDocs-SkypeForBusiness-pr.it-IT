---
title: Visualizzazione FileTransfers
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Nella visualizzazione FileTransfer vengono archiviate informazioni sulle sessioni di trasferimento file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
---

# <a name="filetransfers-view"></a>Visualizzazione FileTransfers
 
Nella visualizzazione FileTransfer vengono archiviate informazioni sulle sessioni di trasferimento file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
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
   

