---
title: Scaricare e installare Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Scaricare, installare e usare Windows PowerShell 5.1 per creare una sessione remota di PowerShell che si connette a Skype for Business online.
ms.openlocfilehash: 1bea6ab4081acbc5efa07c3ec0e60677fe60a326
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692911"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="173ce-103">Scaricare e installare Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="173ce-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="173ce-104">Se si usa Aggiornamento dell'anniversario di Windows 10 o Windows Server 2016, Windows PowerShell 5.1 dovrebbe essere già disponibile</span><span class="sxs-lookup"><span data-stu-id="173ce-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="173ce-105">perché questa applicazione viene preinstallata con tali sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="173ce-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="173ce-106">Per determinare la versione di Microsoft PowerShell in uso, eseguire la procedura seguente nel computer Windows 7, Windows Server 2008 R2 o Windows Server 2012 in uso:</span><span class="sxs-lookup"><span data-stu-id="173ce-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="173ce-107">Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell** e poi fai clic su **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="173ce-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="173ce-108">Nella console PowerShell, digita il comando seguente e poi premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="173ce-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="173ce-109">La finestra della console mostrerà informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="173ce-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="173ce-110">Se il numero di versione indicato è 5.1, l'applicazione in esecuzione è Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="173ce-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="173ce-111">Se il numero di versione indicato non è 5.1, è necessario installare Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="173ce-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="173ce-112">È possibile scaricare Windows Management Framework 5.1, che include Windows PowerShell 5.1, dall'[Area download Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="173ce-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="173ce-113">Dopo aver verificato che Windows PowerShell 5.1 è installato, è necessario verificare che PowerShell sia configurato per l'esecuzione di script remoti.</span><span class="sxs-lookup"><span data-stu-id="173ce-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="173ce-114">Per farlo, avvia PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="173ce-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="173ce-115">Su Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="173ce-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="173ce-116">Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell**, fai clic con il pulsante destro su **Windows PowerShell** e poi fai clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="173ce-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="173ce-117">Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fare clic su **Sì** per verificare che PowerShell venga eseguito con credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="173ce-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="173ce-118">Se invece usi Windows 8, procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="173ce-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="173ce-p104">Accedi alla barra Accessi, fai clic su **Cerca**, quindi fai clic con il pulsante destro su **Windows PowerShell**. Per accedere rapidamente alla barra Accessi su qualsiasi computer con Windows 8 (con o senza touch screen), tieni premuto il tasto Windows e premi C.</span><span class="sxs-lookup"><span data-stu-id="173ce-p104">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="173ce-121">Nella barra degli strumenti nella parte inferiore dello schermo, fai clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="173ce-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="173ce-122">Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.</span><span class="sxs-lookup"><span data-stu-id="173ce-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="173ce-p105">Una volta che PowerShell è in esecuzione, devi modificare il criterio di esecuzione in modo da consentire l'esecuzione di script remoti. Nella console PowerShell, digita il comando seguente e poi premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="173ce-p105">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="173ce-125">Quando si esegue il comando procedente, potrebbe essere visualizzato il messaggio di errore seguente:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' del Registro di sistema*.</span><span class="sxs-lookup"><span data-stu-id="173ce-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="173ce-126">Questo messaggio di errore viene in genere visualizzato se non si esegue PowerShell con credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="173ce-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="173ce-127">Chiudi la sessione di PowerShell e avvia una nuova sessione come amministratore.</span><span class="sxs-lookup"><span data-stu-id="173ce-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="173ce-128">Per verificare che il criterio di esecuzione sia stato configurato correttamente, digita quanto segue al prompt di PowerShell e premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="173ce-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="173ce-129">Se ottieni il valore seguente, tutto è configurato correttamente:</span><span class="sxs-lookup"><span data-stu-id="173ce-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="173ce-130">Se al momento non si sta eseguendo Windows PowerShell 5.1, sarà necessario scaricare e installare anche Windows Management Framework 5.1 dall'Area download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="173ce-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="173ce-131">Si tratta di un pacchetto di installazione che include Windows PowerShell 5.1 e Windows Remote Management (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="173ce-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="173ce-132">Questo pacchetto di installazione potrebbe essere necessario, ad esempio, se si esegue Windows 7 SP1e non è ancora stato eseguito l'aggiornamento a Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="173ce-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="173ce-133">Se si esegue Windows Server 2016 o Aggiornamento dell'anniversario di Windows 10, non dovrebbe essere necessario installare Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="173ce-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="173ce-134">Windows PowerShell 5.1 viene infatti preinstallato in tali sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="173ce-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="173ce-135">Prima di installare Windows Management Framework 5.1:</span><span class="sxs-lookup"><span data-stu-id="173ce-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="173ce-136">Assicurarsi di avere scaricato la versione corretta del pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="173ce-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="173ce-137">Se si esegue la versione a 64 bit di Windows 7 SP1, scaricare il file Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="173ce-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="173ce-138">Se si esegue la versione a 32 bit di Windows 7, scaricare il file Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="173ce-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="173ce-139">Se usi Windows 7 sul tuo computer, accertati di aver installato Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="173ce-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="173ce-p109">Se non sei sicuro della versione di Windows in uso o non sei sicuro di aver installato Windows 7 Service Pack 1, fai click su **Start**, fai clic con il pulsante destro su **Computer**, poi fai clic su **Proprietà**. Queste informazioni saranno riportate nella finestra di dialogo Sistema.</span><span class="sxs-lookup"><span data-stu-id="173ce-p109">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="173ce-142">Per installare Windows Management Framework 5.1, completare la procedura descritta in [Installare e configurare WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="173ce-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="173ce-p110">Una volta riavviato il computer, verifica che Windows PowerShell si avvii e che possa essere eseguito con credenziali di amministratore. Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="173ce-p110">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="173ce-145">Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell**, fai clic con il pulsante destro su **Windows PowerShell** e poi fai clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="173ce-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="173ce-146">Se viene visualizzata la finestra di dialogo Controllo dell'account utente, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.</span><span class="sxs-lookup"><span data-stu-id="173ce-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="173ce-p111">Quando viene visualizzata la console PowerShell, verifica che il servizio WinRM sia in esecuzione e sia stato configurato correttamente. Per verificare che il servizio sia in esecuzione, digita il comando seguente al prompt di PowerShell e poi premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="173ce-p111">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="173ce-149">Verranno quindi visualizzate sullo schermo informazioni sul servizio WinRM:</span><span class="sxs-lookup"><span data-stu-id="173ce-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="173ce-150">Se lo Stato del servizio non è "In esecuzione", digita il comando seguente e premi INVIO per avviare il servizio WinRM:</span><span class="sxs-lookup"><span data-stu-id="173ce-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="173ce-151">Una volta avviato il servizio, esegui il comando seguente per verificare che WinRM stia usando l'Autenticazione di base:</span><span class="sxs-lookup"><span data-stu-id="173ce-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="173ce-152">Lo schermo mostrerà informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="173ce-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="173ce-153">Se l'autenticazione di base è stata impostata su true, è possibile usare PowerShell per connettersi a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="173ce-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="173ce-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="173ce-154">Related topics</span></span>
[<span data-ttu-id="173ce-155">Configurare il computer per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="173ce-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
