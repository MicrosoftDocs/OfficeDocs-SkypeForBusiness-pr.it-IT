---
title: Ottenere i client per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i vari client disponibili per Microsoft Teams, che includono client Web, desktop (per Windows e Mac) e per dispositivi mobili (Android e iOS).
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e423bedc05dbbf303ecfdbf569ff9e1b096bd3d7
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327838"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="d8fa2-103">Ottenere i client per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d8fa2-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="d8fa2-104">Microsoft Teams dispone di client per PC (Windows, Mac e Linux), Web e dispositivi mobili (Android e iOS).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="d8fa2-105">Per questi client è necessaria una connessione Internet attiva e la modalità offline non è supportata.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="d8fa2-106">Dal 29 novembre 2018 non è più possibile usare l'app Microsoft Teams per Windows 10 S (anteprima) disponibile in Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="d8fa2-107">In alternativa, sui dispositivi che eseguono la modalità S di Windows 10 si può scaricare e installare il client desktop di Teams.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="d8fa2-108">Per scaricare il client desktop, passare alla pagina [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="d8fa2-109">Le build MSI del client desktop di Teams non sono ancora disponibili per i dispositivi che eseguono Windows 10 in modalità S.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="d8fa2-110">Per altre informazioni, vedere [Ti presentiamo Windows 10 in modalità S](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="d8fa2-111">Client desktop</span><span class="sxs-lookup"><span data-stu-id="d8fa2-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="d8fa2-112">Guardare la sessione seguente per informazioni sui vantaggi offerti dal client desktop per Windows e su come pianificare ed eseguire la distribuzione: [Teams Windows Desktop Client](https://aka.ms/teams-clients) (client desktop di Teams per Windows).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="d8fa2-113">Il client desktop di Microsoft Teams è un'applicazione autonoma ed è anche [disponibile in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="d8fa2-114">Teams è disponibile per le versioni a 32 e 64 bit di Windows (8.1 o successiva) e di Windows Server (2012 R2 o successiva), oltre che per macOS (10.10 o versione successiva) e Linux (nei formati `.deb` e `.rpm`).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-114">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later) and Windows Server (2012 R2 or later), as well as for macOS (10.10 or later) and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="d8fa2-115">In Windows, Teams richiede .NET Framework 4.5 o versione successiva. Se non è disponibile, il programma di installazione di Teams offrirà la possibilità di installarlo.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="d8fa2-116">In Linux, i gestori di pacchetti come `apt` e `yum` cercheranno di installare automaticamente tutti i requisiti.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-116">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="d8fa2-117">Se questo non avviene, prima di installare Team su Linux sarà necessario installare i requisiti segnalati.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="d8fa2-118">I client desktop supportano le comunicazioni in tempo reale (audio, video e condivisione del contenuto) per riunioni del team, chiamate di gruppo e chiamate private tra due persone.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="d8fa2-119">I client desktop possono essere scaricati e installati direttamente dagli utenti finali dalla pagina [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754), se hanno le autorizzazioni locali appropriate. I diritti di amministratore non sono necessari per installare il client di Teams in un PC, ma lo sono per installarlo in un Mac.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="d8fa2-120">Gli amministratori IT possono usare il proprio metodo preferito per distribuire i file di installazione nei computer dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="d8fa2-121">Alcuni esempi sono Microsoft Endpoint Configuration Manager in Windows o Jamf Pro in macOS.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-121">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="d8fa2-122">Per ottenere il pacchetto MSI per la distribuzione in Windows, vedere [Installare Microsoft Teams con MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="d8fa2-123">La distribuzione tramite questi meccanismi è necessaria solo per l'installazione iniziale dei client di Microsoft Teams e non per gli aggiornamenti futuri.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="d8fa2-124">Windows</span><span class="sxs-lookup"><span data-stu-id="d8fa2-124">Windows</span></span>

<span data-ttu-id="d8fa2-125">L'installazione di Microsoft Teams per Windows include programmi di installazione scaricabili con architettura a 32 bit e a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="d8fa2-126">L'architettura (a 32 bit o a 64 bit) di Microsoft Teams è indipendente dall'architettura di Windows e di Office installata.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="d8fa2-127">Il client Windows viene distribuito nella cartella AppData, all'interno del profilo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="d8fa2-128">La distribuzione nel profilo locale dell'utente consente di installare il client senza bisogno di diritti elevati.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="d8fa2-129">Il client Windows utilizza le posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="d8fa2-130">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="d8fa2-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="d8fa2-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="d8fa2-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="d8fa2-132">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="d8fa2-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="d8fa2-133">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="d8fa2-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="d8fa2-134">Quando gli utenti avviano per la prima volta una chiamata usando il client di Microsoft Teams, potrebbe comparire un avviso relativo alle impostazioni di Windows Firewall in cui si chiede di consentire la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="d8fa2-135">Si potrebbe anche indicare agli utenti di ignorare il messaggio, perché la chiamata funzionerà anche se l'avviso viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Screenshot di una finestra di dialogo Avviso di sicurezza di Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="d8fa2-137">La configurazione di Windows Firewall verrà modificata anche se il messaggio viene ignorato selezionando "Annulla".</span><span class="sxs-lookup"><span data-stu-id="d8fa2-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="d8fa2-138">Verranno create due regole in entrata per teams.exe, con l'azione Blocca per i protocolli TCP e UDP.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="d8fa2-139">Mac</span><span class="sxs-lookup"><span data-stu-id="d8fa2-139">Mac</span></span>

<span data-ttu-id="d8fa2-140">Gli utenti Mac possono installare Teams con un file di installazione PKG per i computer che eseguono macOS.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="d8fa2-141">Per installare il client Mac è necessario l'accesso amministrativo.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="d8fa2-142">Il client macOS viene installato nella cartella /Applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="d8fa2-143">Installare Teams usando il file PKG</span><span class="sxs-lookup"><span data-stu-id="d8fa2-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="d8fa2-144">Nella pagina di download di [Teams](https://teams.microsoft.com/downloads), in **Mac** fare clic su **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="d8fa2-145">Fare doppio clic sul file PKG.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="d8fa2-146">Seguire la procedura guidata per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="d8fa2-147">Teams verrà installato nella cartella /Applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="d8fa2-148">Si tratta di un'installazione a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="d8fa2-149">Durante l'installazione verranno richieste le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="d8fa2-150">L'utente deve immettere le credenziali di amministratore, indipendentemente dal fatto di esserlo o meno.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="d8fa2-151">Se un utente ha un'installazione DMG di Teams e vuole sostituirla con l'installazione PKG, deve procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="d8fa2-152">Uscire dall'app Teams.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="d8fa2-153">Disinstallare l'app Teams.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="d8fa2-154">Installare il file PKG.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-154">Install the PKG file.</span></span>

<span data-ttu-id="d8fa2-155">Gli amministratori IT possono usare la distribuzione gestita di Teams per distribuire i file di installazione in tutti i Mac dell'organizzazione, ad esempio Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="d8fa2-156">Se si verificano problemi durante l'installazione del file PKG, inviare una segnalazione a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="d8fa2-157">Nella sezione **Feedback** alla fine di questo articolo fare clic su **Feedback sul prodotto**.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="d8fa2-158">Linux</span><span class="sxs-lookup"><span data-stu-id="d8fa2-158">Linux</span></span>

<span data-ttu-id="d8fa2-159">Gli utenti potranno installare pacchetti Linux nativi nei formati `.deb` e `.rpm`.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="d8fa2-160">Installando il pacchetto DEB o RPM verrà installato automaticamente il repository del pacchetto</span><span class="sxs-lookup"><span data-stu-id="d8fa2-160">Installing the DEB or RPM package will automatically install the package repository</span></span>
- <span data-ttu-id="d8fa2-161">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="d8fa2-161">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="d8fa2-162">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="d8fa2-162">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="d8fa2-163">La chiave di firma per abilitare l'aggiornamento automatico usando il gestore pacchetti del sistema viene installata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-163">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="d8fa2-164">Tuttavia, è disponibile anche alla pagina: (https://packages.microsoft.com/keys/microsoft.asc).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-164">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="d8fa2-165">Microsoft Teams viene aggiornato mensilmente. Se il repository è stato installato correttamente, il gestore pacchetti del sistema dovrebbe gestire l'aggiornamento automatico esattamente come per gli altri pacchetti presenti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-165">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="d8fa2-166">Se si trova un bug, inviarlo usando `Report a Problem` all'interno del client.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-166">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="d8fa2-167">Per i problemi noti, vedere [Problemi noti](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-167">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="d8fa2-168">Per il supporto di Teams per Linux è possibile usare il [canale di supporto del forum per Linux su Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-168">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="d8fa2-169">Assicurarsi di usare il tag `teams-linux` quando si pubblicano le domande.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-169">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="d8fa2-170">Installare Teams usando il pacchetto DEB</span><span class="sxs-lookup"><span data-stu-id="d8fa2-170">Install Teams using DEB package</span></span>

1. <span data-ttu-id="d8fa2-171">Scaricare il pacchetto da https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-171">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="d8fa2-172">Installare usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-172">Install using one of the following:</span></span>  
    - <span data-ttu-id="d8fa2-173">Aprire lo strumento di gestione dei pacchetti appropriato e seguire il processo guidato di installazione delle app di Linux.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-173">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="d8fa2-174">Se si preferisce usare Terminale, digitare: `sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="d8fa2-174">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="d8fa2-175">È possibile avviare Teams tramite Attività o tramite Terminale digitando `Teams`.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-175">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="d8fa2-176">Installare Team usando il pacchetto RPM</span><span class="sxs-lookup"><span data-stu-id="d8fa2-176">Install Teams using RPM package</span></span>

1. <span data-ttu-id="d8fa2-177">Scaricare il pacchetto da https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-177">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="d8fa2-178">Installare usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-178">Install using one of the following:</span></span>
    - <span data-ttu-id="d8fa2-179">Aprire lo strumento di gestione dei pacchetti appropriato e seguire il processo guidato di installazione delle app di Linux.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-179">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="d8fa2-180">Se si preferisce usare Terminale, digitare: `sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="d8fa2-180">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="d8fa2-181">È possibile avviare Teams tramite Attività o tramite Terminale digitando `Teams`.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-181">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="d8fa2-182">Eseguire l'installazione manualmente dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="d8fa2-182">Install manually from the command line</span></span>

<span data-ttu-id="d8fa2-183">Installare manualmente nelle distribuzioni Debian e Ubuntu:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-183">Install manually on Debian and Ubuntu distributions:</span></span>
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="d8fa2-184">Installare manualmente nelle distribuzioni basate su RHEL, Fedora e CentOS:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-184">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="d8fa2-185">In alternativa, per usare yum anziché dnf:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-185">Alternatively, to use yum instead of dnf:</span></span>
```
yum check-update
sudo yum install teams
```

<span data-ttu-id="d8fa2-186">Installare manualmente nelle distribuzioni basate su openSUSE:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-186">Install manually on openSUSE based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="d8fa2-187">Client Web</span><span class="sxs-lookup"><span data-stu-id="d8fa2-187">Web client</span></span> 

<span data-ttu-id="d8fa2-188">Il client Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) è un client completo di tutte le funzionalità che è possibile usare da più browser.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-188">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="d8fa2-189">Il client Web supporta le chiamate e le riunioni tramite webRTC, quindi non sono necessari plug-in o download per eseguire Teams in un Web browser.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-189">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="d8fa2-190">Il browser deve essere configurato in modo da consentire i cookie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-190">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="d8fa2-191">Il client Web rileva la versione del browser al momento della connessione a [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span><span class="sxs-lookup"><span data-stu-id="d8fa2-191">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="d8fa2-192">Se viene rilevata una versione del browser non supportata, blocca l'accesso all'interfaccia Web e invita l'utente a scaricare il client desktop o l'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-192">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="d8fa2-193">Client per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="d8fa2-193">Mobile clients</span></span>

<span data-ttu-id="d8fa2-194">Le app Microsoft Teams per dispositivi mobili sono disponibili per Android e iOS. Sono pensate per gli utenti che partecipano a conversazioni basate su chat mentre sono in movimento e consentono l'esecuzione di chiamate audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-194">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="d8fa2-195">Per le app per dispositivi mobili, visitare Google Play Store e l'App Store di Apple.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-195">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="d8fa2-196">L'app per Windows Phone è stata ritirata il 20 luglio 2018 e potrebbe non funzionare più.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-196">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="d8fa2-197">Ecco come [ottenere Teams per Android](get-teams-android-in-china.md) in Cina.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-197">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span> 

<span data-ttu-id="d8fa2-198">Le piattaforme supportate dalle app Microsoft Teams per dispositivi mobili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8fa2-198">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="d8fa2-199">**Android**: il supporto è limitato alle ultime quattro versioni principali di Android.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-199">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="d8fa2-200">Quando viene rilasciata una nuova versione principale di Android, sono ufficialmente supportate la nuova versione e le tre versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-200">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="d8fa2-201">**iOS**: il supporto è limitato alle ultime due versioni principali di iOS.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-201">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="d8fa2-202">Quando viene rilasciata una nuova versione principale di iOS, sono ufficialmente supportate la nuova versione e la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-202">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="d8fa2-203">Perché Teams funzioni come previsto, la versione per dispositivi mobili deve essere disponibile al pubblico.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-203">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="d8fa2-204">Le app per dispositivi mobili vengono distribuite e aggiornate solo tramite l'app store della piattaforma corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-204">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="d8fa2-205">La distribuzione delle app per dispositivi mobili tramite MDM o sideload non è supportata da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-205">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="d8fa2-206">Dopo l'installazione in una piattaforma mobile supportata, l'app Teams per dispositivi mobili sarà supportata purché la versione rientri entro tre mesi dalla versione corrente.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-206">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Icona che descrive un punto decisionale](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="d8fa2-208">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="d8fa2-208">Decision Point</span></span>         |<span data-ttu-id="d8fa2-209">Ci sono limitazioni che impediscono agli utenti di installare il client di Microsoft Teams appropriato nei dispositivi?</span><span class="sxs-lookup"><span data-stu-id="d8fa2-209">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Icona che descrive i passaggi successivi](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="d8fa2-211">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d8fa2-211">Next Steps</span></span>         |<span data-ttu-id="d8fa2-212">Se l'organizzazione limita l'installazione di software, accertarsi che la procedura sia compatibile con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-212">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="d8fa2-213">Nota: i diritti di amministratore non sono necessari per l'installazione del client in un PC ma sono necessari per l'installazione in un Mac.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-213">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="d8fa2-214">Gestione degli aggiornamenti del client</span><span class="sxs-lookup"><span data-stu-id="d8fa2-214">Client update management</span></span>

<span data-ttu-id="d8fa2-215">I client vengono aggiornati automaticamente dal servizio Microsoft Teams e non è necessario alcun intervento da parte dell'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-215">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="d8fa2-216">Se è disponibile un aggiornamento, il client lo scarica automaticamente e, quando l'app resta inattiva per un certo periodo di tempo, avvia il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-216">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="d8fa2-217">Configurazioni lato client</span><span class="sxs-lookup"><span data-stu-id="d8fa2-217">Client-side configurations</span></span>

<span data-ttu-id="d8fa2-218">Attualmente non sono disponibili opzioni supportate per configurare il client tramite amministrazione del tenant, PowerShell, oggetti Criteri di gruppo o il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-218">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="d8fa2-219">Impostazioni di notifica</span><span class="sxs-lookup"><span data-stu-id="d8fa2-219">Notification settings</span></span>

<span data-ttu-id="d8fa2-220">Per gli amministratori IT non sono attualmente disponibili opzioni per configurare le impostazioni di notifica sul lato client.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-220">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="d8fa2-221">Tutte le opzioni di notifica sono impostate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-221">All notification options are set by the user.</span></span> <span data-ttu-id="d8fa2-222">La figura seguente illustra le impostazioni predefinite del client.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-222">The figure below outlines the default client settings.</span></span>

![Screenshot delle impostazioni di notifica.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="d8fa2-224">Script di PowerShell di esempio</span><span class="sxs-lookup"><span data-stu-id="d8fa2-224">Sample PowerShell Script</span></span>

<span data-ttu-id="d8fa2-225">Questo script di esempio, che deve essere eseguito nei computer client nel contesto di un account amministratore con privilegi elevati, creerà una nuova regola del firewall in entrata per ogni cartella utente trovata in c:\Users.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-225">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="d8fa2-226">Questa regola impedisce all'applicazione di chiedere agli utenti di creare regole del firewall quando effettuano la loro prima chiamata da Teams.</span><span class="sxs-lookup"><span data-stu-id="d8fa2-226">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
