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
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="d8113-103">Condivisione di file con disponibilità elevata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d8113-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="d8113-104">Informazioni su come garantire l'elevata disponibilità delle condivisioni di file in Skype for Business Server, usando DFS.</span><span class="sxs-lookup"><span data-stu-id="d8113-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="d8113-105">Per garantire una disponibilità elevata per la condivisione di file nella distribuzione di Skype for Business Server, è possibile usare il file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="d8113-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="d8113-106">DFS supporta il failover da un file server a un altro nello stesso centro dati.</span><span class="sxs-lookup"><span data-stu-id="d8113-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="d8113-107">Per una distribuzione su larga scala, è consigliabile usare i file server dedicati abbinati tramite DFS.</span><span class="sxs-lookup"><span data-stu-id="d8113-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="d8113-108">Per altre informazioni sul DFS in Windows Server 2012, vedere [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span><span class="sxs-lookup"><span data-stu-id="d8113-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="d8113-109">Per informazioni su DFS in Windows Server 2008, vedere [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span><span class="sxs-lookup"><span data-stu-id="d8113-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="d8113-110">A seconda delle dimensioni della rete e della quantità di flessibilità desiderata, è possibile usare una coppia di server per ospitare tutte le condivisioni di file in un sito oppure usare una coppia per ogni pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="d8113-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="d8113-111">DFS è un meccanismo di replica dei file di massimo sforzo, senza l'impegno per i tempi di recupero pubblicato (RTO) o RPO (Recovery Point Objective).</span><span class="sxs-lookup"><span data-stu-id="d8113-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="d8113-112">Un failover tra server DFS deve essere completato in modo rapido, ma il ritardo della replica dei dati può impedire agli utenti di continuare a lavorare in corso quando il failover si verifica.</span><span class="sxs-lookup"><span data-stu-id="d8113-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="d8113-113">Se si usa DFS e l'archivio dati della condivisione di file è fondamentale, è consigliabile eseguire il backup delle condivisioni in modo frequente, ad esempio ogni 4 o 8 ore.</span><span class="sxs-lookup"><span data-stu-id="d8113-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="d8113-114">Quando si abbassa una condivisione file e la replica non è aggiornata, è possibile usare il backup per ripristinare il contenuto del server non riuscito con l'altro server associato al server che ora non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d8113-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

