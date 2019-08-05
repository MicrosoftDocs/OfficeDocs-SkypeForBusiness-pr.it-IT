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
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194802"
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
   

