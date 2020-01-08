---
title: "Lync Server 2013: Configurare l'archiviazione dei file"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c34d0f93e94c954b3ad2ab6cbd472a3d6a40e3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="fd3ec-102">Configurare l'archiviazione dei file per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd3ec-102">Configure DFS file storage for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd3ec-103">_**Argomento Ultima modifica:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="fd3ec-103">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="fd3ec-104">Lync Server 2013 supporta l'uso di condivisioni file in un file System distribuito (DFS).</span><span class="sxs-lookup"><span data-stu-id="fd3ec-104">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="fd3ec-105">Per informazioni dettagliate su DFS per Windows Server 2008, vedere la guida dettagliata a [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)DFS per windows Server 2008. Per usare un DFS, Lync Server 2013 richiede le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd3ec-105">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="fd3ec-106">Gli spazi dei nomi sono basati su dominio</span><span class="sxs-lookup"><span data-stu-id="fd3ec-106">Namespaces are domain based</span></span>

  - <span data-ttu-id="fd3ec-107">Tutti i server dello spazio dei nomi esegue un minimo di Windows 2008</span><span class="sxs-lookup"><span data-stu-id="fd3ec-107">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="fd3ec-108">La configurazione di Lync Server 2013 richiede che le autorizzazioni per la cartella condivisa consentano l'accesso completo all'amministratore.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-108">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="fd3ec-109">Lync Server 2013 utilizzerà quindi le autorizzazioni per i file NTFS per l'ACL delle cartelle.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-109">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="fd3ec-110">Le autorizzazioni di condivisione DFS ereditate non verranno usate per limitare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-110">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="fd3ec-111">Per altre informazioni sui requisiti di condivisione file, vedere Supporto per l' [archiviazione dei file in Lync Server 2013](lync-server-2013-file-storage-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-111">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd3ec-112">Potrebbe essere necessario cercare informazioni sulla configurazione di una condivisione non DFS.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-112">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="fd3ec-113">In questo caso, estrarre <A href="lync-server-2013-hardware-setup.md">la configurazione hardware per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-113">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="fd3ec-114">La procedura seguente descrive come configurare correttamente le autorizzazioni per le cartelle condivise usando la procedura guidata dello spazio dei nomi DFS, come descritto nella Guida alla configurazione DFS.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-114">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="fd3ec-115">Per configurare le autorizzazioni per le cartelle condivise</span><span class="sxs-lookup"><span data-stu-id="fd3ec-115">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="fd3ec-116">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione DFS**.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-116">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="fd3ec-117">Nell'albero della console dello snap-in Gestione DFS fare clic con il pulsante destro del mouse sul server dello spazio dei nomi (ad esempio filesrv1.contoso.com) e quindi scegliere **Modifica impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-117">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="fd3ec-118">Selezionare **autorizzazioni cartella condivisa**.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-118">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="fd3ec-119">Selezionare **Usa autorizzazioni personalizzate**.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-119">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="fd3ec-120">Per il gruppo amministratore selezionare le opzioni seguenti in **Consenti**:</span><span class="sxs-lookup"><span data-stu-id="fd3ec-120">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="fd3ec-121">**Controllo completo**</span><span class="sxs-lookup"><span data-stu-id="fd3ec-121">**Full Control**</span></span>
    
      - <span data-ttu-id="fd3ec-122">**Modificare**</span><span class="sxs-lookup"><span data-stu-id="fd3ec-122">**Change**</span></span>
    
      - <span data-ttu-id="fd3ec-123">**Leggere**</span><span class="sxs-lookup"><span data-stu-id="fd3ec-123">**Read**</span></span>

6.  <span data-ttu-id="fd3ec-124">Fare clic su **applica**e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd3ec-124">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

