---
title: Download e installazione del modulo Skype for Business Online Connector
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 'Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online. '
ms.openlocfilehash: 7e97bc31d85370919eec7c50fae01d00f5b1ddac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284711"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="81c0b-103">Download e installazione del modulo Skype for Business Online Connector</span><span class="sxs-lookup"><span data-stu-id="81c0b-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="81c0b-104">[] Modulo del connettore di Skype for Business Online include il cmdlet **New-CsOnlineSession**, che consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="81c0b-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="81c0b-105">Questo modulo, supportato solo in computer a 64 bit (vedere [configurare il computer per la gestione di Skype for business online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md) per altre informazioni), può essere scaricato dall'area download Microsoft [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="81c0b-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="81c0b-106">Scarica il file SkypeOnlinePowershell.exe, poi procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="81c0b-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="81c0b-107">Fai doppio clic sul file **SkypeOnlinePowershell.exe**.</span><span class="sxs-lookup"><span data-stu-id="81c0b-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="81c0b-p102">Nell'installazione guidata di Skype for Business online, Windows PowerShell, nella pagina **Condizioni di licenza software Microsoft**, seleziona **Accetto i termini del Contratto di licenza**, poi fai clic su **Installa**. Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fai clic su **Sì** per continuare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="81c0b-p102">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**. If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="81c0b-110">Nella pagina **Skype for Business Online, modulo Windows PowerShell completato**, fai clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="81c0b-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="81c0b-p103">Il programma di installazione copia Modulo del connettore di Skype for Business Online (e il cmdlet **New-CsOnlineSession** ) sul tuo computer. Per accedere al modulo, avvia una sessione di Windows PowerShell con credenziali di amministratore ed esegui il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="81c0b-p103">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer. To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="81c0b-p104">Se non vuoi digitare questo comando ogni volta che avvii Windows PowerShell, puoi aggiungere il comando al profilo di Windows PowerShell. Per farlo, digita il comando seguente al prompt di Windows PowerShell e premi INVIO:</span><span class="sxs-lookup"><span data-stu-id="81c0b-p104">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile. To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="81c0b-115">Quando viene visualizzato Blocco note, aggiungi la riga seguente dopo i comandi già presenti nel profilo (se ce ne sono):</span><span class="sxs-lookup"><span data-stu-id="81c0b-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="81c0b-p105">Salva il file. La prossima volta che avvierai Windows PowerShell, Modulo del connettore di Skype for Business Online verrà importato automaticamente. Ricorda che riceverai un messaggio d'errore, e il modulo non verrà caricato, se non stai eseguendo Windows PowerShell con credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="81c0b-p105">Save the file. The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported. Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="81c0b-p106">Oltre a installare Modulo del connettore di Skype for Business Online, SkypeOnlinePowershell.exe installa anche tre componenti aggiuntivi: 1) la libreria IDCRL (Identity Service Client Runtime Library), che gestisce l'autenticazione del client con Skype for Business online; 2) .NET Framework 4.5; e 3) pacchetto Microsoft Visual C++ 2012 Redistributable (x64) Package (versione 11.0.50727). .NET Framework 4.5 offre l'infrastruttura necessaria per compilare ed eseguire le applicazioni .NET, compresa Windows PowerShell. Visual C++ Redistributable Package installa i componenti di runtime di Visual C++ per i computer in cui non è installato Microsoft Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="81c0b-p106">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727). .NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell. The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="81c0b-122">Per verificare il numero di versione del modulo Connector attualmente installato sul computer, apri Pannello di controllo, apri **Programmi e funzionalità** e verifica il numero di versione di **Skype for Business Online, modulo Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="81c0b-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="81c0b-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="81c0b-123">Related topics</span></span>
[<span data-ttu-id="81c0b-124">Configurare il computer per la gestione di Skype for business online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81c0b-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
