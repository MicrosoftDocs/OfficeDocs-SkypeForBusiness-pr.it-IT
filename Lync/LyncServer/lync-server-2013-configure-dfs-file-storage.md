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
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Configurare l'archiviazione dei file DFS per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-05-23_

Lync Server 2013 supporta l'utilizzo di condivisioni di file in un file System distribuito (DFS). Per informazioni dettagliate su DFS per Windows Server 2008, vedere la guida dettagliata di DFS per Windows Server 2008 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) . Per utilizzare un DFS, Lync Server 2013 richiede quanto segue:

  - Gli spazi dei nomi devono essere basati sul dominio.

  - Tutti i server dello spazio dei nomi devono eseguire almeno Windows 2008.

L'installazione di Lync Server 2013 richiede che le autorizzazioni per la cartella condivisa consentano l'accesso completo all'amministratore. Lync Server 2013 utilizzerà le autorizzazioni per i file NTFS per le cartelle ACL. Le autorizzazioni di condivisione DFS ereditate non verranno utilizzate per limitare l'accesso.

Per ulteriori informazioni sui requisiti di condivisione file, vedere [file Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md) nella documentazione relativa alla supportabilità.

<div>


> [!NOTE]  
> È possibile cercare informazioni sulla configurazione di una condivisione non DFS. In caso affermativo, vedere <A href="lync-server-2013-hardware-setup.md">installazione hardware per Lync Server 2013</A>.



</div>

Nella procedura seguente viene illustrato come configurare correttamente le autorizzazioni delle cartelle condivise utilizzando la procedura guidata per lo spazio dei nomi DFS, come descritto nella guida all'installazione di DFS.

<div>

## <a name="to-configure-shared-folder-permissions"></a>Per configurare le autorizzazioni delle cartelle condivise

1.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Gestione DFS**.

2.  Nell'albero della console dello snap-in Gestione DFS fare clic con il pulsante destro del mouse sul server dello spazio dei nomi, ad esempio filesrv1.contoso.com, e quindi scegliere **Modifica impostazioni**.

3.  Selezionare **Autorizzazioni cartella condivisa**.

4.  Selezionare **Usa autorizzazioni personalizzate**.

5.  Per il gruppo degli amministratori, selezionare quanto segue in **Consenti**:
    
      - **Controllo completo**
    
      - **Modifica**
    
      - **Lettura**

6.  Fare clic su **Applica** e quindi su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

