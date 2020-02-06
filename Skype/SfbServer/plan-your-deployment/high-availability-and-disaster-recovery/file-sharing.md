---
title: Condivisione di file con disponibilità elevata in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Informazioni su come garantire l'elevata disponibilità delle condivisioni di file in Skype for Business Server, usando DFS.
ms.openlocfilehash: c04c3acd009dd59a3894a62d08395db19c6d2368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815934"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Condivisione di file con disponibilità elevata in Skype for Business Server
 
Informazioni su come garantire l'elevata disponibilità delle condivisioni di file in Skype for Business Server, usando DFS.
  
Per garantire una disponibilità elevata per la condivisione di file nella distribuzione di Skype for Business Server, è possibile usare il file System distribuito (DFS). DFS supporta il failover da un file server a un altro nello stesso centro dati. Per una distribuzione su larga scala, è consigliabile usare i file server dedicati abbinati tramite DFS. Per altre informazioni sul DFS in Windows Server 2012, vedere [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384). Per informazioni su DFS in Windows Server 2008, vedere [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).
  
A seconda delle dimensioni della rete e della quantità di flessibilità desiderata, è possibile usare una coppia di server per ospitare tutte le condivisioni di file in un sito oppure usare una coppia per ogni pool di front-end.
  
DFS è un meccanismo di replica dei file di massimo sforzo, senza l'impegno per i tempi di recupero pubblicato (RTO) o RPO (Recovery Point Objective). Un failover tra server DFS deve essere completato in modo rapido, ma il ritardo della replica dei dati può impedire agli utenti di continuare a lavorare in corso quando il failover si verifica.
  
Se si usa DFS e l'archivio dati della condivisione di file è fondamentale, è consigliabile eseguire il backup delle condivisioni in modo frequente, ad esempio ogni 4 o 8 ore. Quando si abbassa una condivisione file e la replica non è aggiornata, è possibile usare il backup per ripristinare il contenuto del server non riuscito con l'altro server associato al server che ora non è disponibile.
  

