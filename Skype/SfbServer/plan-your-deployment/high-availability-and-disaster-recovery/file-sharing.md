---
title: Disponibilità elevata per la condivisione di file in Skype for Business Server
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
description: Informazioni su come garantire la disponibilità elevata delle condivisioni file in Skype for Business Server, usando DFS.
ms.openlocfilehash: f47d8207969063472af23d898ef8a52c2383df0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093094"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="44b2a-103">Disponibilità elevata per la condivisione di file in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="44b2a-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="44b2a-104">Informazioni su come garantire la disponibilità elevata delle condivisioni file in Skype for Business Server, usando DFS.</span><span class="sxs-lookup"><span data-stu-id="44b2a-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="44b2a-105">Per garantire la disponibilità elevata per la condivisione di file nella distribuzione di Skype for Business Server, è possibile utilizzare DFS (Distributed File System).</span><span class="sxs-lookup"><span data-stu-id="44b2a-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="44b2a-106">DFS supporta il failover da un file server a un altro all'interno dello stesso data center.</span><span class="sxs-lookup"><span data-stu-id="44b2a-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="44b2a-107">Per una distribuzione su larga scala, è consigliabile utilizzare file server dedicati accoppiati mediante DFS.</span><span class="sxs-lookup"><span data-stu-id="44b2a-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="44b2a-108">Per ulteriori informazioni su DFS in Windows Server 2012, vedere [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) .</span><span class="sxs-lookup"><span data-stu-id="44b2a-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)).</span></span> <span data-ttu-id="44b2a-109">Per informazioni su DFS in Windows Server 2008, vedere [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) .</span><span class="sxs-lookup"><span data-stu-id="44b2a-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)).</span></span>
  
<span data-ttu-id="44b2a-110">A seconda delle dimensioni della rete e del grado di resilienza desiderato, è possibile utilizzare una coppia di server per ospitare tutte le condivisioni file in un sito oppure utilizzare una coppia per ogni pool Front End.</span><span class="sxs-lookup"><span data-stu-id="44b2a-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="44b2a-111">DFS è un meccanismo che esegue la replica nel miglior modo possibile in base alle condizioni esistenti, senza alcun impegno pubblicato relativamente al raggiungimento degli obiettivi in termini di tempo di ripristino (RTO, Recovery Time Objective) o di punto di ripristino (RPO, Recovery Point Objective).</span><span class="sxs-lookup"><span data-stu-id="44b2a-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="44b2a-112">Un failover tra server DFS deve essere completato rapidamente, ma il ritardo della replica dei dati può impedire agli utenti di continuare a lavorare in corso quando si verifica il failover.</span><span class="sxs-lookup"><span data-stu-id="44b2a-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="44b2a-113">Se si utilizza DFS e l'archivio dati nella condivisione file è fondamentale, è consigliabile eseguire frequentemente il backup delle condivisioni file, ad esempio ogni 4-8 ore.</span><span class="sxs-lookup"><span data-stu-id="44b2a-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="44b2a-114">Quando una condivisione file non è più attiva e la replica non è aggiornata, è possibile utilizzare il backup per ripristinare il contenuto del server con problemi nell'altro server accoppiato al server attualmente non disponibile.</span><span class="sxs-lookup"><span data-stu-id="44b2a-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
