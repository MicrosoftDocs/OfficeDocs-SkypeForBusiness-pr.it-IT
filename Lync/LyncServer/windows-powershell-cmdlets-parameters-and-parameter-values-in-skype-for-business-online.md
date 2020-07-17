---
title: Cmdlet di Windows PowerShell, parametri e valori dei parametri in Skype for business online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c7b04c428297e74d0910a42c4136bf4a06dacd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="1d6bd-102">Cmdlet di Windows PowerShell, parametri e valori dei parametri in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="1d6bd-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d6bd-103">_**Ultimo argomento modificato:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="1d6bd-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="1d6bd-104">Se si ha familiarità con la finestra di comando trovata in tutte le versioni di Windows (o se si ha familiarità con MS-DOS), si avrà un vantaggio quando si tratta di imparare a usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="1d6bd-105">Nella finestra di comando, digitare un comando e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="1d6bd-106">In risposta, il computer esegue un comando o un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="1d6bd-107">Ad esempio, per restituire informazioni su tutti i file e le cartelle nella directory corrente, digitare questo comando al prompt dei comandi e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="1d6bd-108">A sua scelta, vengono riportate informazioni su tutti i file e le cartelle presenti nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

```console
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

<span data-ttu-id="1d6bd-109">Questo è un esempio di un risultato quando si digita solo il nome di un comando o di un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="1d6bd-110">Tuttavia, molti dei comandi eseguiti dall'interno della finestra di comando accettano anche *argomenti*.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="1d6bd-111">Gli argomenti sono altre informazioni passate al comando, che modificano il comportamento del comando.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="1d6bd-112">Ad esempio, se si desidera visualizzare solo i nomi dei file e delle cartelle nella directory corrente, non sono presenti altre informazioni, quali le dimensioni del file o della cartella, oppure la data e l'ora in cui è stata creata la cartella o la cartella.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="1d6bd-113">In questo caso, è necessario aggiungere l'argomento **/b** quando si esegue il comando dir:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="1d6bd-114">Quando si include l'argomento **/b** , il comando **dir** riporta solo i nomi delle cartelle e dei file trovati nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

```console
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
```

<span data-ttu-id="1d6bd-115">Nel comando precedente, l'argomento **/b** è l'unica informazione necessaria per limitare i dati restituiti ai nomi di file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="1d6bd-116">Questo accade spesso con i comandi della riga di comando: la mera presenza di un argomento è tutto ciò che è necessario per modificare il comportamento del comando.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="1d6bd-117">(Ovvero, è necessario includere l'argomento **/b** per nascondere altre informazioni oppure escludere l'argomento **/b** per visualizzare le informazioni aggiuntive). In altri casi, tuttavia, è necessario specificare un *valore di argomento*.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="1d6bd-118">Un valore di argomento è costituito da informazioni aggiuntive passate all'argomento stesso.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="1d6bd-119">Ad esempio, l'argomento **/o** consente di specificare in che modo si desidera che il comando dir ordini i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="1d6bd-120">Tra le altre opzioni, è possibile utilizzare il valore dell'argomento **e** per ordinare in base all'estensione di file o al valore dell'argomento **s** per ordinare in base alle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="1d6bd-121">Ad esempio, questo comando consente di ordinare i dati restituiti in base all'estensione del file.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="1d6bd-122">Si noti che il valore dell'argomento **e** è incluso subito dopo l'argomento **/o** :</span><span class="sxs-lookup"><span data-stu-id="1d6bd-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="1d6bd-123">Utilizzando la cartella di esempio, i dati restituiti avranno l'aspetto seguente, con i file ordinati in ordine alfabetico in base all'estensione dei file:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

```console
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

<span data-ttu-id="1d6bd-124">In alternativa, per individuare esattamente gli elementi di cui si parla:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="1d6bd-125">Anche se Windows PowerShell utilizza una terminologia diversa, l'approccio di base all'utilizzo di Windows PowerShell equivale all'utilizzo della finestra di comando: si digitano comandi, si includono argomenti e valori di argomento necessari e quindi si preme INVIO per eseguire tali comandi.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="1d6bd-126">Come indicato, tuttavia, Windows PowerShell utilizza una terminologia diversa da quella utilizzata dalla shell dei comandi.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="1d6bd-127">In Windows PowerShell, i comandi eseguiti sono noti come *cmdlet*.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="1d6bd-128">A sua insaputa, gli argomenti passati a un cmdlet sono noti come *parametri*e i valori passati a un parametro sono noti come *valori dei*parametri.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="1d6bd-129">Le definizioni precedenti sono piuttosto semplificate.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="1d6bd-130">I cmdlet sono essenzialmente mini-applicazioni che possono essere eseguite solo all'interno dell'ambiente di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="1d6bd-131">Tuttavia, è anche possibile eseguire altri comandi e applicazioni dall'interno di Windows PowerShell, inclusa la maggior parte dei comandi e delle applicazioni che possono essere eseguiti da una finestra di comando.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="1d6bd-132">Ad esempio, se si desidera avviare il blocco note dall'interno di Windows PowerShell, è sufficiente digitare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="1d6bd-133">Quando si tratta di gestire Skype for business online, la maggior parte degli amministratori si affiderà ai cmdlet di Windows PowerShell per eseguire le attività amministrative.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="1d6bd-134">Al momento, esistono pochissimi altri tipi di comandi o applicazioni che possono essere utilizzati per gestire Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="1d6bd-135">In alcuni casi, è possibile utilizzare i cmdlet Skype for business online senza argomenti aggiuntivi (gli argomenti, come indicato, sono noti come parametri in Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1d6bd-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="1d6bd-136">Ad esempio, il comando seguente consente di chiamare il cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) senza parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="1d6bd-137">Da solo, il comando restituisce le informazioni su tutti gli utenti di Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="1d6bd-138">Tuttavia, la maggior parte dei cmdlet di Skype for business online accettano anche parametri (e valori dei parametri).</span><span class="sxs-lookup"><span data-stu-id="1d6bd-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="1d6bd-139">Si consideri il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="1d6bd-140">Questo comando è costituito da tre parti:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="1d6bd-141">Il cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="1d6bd-142">Il parametro Identity.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-142">The Identity parameter.</span></span> <span data-ttu-id="1d6bd-143">Si noti che, in Windows PowerShell, i parametri sono sempre preattivati con un trattino (-).</span><span class="sxs-lookup"><span data-stu-id="1d6bd-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="1d6bd-144">Questo significa che, per questo stesso cmdlet, il parametro UnassignedUser verrebbe indicato utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="1d6bd-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="1d6bd-145">Questo è utile per sapere, non solo perché i parametri devono essere precostituiti con un trattino, ma anche perché questo è diverso dalla finestra di comando, in cui gli argomenti sono prefaced con una barra (/):</span><span class="sxs-lookup"><span data-stu-id="1d6bd-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="1d6bd-146">Il valore del parametro **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="1d6bd-147">Questo comando, tra l'altro, restituisce informazioni su un utente specifico, ovvero l'utente con l'identità kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1d6bd-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1d6bd-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d6bd-148">See Also</span></span>


<span data-ttu-id="1d6bd-149">[Introduzione a Windows PowerShell e Skype for business online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1d6bd-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

