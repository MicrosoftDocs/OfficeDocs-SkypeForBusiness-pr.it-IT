---
title: Download e installazione di Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: 9c2b0f02d9da7e44cdb5585314c13a6bafbe58c6
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568323"
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="46b91-103">Download e installazione di Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="46b91-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="46b91-p101">[] Se usi Windows 8.1, Windows 8, Windows Server 2012 R2 o Windows Server 2012, dovresti già avere Windows PowerShell 3.0, perché è un'applicazione preinstallata in quei sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="46b91-p101">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0. That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="46b91-p102">Se usi Windows 7 o Windows Server 2008 R2, è possibile che tu stia già usando Windows PowerShell 3.0. Tuttavia, è anche possibile che tu abbia invece la versione 2.0, cioè la versione originariamente in dotazione con quei sistemi operativi. Per sapere quale versione di Microsoft PowerShell stai usando, procedi come segue sul tuo computer con Windows 7 o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="46b91-p102">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0. However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems. To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="46b91-109">Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell** e poi fai clic su **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="46b91-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="46b91-110">Nella console PowerShell, digita il comando seguente e poi premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="46b91-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="46b91-111">La finestra della console mostrerà informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="46b91-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    3.0
    </pre>

    <span data-ttu-id="46b91-p103">Se il numero di versione indicato è 3.0, allora stai usando Windows PowerShell 3.0. Se il numero di versione indicato non è 3.0, allora dovrai installare Windows PowerShell 3.0. Puoi scaricare Windows Management Framework 3.0, che include Windows PowerShell 3.0, dall'[Area download Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span><span class="sxs-lookup"><span data-stu-id="46b91-p103">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0. If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0. You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="46b91-p104">Dopo aver verificato che Windows PowerShell 3.0 è installato, dovrai assicurarti che PowerShell sia configurato per eseguire script remoti. Per farlo, avvia PowerShell come amministratore. Su Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="46b91-p104">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts. To do that, start PowerShell as an administrator. On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="46b91-118">Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell**, fai clic con il pulsante destro su **Windows PowerShell** e poi fai clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="46b91-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="46b91-119">Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.</span><span class="sxs-lookup"><span data-stu-id="46b91-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="46b91-120">Se invece usi Windows 8, procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="46b91-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="46b91-p105">Accedi alla barra Accessi, fai clic su **Cerca**, quindi fai clic con il pulsante destro su **Windows PowerShell**. Per accedere rapidamente alla barra Accessi su qualsiasi computer con Windows 8 (con o senza touch screen), tieni premuto il tasto Windows e premi C.</span><span class="sxs-lookup"><span data-stu-id="46b91-p105">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**. You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="46b91-123">Nella barra degli strumenti nella parte inferiore dello schermo, fai clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="46b91-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="46b91-124">Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.</span><span class="sxs-lookup"><span data-stu-id="46b91-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="46b91-p106">Una volta che PowerShell è in esecuzione, devi modificare il criterio di esecuzione in modo da consentire l'esecuzione di script remoti. Nella console PowerShell, digita il comando seguente e poi premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="46b91-p106">After PowerShell is running, you must change the execution policy to allow the running of remote scripts. In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="46b91-127">Quando si esegue il comando precedente, potrebbe essere visualizzato il messaggio di errore: > *Set-ExecutionPolicy: accesso alla chiave del Registro di sistema ' HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' viene negata.*</span><span class="sxs-lookup"><span data-stu-id="46b91-127">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="46b91-128">Questo messaggio di errore si verifica in genere se non si esegue PowerShell con credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="46b91-128">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="46b91-129">Chiudi la sessione di PowerShell e avvia una nuova sessione come amministratore.</span><span class="sxs-lookup"><span data-stu-id="46b91-129">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="46b91-130">Per verificare che il criterio di esecuzione sia stato configurato correttamente, digita quanto segue al prompt di PowerShell e premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="46b91-130">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="46b91-131">Se ottieni il valore seguente, tutto è configurato correttamente:</span><span class="sxs-lookup"><span data-stu-id="46b91-131">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="46b91-p108">Se al momento non stai usando Windows PowerShell 3.0, dovrai anche scaricare e installare Windows Management Framework 3.0 dall'Area download Microsoft. Si tratta di un pacchetto di installazione che include Windows PowerShell 3.0 e Windows Remote Management (WinRM) 3.0. Questo pacchetto di installazione potrebbe essere necessario se stai usando Windows 7 e non hai ancora aggiornato a Windows PowerShell 3.0. Se stai usando Windows Server 2012, Windows Server 2012 R2, Windows 8 o Windows 8.1, non dovrebbe essere necessario installare Windows PowerShell 3.0. Windows PowerShell 3.0 è preinstallato su quei sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="46b91-p108">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center. This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0. This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0. If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0. Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="46b91-137">Prima di installare Windows Management Framework 3.0:</span><span class="sxs-lookup"><span data-stu-id="46b91-137">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="46b91-p109">Accertati di aver scaricato la versione corretta del pacchetto di installazione. Se stai usando la versione a 64 bit di Windows 7, scarica il file Windows6.1-KB2506143-x64.msu. Se stai usando la versione a 32 bit di Windows 7, scarica il file Windows6.1-KB2506143-x86.msu.</span><span class="sxs-lookup"><span data-stu-id="46b91-p109">Make sure you have downloaded the correct version of the installation package. If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu. If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="46b91-141">Se usi Windows 7 sul tuo computer, accertati di aver installato Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="46b91-141">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="46b91-p110">Se non sei sicuro della versione di Windows in uso o non sei sicuro di aver installato Windows 7 Service Pack 1, fai click su **Start**, fai clic con il pulsante destro su **Computer**, poi fai clic su **Proprietà**. Queste informazioni saranno riportate nella finestra di dialogo Sistema.</span><span class="sxs-lookup"><span data-stu-id="46b91-p110">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**. This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="46b91-144">Per installare Windows Management Framework 3.0, procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="46b91-144">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="46b91-145">Fai doppio clic sul file di installazione .MSU ( **Windows6.1-KB2506143-x64.msu** oppure **Windows6.1-KB2506143-x86.msu**).</span><span class="sxs-lookup"><span data-stu-id="46b91-145">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="46b91-146">Nella procedura guidata Scarica e installa aggiornamenti, nella pagina **Leggere le condizioni di licenza (1 di 1)**, fai clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="46b91-146">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="46b91-147">Una volta completata l'installazione, fai clic su **Riavvia ora** per riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="46b91-147">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="46b91-p111">Una volta riavviato il computer, verifica che Windows PowerShell si avvii e che possa essere eseguito con credenziali di amministratore. Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="46b91-p111">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials. To do this:</span></span>
  
