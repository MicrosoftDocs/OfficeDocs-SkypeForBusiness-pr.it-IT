---
title: Aggiungere l'archivio file per Front End Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile utilizzare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: e1dc0c94880bd161fae41be811847e1b0da3dbb5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118695"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="2e06b-104">Aggiungere l'archivio file per Front End Server</span><span class="sxs-lookup"><span data-stu-id="2e06b-104">Add Front End File Store</span></span>

<span data-ttu-id="2e06b-p102">È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile utilizzare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve essere posizionata la condivisione file, oltre a un nome di cartella per la nuova condivisione file.</span><span class="sxs-lookup"><span data-stu-id="2e06b-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e06b-107">La condivisione file non può trovarsi nel Front End Server Enterprise Edition, ma in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2e06b-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e06b-108">È possibile definire la condivisione file nel Generatore di topologie prima di crearla, ma è necessario crearla nel percorso definito prima di pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="2e06b-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e06b-p103">Quando si aggiunge un pool Enterprise Edition Front End o un server Standard Edition alla topologia, il Generatore di topologie deve essere in grado di impostare l'archivio file e configurare elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da usare per l'archivio file. Quando si esegue il Generatore di topologie per pubblicare la nuova topologia, è pertanto necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="2e06b-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="2e06b-111">Per informazioni dettagliate sul supporto dell'archiviazione per le condivisioni file, vedere [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) nella documentazione relativa alla supportabilità e SQL Server Data and Log File [Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2e06b-111">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="2e06b-112">Per informazioni dettagliate sulla collocazione della condivisione file, vedere [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) nella documentazione relativa al supporto.</span><span class="sxs-lookup"><span data-stu-id="2e06b-112">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span> <span data-ttu-id="2e06b-113">Per informazioni dettagliate sulla progettazione della topologia per un pool Enterprise Edition Front End, vedere [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2e06b-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>