---
title: Eseguire LyncPerfTool
description: Eseguire LyncPerfTool.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560082"
---
# <a name="run-lyncperftool"></a><span data-ttu-id="2045a-103">Eseguire LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="2045a-103">Run LyncPerfTool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2045a-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2045a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="2045a-105">Prima di eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 (LyncPerfTool.exe), è necessario creare gli utenti, i contatti e gli scenari.</span><span class="sxs-lookup"><span data-stu-id="2045a-105">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="2045a-106">Per informazioni dettagliate sull'utilizzo degli strumenti per eseguire queste operazioni, vedere [creare utenti e contatti](create-users-and-contacts.md) e [configurare il profilo utente](configure-user-profile.md).</span><span class="sxs-lookup"><span data-stu-id="2045a-106">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="2045a-107">L'esecuzione di questi strumenti genererà anche un file che verrà eseguito LyncPerfTool.exe come parte di un file batch con i parametri necessari inclusi.</span><span class="sxs-lookup"><span data-stu-id="2045a-107">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="2045a-108">Esecuzione dello strumento di stress e prestazioni di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2045a-108">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="2045a-109">Lo strumento UserProfileGenerator.exe crea un file batch che consente di eseguire LyncPerfTool.exe registrando i contatori delle prestazioni di LyncPerfTool e il caricamento del file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="2045a-109">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="2045a-110">Il file batch esegue un'istanza di LyncPerfTool.exe per ogni file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2045a-110">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="2045a-111">Per eseguire il file batch, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2045a-111">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="2045a-112">Copiare la cartella contenente le cartelle e i file di configurazione nella directory che contiene LyncStressTool.exe su ogni computer client.</span><span class="sxs-lookup"><span data-stu-id="2045a-112">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="2045a-113">Ad esempio, se i file di configurazione sono stati generati nella cartella denominata 1,28 \_ 13.16.16, copiare tale cartella nella cartella che contiene LyncPerfTool.exe su ogni client.</span><span class="sxs-lookup"><span data-stu-id="2045a-113">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="2045a-114">Passare alla cartella client numerata in modo appropriato ed eseguire lo script batch di RunClient.</span><span class="sxs-lookup"><span data-stu-id="2045a-114">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="2045a-115">È sufficiente fare doppio clic sul file batch in Esplora risorse e verranno eseguiti tutti i file di configurazione per il numero di client.</span><span class="sxs-lookup"><span data-stu-id="2045a-115">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="2045a-116">È inoltre possibile eseguire lo script dalla cartella client appropriata utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2045a-116">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="2045a-117">Per eseguire LyncPerfTool.exe direttamente, aprire una finestra del prompt dei comandi e quindi digitare il comando seguente dalla riga di comando (quando si esegue questa operazione per la prima volta, assicurarsi di registrare i contatori delle prestazioni regsvr32/i/n/s LyncPerfToolPerf.dll, come illustrato nella nota più avanti in questo argomento) :LyncPerfTool.exe/file:\<configXML\></span><span class="sxs-lookup"><span data-stu-id="2045a-117">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="2045a-118">Per visualizzare i valori nel file di configurazione, includere il parametro/displayfile nel comando precedente, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2045a-118">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="2045a-119">Per terminare il processo, premere CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="2045a-119">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2045a-120">Prima di eseguire direttamente LyncPerfTool, è necessario registrare i contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2045a-120">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="2045a-121">Immettere il comando seguente per registrare i contatori delle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="2045a-121">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="2045a-122">Ogni istanza di LyncPerfTool.exe avviata inizierà immediatamente la firma degli utenti, generalmente a una velocità di un utente al secondo.</span><span class="sxs-lookup"><span data-stu-id="2045a-122">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="2045a-123">La frequenza di accesso dell'utente di picco per il pool è pari a circa 12 al secondo.</span><span class="sxs-lookup"><span data-stu-id="2045a-123">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="2045a-124">Questo significa che non è necessario avviare più di 12 istanze di LyncPerfTool contemporaneamente, mentre gli utenti continuano a eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="2045a-124">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="2045a-125">1000 gli utenti impiegano circa 20 minuti per accedere completamente, a una al secondo.</span><span class="sxs-lookup"><span data-stu-id="2045a-125">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2045a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2045a-126">See Also</span></span>


[<span data-ttu-id="2045a-127">Creare utenti e contatti</span><span class="sxs-lookup"><span data-stu-id="2045a-127">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="2045a-128">Configurare il profilo utente</span><span class="sxs-lookup"><span data-stu-id="2045a-128">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

