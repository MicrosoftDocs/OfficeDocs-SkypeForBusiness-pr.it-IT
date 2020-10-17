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
# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="4f414-102">Provisioning della topologia per l'esecuzione del caricamento</span><span class="sxs-lookup"><span data-stu-id="4f414-102">Provisioning the Topology to Run Load</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f414-103">_**Ultimo argomento modificato:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="4f414-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

<span data-ttu-id="4f414-104">A seconda delle impostazioni e della configurazione esistenti di Lync Server 2013, potrebbe essere necessario apportare le modifiche seguenti nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="4f414-104">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="4f414-105">Impostare il criterio di esecuzione di Windows PowerShell su Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="4f414-105">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="4f414-106">Per controllare le impostazioni dei criteri di esecuzione, aprire Lync Server Management Shell ed eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4f414-106">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="4f414-107">Se il comando non restituisce il valore Unrestricted, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4f414-107">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="4f414-108">Per configurare in modo efficace Lync Server 2013, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f414-108">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="4f414-109">Acquisire familiarità con la topologia di Lync Server 2013, ad esempio i nomi di computer, le istanze di servizio, i nomi dei siti e i criteri.</span><span class="sxs-lookup"><span data-stu-id="4f414-109">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="4f414-110">Assegnare alcuni degli utenti che sono stati creati ai gruppi, ad esempio i gruppi di risposta di Response Group, come gli URI SIP.</span><span class="sxs-lookup"><span data-stu-id="4f414-110">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="4f414-111">Per eseguire lo script dalla riga di comando, è possibile utilizzare:</span><span class="sxs-lookup"><span data-stu-id="4f414-111">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="4f414-112">In genere, dopo l'esecuzione di uno degli script in questo pacchetto, le tracce risultanti dallo script verranno archiviate in un file nello stesso percorso da cui è stato richiamato lo script, denominato \<scriptname\> $h $ m $s.txt.</span><span class="sxs-lookup"><span data-stu-id="4f414-112">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="4f414-113">Ad esempio, l'esecuzione di ArchivingPolicy.ps1 alle 12:15 P.M.</span><span class="sxs-lookup"><span data-stu-id="4f414-113">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="4f414-114">genererà un file di registro, ad esempio ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="4f414-114">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="4f414-115">Si noti infine che, sebbene siano stati forniti esempi per la configurazione del server, è necessario modificare o eliminare la configurazione dopo aver completato l'esecuzione del carico.</span><span class="sxs-lookup"><span data-stu-id="4f414-115">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