1. <span data-ttu-id="46b91-150">Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell**, fai clic con il pulsante destro su **Windows PowerShell** e poi fai clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="46b91-150">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="46b91-151">Se viene visualizzata la finestra di dialogo Controllo dell'account utente, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.</span><span class="sxs-lookup"><span data-stu-id="46b91-151">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="46b91-p112">Quando viene visualizzata la console PowerShell, verifica che il servizio WinRM sia in esecuzione e sia stato configurato correttamente. Per verificare che il servizio sia in esecuzione, digita il comando seguente al prompt di PowerShell e poi premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="46b91-p112">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly. To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="46b91-154">Verranno quindi visualizzate sullo schermo informazioni sul servizio WinRM:</span><span class="sxs-lookup"><span data-stu-id="46b91-154">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="46b91-155">Se lo Stato del servizio non è "In esecuzione", digita il comando seguente e premi INVIO per avviare il servizio WinRM:</span><span class="sxs-lookup"><span data-stu-id="46b91-155">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="46b91-156">Una volta avviato il servizio, esegui il comando seguente per verificare che WinRM stia usando l'Autenticazione di base:</span><span class="sxs-lookup"><span data-stu-id="46b91-156">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="46b91-157">Lo schermo mostrerà informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="46b91-157">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="46b91-158">Se l'autenticazione di base è stata impostata su true, quindi si è pronti per utilizzare PowerShell per connettersi a Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="46b91-158">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="46b91-159">See also</span><span class="sxs-lookup"><span data-stu-id="46b91-159">Related topics</span></span>
[<span data-ttu-id="46b91-160">Configurare il computer per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46b91-160">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 