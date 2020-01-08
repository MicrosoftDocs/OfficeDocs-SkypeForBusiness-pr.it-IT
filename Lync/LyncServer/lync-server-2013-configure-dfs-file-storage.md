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

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Configurare l'archiviazione dei file per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-05-23_

Lync Server 2013 supporta l'uso di condivisioni file in un file System distribuito (DFS). Per informazioni dettagliate su DFS per Windows Server 2008, vedere la guida dettagliata a [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)DFS per windows Server 2008. Per usare un DFS, Lync Server 2013 richiede le operazioni seguenti:

  - Gli spazi dei nomi sono basati su dominio

  - Tutti i server dello spazio dei nomi esegue un minimo di Windows 2008

La configurazione di Lync Server 2013 richiede che le autorizzazioni per la cartella condivisa consentano l'accesso completo all'amministratore. Lync Server 2013 utilizzerà quindi le autorizzazioni per i file NTFS per l'ACL delle cartelle. Le autorizzazioni di condivisione DFS ereditate non verranno usate per limitare l'accesso.

Per altre informazioni sui requisiti di condivisione file, vedere Supporto per l' [archiviazione dei file in Lync Server 2013](lync-server-2013-file-storage-support.md) nella documentazione relativa alla supportabilità.

<div>


> [!NOTE]  
> Potrebbe essere necessario cercare informazioni sulla configurazione di una condivisione non DFS. In questo caso, estrarre <A href="lync-server-2013-hardware-setup.md">la configurazione hardware per Lync Server 2013</A>.



</div>

La procedura seguente descrive come configurare correttamente le autorizzazioni per le cartelle condivise usando la procedura guidata dello spazio dei nomi DFS, come descritto nella Guida alla configurazione DFS.

<div>

## <a name="to-configure-shared-folder-permissions"></a>Per configurare le autorizzazioni per le cartelle condivise

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione DFS**.

2.  Nell'albero della console dello snap-in Gestione DFS fare clic con il pulsante destro del mouse sul server dello spazio dei nomi (ad esempio filesrv1.contoso.com) e quindi scegliere **Modifica impostazioni**.

3.  Selezionare **autorizzazioni cartella condivisa**.

4.  Selezionare **Usa autorizzazioni personalizzate**.

5.  Per il gruppo amministratore selezionare le opzioni seguenti in **Consenti**:
    
      - **Controllo completo**
    
      - **Modificare**
    
      - **Leggere**

6.  Fare clic su **applica**e quindi su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

