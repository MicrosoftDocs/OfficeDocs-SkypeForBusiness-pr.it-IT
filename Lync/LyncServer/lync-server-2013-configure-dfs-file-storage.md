---
title: "Lync Server 2013: configurare l'archiviazione di file DFS"
description: "Lync Server 2013: configurare l'archiviazione di file DFS."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70ae93db188ec51d04dd33d6c3cb5659db5a2c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564382"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="fbaa5-103">Configurare l'archiviazione dei file DFS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbaa5-103">Configure DFS file storage for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbaa5-104">_**Ultimo argomento modificato:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="fbaa5-104">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="fbaa5-105">Lync Server 2013 supporta l'utilizzo di condivisioni di file in un file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="fbaa5-105">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="fbaa5-106">Per informazioni dettagliate su DFS per Windows Server 2008, vedere la guida dettagliata di DFS per Windows Server 2008 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) . Per utilizzare un DFS, Lync Server 2013 richiede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fbaa5-106">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="fbaa5-107">Gli spazi dei nomi devono essere basati sul dominio.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-107">Namespaces are domain based</span></span>

  - <span data-ttu-id="fbaa5-108">Tutti i server dello spazio dei nomi devono eseguire almeno Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-108">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="fbaa5-109">L'installazione di Lync Server 2013 richiede che le autorizzazioni per la cartella condivisa consentano l'accesso completo all'amministratore.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-109">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="fbaa5-110">Lync Server 2013 utilizzerà le autorizzazioni per i file NTFS per le cartelle ACL.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-110">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="fbaa5-111">Le autorizzazioni di condivisione DFS ereditate non verranno utilizzate per limitare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-111">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="fbaa5-112">Per ulteriori informazioni sui requisiti di condivisione file, vedere [file Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-112">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fbaa5-113">È possibile cercare informazioni sulla configurazione di una condivisione non DFS.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-113">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="fbaa5-114">In caso affermativo, vedere <A href="lync-server-2013-hardware-setup.md">installazione hardware per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-114">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="fbaa5-115">Nella procedura seguente viene illustrato come configurare correttamente le autorizzazioni delle cartelle condivise utilizzando la procedura guidata per lo spazio dei nomi DFS, come descritto nella guida all'installazione di DFS.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-115">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="fbaa5-116">Per configurare le autorizzazioni delle cartelle condivise</span><span class="sxs-lookup"><span data-stu-id="fbaa5-116">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="fbaa5-117">Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Gestione DFS**.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="fbaa5-118">Nell'albero della console dello snap-in Gestione DFS fare clic con il pulsante destro del mouse sul server dello spazio dei nomi, ad esempio filesrv1.contoso.com, e quindi scegliere **Modifica impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-118">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="fbaa5-119">Selezionare **Autorizzazioni cartella condivisa**.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-119">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="fbaa5-120">Selezionare **Usa autorizzazioni personalizzate**.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-120">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="fbaa5-121">Per il gruppo degli amministratori, selezionare quanto segue in **Consenti**:</span><span class="sxs-lookup"><span data-stu-id="fbaa5-121">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="fbaa5-122">**Controllo completo**</span><span class="sxs-lookup"><span data-stu-id="fbaa5-122">**Full Control**</span></span>
    
      - <span data-ttu-id="fbaa5-123">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="fbaa5-123">**Change**</span></span>
    
      - <span data-ttu-id="fbaa5-124">**Lettura**</span><span class="sxs-lookup"><span data-stu-id="fbaa5-124">**Read**</span></span>

6.  <span data-ttu-id="fbaa5-125">Fare clic su **Applica** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbaa5-125">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

