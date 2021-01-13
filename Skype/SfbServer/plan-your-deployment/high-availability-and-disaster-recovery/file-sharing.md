---
title: Disponibilità elevata della condivisione di file in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: Informazioni su come garantire la disponibilità elevata delle condivisioni di file in Skype for Business Server, utilizzando DFS.
ms.openlocfilehash: 4d443425f453d63694511d13c6d3a84893058daa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802896"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="df1f9-103">Disponibilità elevata della condivisione di file in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="df1f9-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="df1f9-104">Informazioni su come garantire la disponibilità elevata delle condivisioni di file in Skype for Business Server, utilizzando DFS.</span><span class="sxs-lookup"><span data-stu-id="df1f9-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="df1f9-105">Per garantire la disponibilità elevata per la condivisione dei file nella distribuzione di Skype for Business Server, è possibile utilizzare il file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="df1f9-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="df1f9-106">DFS supporta il failover da un file server a un altro all'interno dello stesso data center.</span><span class="sxs-lookup"><span data-stu-id="df1f9-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="df1f9-107">Per una distribuzione su larga scala, è consigliabile utilizzare file server dedicati accoppiati mediante DFS.</span><span class="sxs-lookup"><span data-stu-id="df1f9-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="df1f9-108">Per ulteriori informazioni su DFS in Windows Server 2012, vedere [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) .</span><span class="sxs-lookup"><span data-stu-id="df1f9-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="df1f9-109">Per informazioni su DFS su Windows Server 2008, vedere [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) .</span><span class="sxs-lookup"><span data-stu-id="df1f9-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="df1f9-110">A seconda delle dimensioni della rete e del grado di resilienza desiderato, è possibile utilizzare una coppia di server per ospitare tutte le condivisioni file in un sito oppure utilizzare una coppia per ogni pool Front End.</span><span class="sxs-lookup"><span data-stu-id="df1f9-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="df1f9-111">DFS è un meccanismo che esegue la replica nel miglior modo possibile in base alle condizioni esistenti, senza alcun impegno pubblicato relativamente al raggiungimento degli obiettivi in termini di tempo di ripristino (RTO, Recovery Time Objective) o di punto di ripristino (RPO, Recovery Point Objective).</span><span class="sxs-lookup"><span data-stu-id="df1f9-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="df1f9-112">Un failover tra server DFS dovrebbe essere completato rapidamente, ma il ritardo di replica dei dati potrebbe impedire agli utenti di continuare a lavorare in corso quando si verifica il failover.</span><span class="sxs-lookup"><span data-stu-id="df1f9-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="df1f9-113">Se si utilizza DFS e l'archivio dati della condivisione file è critico, è consigliabile eseguire il backup delle condivisioni di titoli di frequente, ad esempio ogni 4 o 8 ore.</span><span class="sxs-lookup"><span data-stu-id="df1f9-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="df1f9-114">Quando una condivisione file non è più attiva e la replica non è aggiornata, è possibile utilizzare il backup per ripristinare il contenuto del server con problemi nell'altro server accoppiato al server attualmente non disponibile.</span><span class="sxs-lookup"><span data-stu-id="df1f9-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

