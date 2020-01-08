---
title: Provisioning della topologia per l'esecuzione del caricamento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026915b4a08073e96d29b32278adc4e260eaaea4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="a08ac-102">Provisioning della topologia per l'esecuzione del caricamento</span><span class="sxs-lookup"><span data-stu-id="a08ac-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a08ac-103">_**Argomento Ultima modifica:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="a08ac-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="a08ac-104">Provisioning della topologia per l'esecuzione del caricamento</span><span class="sxs-lookup"><span data-stu-id="a08ac-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="a08ac-105">A seconda delle impostazioni e della configurazione esistenti di Lync Server 2013, potrebbe essere necessario apportare le modifiche seguenti nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="a08ac-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="a08ac-106">Impostare i criteri di esecuzione di Windows PowerShell su senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="a08ac-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="a08ac-107">Per controllare le impostazioni dei criteri di esecuzione, aprire Lync Server Management Shell ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a08ac-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="a08ac-108">Se il comando non restituisce il valore senza restrizioni, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="a08ac-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="a08ac-109">Per configurare in modo efficace Lync Server 2013, sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="a08ac-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="a08ac-110">Acquisire familiarità con la topologia di Lync Server 2013, ad esempio nomi di computer, istanze del servizio, nomi di siti e criteri.</span><span class="sxs-lookup"><span data-stu-id="a08ac-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="a08ac-111">Assegna alcuni degli utenti creati a gruppi, ad esempio gruppi di risposta alla ricerca di Response Group, come URI SIP.</span><span class="sxs-lookup"><span data-stu-id="a08ac-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="a08ac-112">Per eseguire lo script dalla riga di comando, è possibile usare:</span><span class="sxs-lookup"><span data-stu-id="a08ac-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="a08ac-113">In genere, dopo l'esecuzione di uno degli script in questo pacchetto, le tracce risultanti dello script verranno archiviate in un file nello stesso percorso da cui è stato richiamato lo \<script,\>denominato scriptname $h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="a08ac-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="a08ac-114">Ad esempio, eseguire ArchivingPolicy. ps1 alle 12:15 P.M.</span><span class="sxs-lookup"><span data-stu-id="a08ac-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="a08ac-115">genererà un file di log, ad esempio ArchivingPolicy121500. txt.</span><span class="sxs-lookup"><span data-stu-id="a08ac-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="a08ac-116">Si noti infine che, anche se sono stati forniti esempi per configurare il server, è necessario modificare o eliminare la configurazione dopo aver completato l'uso del carico.</span><span class="sxs-lookup"><span data-stu-id="a08ac-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

