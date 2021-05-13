---
title: Migrazione da Skype for Business Online Connector al modulo Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Informazioni su come passare da Skype for Business Online Connector al modulo di PowerShell Teams per gestire Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469718"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="bb931-103">Migrazione da Skype for Business Online Connector al modulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb931-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="bb931-104">Teams Il modulo di PowerShell offre un set completo di cmdlet per la gestione Teams direttamente dalla riga di comando di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb931-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="bb931-105">Gli amministratori non richiedono Skype For Business Online Connector per l'amministrazione Teams utenti.</span><span class="sxs-lookup"><span data-stu-id="bb931-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="bb931-106">Teams amministratore è stato avvisato tramite post del Centro messaggi (MC244740, datato 16 marzo 2021; MC250940, datato 16 aprile 2021) su questa modifica.</span><span class="sxs-lookup"><span data-stu-id="bb931-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="bb931-107">Teams Il modulo di PowerShell usa l'autenticazione moderna, ma il client Windows gestione remota (WinRM) sottostante deve essere configurato per consentire l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="bb931-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="bb931-108">Vedere [Scaricare e installare Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) per istruzioni su come abilitare Gestione remota Windows per l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="bb931-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="bb931-109">Skype for Business Le connessioni Online Connector verranno rifiutate a partire dal 17 maggio 2021.</span><span class="sxs-lookup"><span data-stu-id="bb931-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="bb931-110">Contattare il supporto tecnico Microsoft per assistenza e supporto per la migrazione a Teams modulo di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb931-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="bb931-111">Come eseguire la migrazione</span><span class="sxs-lookup"><span data-stu-id="bb931-111">How to Migrate</span></span>

<span data-ttu-id="bb931-112">La migrazione dall'uso di Skype for Business Online Connector Teams modulo di PowerShell è semplice e semplice.</span><span class="sxs-lookup"><span data-stu-id="bb931-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="bb931-113">La procedura seguente spiega come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="bb931-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="bb931-114">Installare il modulo di PowerShell Teams più recente.</span><span class="sxs-lookup"><span data-stu-id="bb931-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="bb931-115">Per la procedura, vedere [Installare Microsoft Teams Powershell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="bb931-115">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="bb931-116">Disinstallare Skype For Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="bb931-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="bb931-117">A questo scopo, nel Pannello di controllo passare a Programmi e funzionalità **,** selezionare Skype for Business **Online, Windows PowerShell modulo** e quindi selezionare **Disinstalla**.</span><span class="sxs-lookup"><span data-stu-id="bb931-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>
3. <span data-ttu-id="bb931-118">Negli script di PowerShell modificare il nome del modulo a cui si fa riferimento ```Import-Module``` da</span><span class="sxs-lookup"><span data-stu-id="bb931-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="bb931-119">`SkypeOnlineConnector` o `LyncOnlineConnector` su `MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="bb931-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="bb931-120">Ad esempio, passare `Import-Module -Name SkypeOnlineConnector` a `Import-Module -Name MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="bb931-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="bb931-121">Quando si Teams modulo di PowerShell 2.0 o versione successiva, aggiornare gli script che fanno riferimento `New-CsOnlineSession` a `Connect-MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="bb931-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="bb931-122">`Import-PsSession`non è più necessario stabilire una sessione remota di PowerShell Skype for Business online, perché questa operazione viene eseguita implicitamente quando si usa `Connect-MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="bb931-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="bb931-123">Supporto online</span><span class="sxs-lookup"><span data-stu-id="bb931-123">Online Support</span></span>

<span data-ttu-id="bb931-124">È possibile risparmiare tempo avviando la richiesta di servizio online.</span><span class="sxs-lookup"><span data-stu-id="bb931-124">Save time by starting your service request online.</span></span> <span data-ttu-id="bb931-125">Microsoft ti aiuterà a trovare una soluzione o a connetterti al supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="bb931-125">We'll help you find a solution or connect you to technical support.</span></span>
1.  <span data-ttu-id="bb931-126">Passare all'interfaccia di amministrazione in [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="bb931-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="bb931-127">Se viene visualizzato un messaggio che indica che non si è autorizzati ad accedere a questa pagina o a eseguire questa azione, non si è amministratori. Who autorizzazioni di amministratore nella mia azienda?</span><span class="sxs-lookup"><span data-stu-id="bb931-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>
2.  <span data-ttu-id="bb931-128">Selezionare la casella **di controllo Serve assistenza?** .</span><span class="sxs-lookup"><span data-stu-id="bb931-128">Select the **Need help**? button.</span></span>
3.  <span data-ttu-id="bb931-129">Nella finestra **Serve aiuto?** , dicci per cosa hai bisogno di aiuto e quindi premi INVIO.</span><span class="sxs-lookup"><span data-stu-id="bb931-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>
4.  <span data-ttu-id="bb931-130">Se i risultati non sono utili, selezionare **Contatta il supporto.**</span><span class="sxs-lookup"><span data-stu-id="bb931-130">If the results don't help, select **Contact support**.</span></span>
5.  <span data-ttu-id="bb931-131">Immettere una descrizione del problema, confermare il numero di contatto e l'indirizzo di posta elettronica, selezionare il metodo di contatto preferito e quindi **selezionare Contattami**.</span><span class="sxs-lookup"><span data-stu-id="bb931-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="bb931-132">Il tempo di attesa previsto è indicato nel campo Serve aiuto? riquadro.</span><span class="sxs-lookup"><span data-stu-id="bb931-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb931-133">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bb931-133">Related topics</span></span>

[<span data-ttu-id="bb931-134">Installare Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb931-134">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="bb931-135">Gestire Teams con Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb931-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="bb931-136">Teams Note sulla versione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb931-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="bb931-137">Microsoft Teams di cmdlet</span><span class="sxs-lookup"><span data-stu-id="bb931-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="bb931-138">Skype for Business cmdlet</span><span class="sxs-lookup"><span data-stu-id="bb931-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
