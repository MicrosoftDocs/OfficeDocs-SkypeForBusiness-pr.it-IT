---
title: Provisioning della topologia per l'esecuzione del caricamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf4c296068e2bd0deea9470dd84d8fd0c0c9d451
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>Provisioning della topologia per l'esecuzione del caricamento

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>Provisioning della topologia per l'esecuzione del caricamento

A seconda delle impostazioni e della configurazione esistenti di Lync Server 2013, potrebbe essere necessario apportare le modifiche seguenti nell'ambiente:

1.  Impostare i criteri di esecuzione di Windows PowerShell su senza restrizioni. Per controllare le impostazioni dei criteri di esecuzione, aprire Lync Server Management Shell ed eseguire il comando seguente:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Se il comando non restituisce il valore senza restrizioni, eseguire questo comando:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Per configurare in modo efficace Lync Server 2013, sarà necessario:
    
      - Acquisire familiarità con la topologia di Lync Server 2013, ad esempio nomi di computer, istanze del servizio, nomi di siti e criteri.
    
      - Assegna alcuni degli utenti creati a gruppi, ad esempio gruppi di risposta alla ricerca di Response Group, come URI SIP.

3.  Per eseguire lo script dalla riga di comando, è possibile usare:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  In genere, dopo l'esecuzione di uno degli script in questo pacchetto, le tracce risultanti dello script verranno archiviate in un file nello stesso percorso da cui è stato richiamato lo \<script,\>denominato scriptname $h $ m $ s. txt. Ad esempio, eseguire ArchivingPolicy. ps1 alle 12:15 P.M. genererà un file di log, ad esempio ArchivingPolicy121500. txt.

5.  Si noti infine che, anche se sono stati forniti esempi per configurare il server, è necessario modificare o eliminare la configurazione dopo aver completato l'uso del carico.

</div>

</div>

<span> </span>

</div>

</div>

</div>

