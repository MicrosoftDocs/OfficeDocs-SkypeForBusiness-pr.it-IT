---
title: Visualizzazione FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815204"
---
# <a name="filetransfers-view"></a>Visualizzazione FileTransfers
 
La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La Visualizzazione FileTransfers contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre alle colonne elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**Nome file** <br/> |nvarchar (256)  <br/> |Nome del file trasferito.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Usato per identificare ogni messaggio di follow-up associato a questo.  <br/> |
|**Fileidentity** <br/> |uniqueidentifier  <br/> |Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.  <br/> |
|**Accettare** <br/> |po'  <br/> |Può essere TRUE o NULL. Se TRUE, quindi Reject e Cancel saranno NULL.  <br/> |
|**Rifiutare** <br/> |po'  <br/> |Può essere TRUE o NULL. Se TRUE, accetta e Annulla sarà NULL.  <br/> |
|**Annulla** <br/> |po'  <br/> |Può essere TRUE o NULL. Se TRUE, accetta e rifiuta sarà NULL.  <br/> |
   

