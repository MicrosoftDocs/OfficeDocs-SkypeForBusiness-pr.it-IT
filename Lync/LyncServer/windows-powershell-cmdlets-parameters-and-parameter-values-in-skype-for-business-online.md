---
title: Cmdlet, parametri e valori di parametro di Windows PowerShell in Skype for business online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce954eff790bae6974f144360637d6061318d3d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="de321-102">Cmdlet, parametri e valori di parametro di Windows PowerShell in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="de321-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de321-103">_**Argomento Ultima modifica:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="de321-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="de321-104">Se si ha familiarità con la finestra di comando trovata in tutte le versioni di Windows (o se si ha familiarità con MS-DOS), si avrà un vantaggio quando si impara a usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de321-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="de321-105">Nella finestra di comando digitare un comando e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="de321-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="de321-106">In risposta, il computer esegue un comando o un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="de321-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="de321-107">Ad esempio, per restituire informazioni su tutti i file e le cartelle nella directory corrente, digitare questo comando al prompt dei comandi e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="de321-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

    dir

<span data-ttu-id="de321-108">A sua volta, vengono restituite informazioni su tutti i file e le cartelle nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="de321-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

<span data-ttu-id="de321-109">Questo è un esempio di risultato quando si digita solo il nome di un comando o di un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="de321-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="de321-110">Tuttavia, molti dei comandi eseguiti dall'interno della finestra di comando accettano anche *argomenti*.</span><span class="sxs-lookup"><span data-stu-id="de321-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="de321-111">Gli argomenti sono altre parti di informazioni passate al comando, che modificano il comportamento del comando.</span><span class="sxs-lookup"><span data-stu-id="de321-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="de321-112">Ad esempio, se si vogliono solo visualizzare i nomi dei file e delle cartelle nella directory corrente, non sono disponibili altre informazioni, come le dimensioni del file o della cartella, o la data e l'ora in cui è stata creata la cartella o la cartella.</span><span class="sxs-lookup"><span data-stu-id="de321-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="de321-113">In questo caso, quando si eseguirà il comando dir si aggiungerà l'argomento **/b** :</span><span class="sxs-lookup"><span data-stu-id="de321-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

    dir /b

<span data-ttu-id="de321-114">Quando Includi l'argomento **/b** , il comando **dir** riporta solo i nomi delle cartelle e dei file trovati nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="de321-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

<span data-ttu-id="de321-115">Nel comando precedente l'argomento **/b** rappresenta le uniche informazioni necessarie per limitare i dati restituiti ai nomi di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="de321-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="de321-116">Questo avviene spesso con i comandi della riga di comando: la mera presenza di un argomento è tutto ciò che serve per modificare il comportamento del comando.</span><span class="sxs-lookup"><span data-stu-id="de321-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="de321-117">Ossia includere l'argomento **/b** per nascondere altre informazioni oppure escludere l'argomento **/b** per visualizzare le informazioni aggiuntive. In altri casi, tuttavia, devi specificare un *valore di argomento*.</span><span class="sxs-lookup"><span data-stu-id="de321-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="de321-118">Un valore di argomento contiene informazioni aggiuntive passate all'argomento stesso.</span><span class="sxs-lookup"><span data-stu-id="de321-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="de321-119">Ad esempio, l'argomento **/o** consente di specificare come si vuole ordinare il comando dir per l'ordinamento dei dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="de321-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="de321-120">Tra le altre opzioni, puoi usare il valore dell'argomento **e** per ordinare per estensione di file o per il valore dell'argomento **s** per ordinare in base alle dimensioni del file.</span><span class="sxs-lookup"><span data-stu-id="de321-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="de321-121">Ad esempio, questo comando Ordina i dati restituiti per estensione di file.</span><span class="sxs-lookup"><span data-stu-id="de321-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="de321-122">Nota in che modo il valore dell'argomento **e** viene incluso subito dopo l'argomento **/o** :</span><span class="sxs-lookup"><span data-stu-id="de321-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

    dir /oe

<span data-ttu-id="de321-123">Usando la cartella di esempio, i dati restituiti avranno un aspetto simile al seguente, con i file ordinati alfabeticamente per estensione di file:</span><span class="sxs-lookup"><span data-stu-id="de321-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

<span data-ttu-id="de321-124">In alternativa, per individuare esattamente le informazioni di cui si sta parlando:</span><span class="sxs-lookup"><span data-stu-id="de321-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

