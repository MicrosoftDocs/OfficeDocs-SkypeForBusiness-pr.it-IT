---
title: Provisioning della topologia per l'esecuzione del caricamento
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45b1c9d320ef35555e83bbd8851d77e00a452631
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509103"
---
# <a name="provisioning-the-topology-to-run-load"></a>Provisioning della topologia per l'esecuzione del caricamento

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-04_

<div>

A seconda delle impostazioni e della configurazione esistenti di Lync Server 2013, potrebbe essere necessario apportare le modifiche seguenti nell'ambiente:

1.  Impostare il criterio di esecuzione di Windows PowerShell su Unrestricted. Per controllare le impostazioni dei criteri di esecuzione, aprire Lync Server Management Shell ed eseguire il comando riportato di seguito:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Se il comando non restituisce il valore Unrestricted, eseguire il comando seguente:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Per configurare in modo efficace Lync Server 2013, è necessario eseguire le operazioni seguenti:
    
      - Acquisire familiarità con la topologia di Lync Server 2013, ad esempio i nomi di computer, le istanze di servizio, i nomi dei siti e i criteri.
    
      - Assegnare alcuni degli utenti che sono stati creati ai gruppi, ad esempio i gruppi di risposta di Response Group, come gli URI SIP.

3.  Per eseguire lo script dalla riga di comando, è possibile utilizzare:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  In genere, dopo l'esecuzione di uno degli script in questo pacchetto, le tracce risultanti dallo script verranno archiviate in un file nello stesso percorso da cui è stato richiamato lo script, denominato \<scriptname\> $h $ m $s.txt. Ad esempio, l'esecuzione di ArchivingPolicy.ps1 alle 12:15 P.M. genererà un file di registro, ad esempio ArchivingPolicy121500.txt.

5.  Si noti infine che, sebbene siano stati forniti esempi per la configurazione del server, è necessario modificare o eliminare la configurazione dopo aver completato l'esecuzione del carico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