<span data-ttu-id="de321-125">configurazione.</span><span class="sxs-lookup"><span data-stu-id="de321-125">setup.</span></span> <span data-ttu-id="de321-126">**documento**</span><span class="sxs-lookup"><span data-stu-id="de321-126">**doc**</span></span>  
<span data-ttu-id="de321-127">RHDSetup.</span><span class="sxs-lookup"><span data-stu-id="de321-127">RHDSetup.</span></span> <span data-ttu-id="de321-128">**exe**</span><span class="sxs-lookup"><span data-stu-id="de321-128">**exe**</span></span>  
<span data-ttu-id="de321-129">pldok.</span><span class="sxs-lookup"><span data-stu-id="de321-129">pldok.</span></span> <span data-ttu-id="de321-130">**log**</span><span class="sxs-lookup"><span data-stu-id="de321-130">**log**</span></span>

<span data-ttu-id="de321-131">Anche se Windows PowerShell usa terminologia diversa, l'approccio di base per l'uso di Windows PowerShell è lo stesso che usare la finestra di comando: si digita comandi, si includono gli argomenti e i valori di argomento necessari e quindi si preme INVIO per eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="de321-131">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="de321-132">Come notato, tuttavia, Windows PowerShell usa una terminologia diversa rispetto alla shell dei comandi.</span><span class="sxs-lookup"><span data-stu-id="de321-132">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="de321-133">In Windows PowerShell i comandi eseguiti sono noti come *cmdlet*.</span><span class="sxs-lookup"><span data-stu-id="de321-133">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="de321-134">A sua volta, gli argomenti passati a un cmdlet sono noti come *parametri*e i valori passati a un parametro sono noti come *valori di parametro*.</span><span class="sxs-lookup"><span data-stu-id="de321-134">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="de321-135">Le definizioni precedenti sono in qualche modo semplificate.</span><span class="sxs-lookup"><span data-stu-id="de321-135">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="de321-136">I cmdlet sono essenzialmente mini-applicazioni che possono essere eseguite solo all'interno dell'ambiente Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de321-136">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="de321-137">Tuttavia, puoi anche eseguire altri comandi e applicazioni da Windows PowerShell, incluso la maggior parte dei comandi e delle applicazioni che possono essere eseguiti da una finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="de321-137">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="de321-138">Se ad esempio si vuole avviare il blocco note da Windows PowerShell, è sufficiente digitare il codice seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="de321-138">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

    notepad.exe

<span data-ttu-id="de321-139">Quando si tratta di gestire Skype for business online, la maggior parte degli amministratori si affiderà ai cmdlet di Windows PowerShell per eseguire attività amministrative.</span><span class="sxs-lookup"><span data-stu-id="de321-139">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="de321-140">Al momento, esistono pochissimi altri tipi di comandi o applicazioni che possono essere usati per gestire Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="de321-140">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="de321-141">Talvolta i cmdlet di Skype for business online possono essere usati senza argomenti aggiuntivi (, come indicato, gli argomenti sono noti come parametri in Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="de321-141">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="de321-142">Il comando seguente, ad esempio, chiama il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) senza parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="de321-142">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="de321-143">Di per sé, il comando restituisce informazioni su tutti gli utenti di Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="de321-143">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="de321-144">Tuttavia, la maggior parte dei cmdlet di Skype for business online accetta anche i parametri e i valori dei parametri.</span><span class="sxs-lookup"><span data-stu-id="de321-144">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="de321-145">Prendere in considerazione il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="de321-145">Consider the following command:</span></span>

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

<span data-ttu-id="de321-146">Questo comando è costituito da tre parti:</span><span class="sxs-lookup"><span data-stu-id="de321-146">This command consists of three parts:</span></span>

  - <span data-ttu-id="de321-147">Il cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="de321-147">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="de321-148">Il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="de321-148">The Identity parameter.</span></span> <span data-ttu-id="de321-149">Tieni presente che in Windows PowerShell i parametri sono sempre prenotati con un trattino (-).</span><span class="sxs-lookup"><span data-stu-id="de321-149">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="de321-150">Questo significa che, per questo stesso cmdlet, il parametro UnassignedUser verrebbe indicato usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="de321-150">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
        -UnassignedUser
    
    <span data-ttu-id="de321-151">Questo è utile per saperlo, non solo perché i parametri devono essere prenotati con un trattino, ma anche perché si differenzia dalla finestra di comando, in cui gli argomenti sono preattivati con una barra (/):</span><span class="sxs-lookup"><span data-stu-id="de321-151">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ``` 
    /b
    ```

  - <span data-ttu-id="de321-152">Il valore del parametro **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="de321-152">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="de321-153">Questo comando, incidentalmente, restituisce informazioni su un utente specifico: l'utente con l'identità, kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="de321-153">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="de321-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de321-154">See Also</span></span>


<span data-ttu-id="de321-155">[Introduzione a Windows Powershell e Skype for Business online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="de321-155">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

