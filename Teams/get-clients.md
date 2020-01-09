---
title: Ottenere client per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i vari client disponibili per Microsoft teams, che includono Web, desktop (Windows e Mac) e dispositivi mobili (Android e iOS).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e47e8e4765bc93c2281efc07766f77f173b0fad
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990851"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="ab133-103">Ottenere client per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab133-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="ab133-104">Microsoft teams include client disponibili per il desktop (Windows, Mac e Linux), Web e dispositivi mobili (Android e iOS).</span><span class="sxs-lookup"><span data-stu-id="ab133-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="ab133-105">Questi client richiedono tutti una connessione Internet attiva e non supportano una modalità offline.</span><span class="sxs-lookup"><span data-stu-id="ab133-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="ab133-106">Efficace il 29 novembre 2018 non sarà più possibile usare l'app Microsoft teams per Windows 10 S (Preview), disponibile presso Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ab133-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="ab133-107">È ora possibile scaricare e installare il client desktop di Teams nei dispositivi in cui è in uso la modalità Windows 10 S.</span><span class="sxs-lookup"><span data-stu-id="ab133-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="ab133-108">Per scaricare il client desktop, vai a [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span><span class="sxs-lookup"><span data-stu-id="ab133-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="ab133-109">Le build MSI del client desktop teams non sono ancora disponibili per i dispositivi che usano la modalità Windows 10 S.</span><span class="sxs-lookup"><span data-stu-id="ab133-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="ab133-110">Per altre informazioni sulla modalità Windows 10 S, vedere [Introduzione a Windows 10 in modalità s](https://www.microsoft.com/windows/s-mode).</span><span class="sxs-lookup"><span data-stu-id="ab133-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="ab133-111">Client desktop</span><span class="sxs-lookup"><span data-stu-id="ab133-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="ab133-112">Vedere la sessione seguente per informazioni sui vantaggi del client desktop di Windows, su come pianificare la procedura e su come distribuirla: [Team client desktop di Windows](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="ab133-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="ab133-113">Il client desktop Microsoft teams è un'applicazione autonoma ed è [disponibile anche in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="ab133-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="ab133-114">Teams è disponibile per Windows (7 +), entrambe le versioni a 32 bit e 64 bit, macOS (10.10 +) e Linux (in `.deb` e `.rpm` formati).</span><span class="sxs-lookup"><span data-stu-id="ab133-114">Teams is available for Windows (7+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (in `.deb` and `.rpm` formats.).</span></span> <span data-ttu-id="ab133-115">In Windows i team richiedono .NET Framework 4,5 o versioni successive; il programma di installazione di teams offrirà l'installazione per se non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="ab133-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="ab133-116">Su Linux, i gestori di pacchetti come apt e yum cercheranno di installare qualsiasi requisito.</span><span class="sxs-lookup"><span data-stu-id="ab133-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="ab133-117">Tuttavia, se non è così, dovrai installare i requisiti segnalati prima di installare teams su Linux.</span><span class="sxs-lookup"><span data-stu-id="ab133-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="ab133-118">I client desktop supportano il supporto delle comunicazioni in tempo reale (audio, video e condivisione di contenuti) per le riunioni del team, le chiamate di gruppo e quelle private uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="ab133-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="ab133-119">I client desktop possono essere scaricati e installati dagli utenti finali direttamente [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) da se hanno le autorizzazioni locali appropriate (i diritti di amministratore non sono necessari per installare il client teams su un PC, ma sono necessari in un Mac).</span><span class="sxs-lookup"><span data-stu-id="ab133-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="ab133-120">Gli amministratori IT possono scegliere il metodo preferito per distribuire i file di installazione nei computer dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab133-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="ab133-121">Alcuni esempi includono System Center Configuration Manager (Windows) o grafp Pro (macOS).</span><span class="sxs-lookup"><span data-stu-id="ab133-121">Some examples include System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="ab133-122">Per ottenere il pacchetto MSI per la distribuzione di Windows, vedere [installare Microsoft teams con MSI](msi-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="ab133-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="ab133-123">La distribuzione del client tramite questi meccanismi è solo per l'installazione iniziale dei client di Microsoft Team e non per gli aggiornamenti futuri.</span><span class="sxs-lookup"><span data-stu-id="ab133-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="ab133-124">Windows</span><span class="sxs-lookup"><span data-stu-id="ab133-124">Windows</span></span>

<span data-ttu-id="ab133-125">L'installazione di Microsoft teams per Windows offre programmi di installazione scaricabili in architettura a 32 bit e a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ab133-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="ab133-126">L'architettura (32 bit e 64 bit) di Microsoft teams è agnostica rispetto all'architettura di Windows e Office installata.</span><span class="sxs-lookup"><span data-stu-id="ab133-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="ab133-127">Il client Windows viene distribuito nella cartella AppData che si trova nel profilo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ab133-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="ab133-128">La distribuzione nel profilo locale dell'utente consente di installare il client senza richiedere diritti elevati.</span><span class="sxs-lookup"><span data-stu-id="ab133-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="ab133-129">Il client Windows sfrutta le posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab133-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="ab133-130">% LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="ab133-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="ab133-131">% LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="ab133-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="ab133-132">% AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="ab133-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="ab133-133">% LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="ab133-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="ab133-134">Quando gli utenti avviano una chiamata con il client Microsoft teams per la prima volta, potrebbero notare un avviso con le impostazioni di Windows Firewall che chiedono agli utenti di consentire la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="ab133-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="ab133-135">Agli utenti potrebbe essere richiesto di ignorare questo messaggio perché la chiamata funzionerà anche quando l'avviso viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="ab133-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Screenshot della finestra di dialogo avviso di sicurezza di Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="ab133-137">La configurazione di Windows Firewall verrà modificata anche quando il messaggio viene chiuso selezionando "Annulla".</span><span class="sxs-lookup"><span data-stu-id="ab133-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="ab133-138">Verranno create due regole in ingresso per Teams. exe con l'azione blocca per i protocolli TCP e UDP.</span><span class="sxs-lookup"><span data-stu-id="ab133-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="ab133-139">Mac</span><span class="sxs-lookup"><span data-stu-id="ab133-139">Mac</span></span>

<span data-ttu-id="ab133-140">Gli utenti di Mac possono installare teams usando un file di installazione di PKG per i computer macOS.</span><span class="sxs-lookup"><span data-stu-id="ab133-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="ab133-141">Per installare il client Mac è necessario l'accesso amministrativo.</span><span class="sxs-lookup"><span data-stu-id="ab133-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="ab133-142">Il client macOS viene installato nella cartella/Applications.</span><span class="sxs-lookup"><span data-stu-id="ab133-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="ab133-143">Installare teams usando il file PKG</span><span class="sxs-lookup"><span data-stu-id="ab133-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="ab133-144">Nella [pagina Download teams](https://teams.microsoft.com/downloads), in **Mac**, fare clic su **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="ab133-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="ab133-145">Fare doppio clic sul file PKG.</span><span class="sxs-lookup"><span data-stu-id="ab133-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="ab133-146">Seguire l'installazione guidata per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="ab133-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="ab133-147">I team verranno installati nella cartella/Applications.</span><span class="sxs-lookup"><span data-stu-id="ab133-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="ab133-148">Si tratta di un'installazione a livello di computer.</span><span class="sxs-lookup"><span data-stu-id="ab133-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="ab133-149">Durante l'installazione, il PKG richiederà le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="ab133-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="ab133-150">L'utente deve immettere le credenziali di amministratore, indipendentemente dal fatto che l'utente sia o meno un amministratore.</span><span class="sxs-lookup"><span data-stu-id="ab133-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="ab133-151">Se un utente ha attualmente un'installazione DMG di teams e vuole sostituirla con l'installazione di PKG, l'utente deve:</span><span class="sxs-lookup"><span data-stu-id="ab133-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="ab133-152">Uscire dall'app teams.</span><span class="sxs-lookup"><span data-stu-id="ab133-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="ab133-153">Disinstallare l'app teams.</span><span class="sxs-lookup"><span data-stu-id="ab133-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="ab133-154">Installare il file PKG.</span><span class="sxs-lookup"><span data-stu-id="ab133-154">Install the PKG file.</span></span>

<span data-ttu-id="ab133-155">Gli amministratori IT possono usare la distribuzione gestita di teams per distribuire i file di installazione in tutti i Mac dell'organizzazione, ad esempio grafp Pro.</span><span class="sxs-lookup"><span data-stu-id="ab133-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="ab133-156">Se si verificano problemi durante l'installazione del PKG, avvisaci.</span><span class="sxs-lookup"><span data-stu-id="ab133-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="ab133-157">Nella sezione **feedback** alla fine di questo articolo fare clic su **feedback prodotto**.</span><span class="sxs-lookup"><span data-stu-id="ab133-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="ab133-158">Linux</span><span class="sxs-lookup"><span data-stu-id="ab133-158">Linux</span></span>

<span data-ttu-id="ab133-159">Gli utenti saranno in grado di installare pacchetti Linux nativi `.deb` e `.rpm` formati.</span><span class="sxs-lookup"><span data-stu-id="ab133-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="ab133-160">L'installazione del pacchetto DEB o RPM installerà automaticamente il repository del pacchetto</span><span class="sxs-lookup"><span data-stu-id="ab133-160">Installing the DEB or RPM package will automatically install the package repository</span></span>
- <span data-ttu-id="ab133-161">DEB`https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="ab133-161">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="ab133-162">RPM`https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="ab133-162">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="ab133-163">La chiave di firma per abilitare l'aggiornamento automatico con gestione pacchetti del sistema viene installata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ab133-163">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="ab133-164">Tuttavia, può essere trovato anche in: (https://packages.microsoft.com/keys/microsoft.asc).</span><span class="sxs-lookup"><span data-stu-id="ab133-164">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="ab133-165">Microsoft teams viene distribuito mensilmente e, se il repository è stato installato correttamente, il gestore di pacchetti di sistema deve gestire l'aggiornamento automatico nello stesso modo degli altri pacchetti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ab133-165">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="ab133-166">Se si trova un bug, inviarlo tramite `Report a Problem` dall'interno del client.</span><span class="sxs-lookup"><span data-stu-id="ab133-166">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="ab133-167">Per i problemi noti, vedere [problemi noti](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ab133-167">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="ab133-168">Per il supporto di teams for Linux puoi usare il [canale di supporto di Linux Forum su Microsoft Q&a](https://docs.microsoft.com/answers/topics/teams.html).</span><span class="sxs-lookup"><span data-stu-id="ab133-168">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="ab133-169">Assicurati di usare il `teams-linux` tag per pubblicare domande.</span><span class="sxs-lookup"><span data-stu-id="ab133-169">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="ab133-170">Installare teams usando il pacchetto DEB</span><span class="sxs-lookup"><span data-stu-id="ab133-170">Install Teams using DEB package</span></span>

1. <span data-ttu-id="ab133-171">Scaricare il pacchetto da https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="ab133-171">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="ab133-172">Installare utilizzando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab133-172">Install using one of the following:</span></span>  
    - <span data-ttu-id="ab133-173">Aprire lo strumento di gestione dei pacchetti pertinente e passare al processo di installazione dell'app Linux auto-guidata.</span><span class="sxs-lookup"><span data-stu-id="ab133-173">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="ab133-174">Oppure, se si ama il terminale, digitare:`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="ab133-174">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="ab133-175">È possibile avviare teams tramite le attività o tramite terminale `Teams`digitando.</span><span class="sxs-lookup"><span data-stu-id="ab133-175">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="ab133-176">Installare teams usando il pacchetto RPM</span><span class="sxs-lookup"><span data-stu-id="ab133-176">Install Teams using RPM package</span></span>

1. <span data-ttu-id="ab133-177">Scaricare il pacchetto da https://aka.ms/getteams.</span><span class="sxs-lookup"><span data-stu-id="ab133-177">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="ab133-178">Installare utilizzando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab133-178">Install using one of the following:</span></span>
    - <span data-ttu-id="ab133-179">Aprire lo strumento di gestione dei pacchetti pertinente e passare al processo di installazione dell'app Linux auto-guidata.</span><span class="sxs-lookup"><span data-stu-id="ab133-179">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="ab133-180">Oppure, se si ama il terminale, digitare:`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="ab133-180">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="ab133-181">È possibile avviare teams tramite le attività o tramite terminale `Teams`digitando.</span><span class="sxs-lookup"><span data-stu-id="ab133-181">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="ab133-182">Installare manualmente dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="ab133-182">Install manually from the command line</span></span>

<span data-ttu-id="ab133-183">Installare manualmente sulle distribuzioni Debian e Ubuntu:</span><span class="sxs-lookup"><span data-stu-id="ab133-183">Install manually on Debian and Ubuntu distributions:</span></span>
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="ab133-184">Installare manualmente nelle distribuzioni basate su RHEL, Fedora e CentOS:</span><span class="sxs-lookup"><span data-stu-id="ab133-184">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="ab133-185">Aternatively, per usare yum al posto di DNF:</span><span class="sxs-lookup"><span data-stu-id="ab133-185">Aternatively, to use yum instead of dnf:</span></span>
```
yum check-update
sudo yum install teams
```

<span data-ttu-id="ab133-186">Installare manualmente nelle distribuzioni basate su openSUSE:</span><span class="sxs-lookup"><span data-stu-id="ab133-186">Install manually on openSUSE based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="ab133-187">Client Web</span><span class="sxs-lookup"><span data-stu-id="ab133-187">Web client</span></span> 

<span data-ttu-id="ab133-188">Il client Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) è un client completo e funzionale che può essere usato da un'ampia varietà di browser.</span><span class="sxs-lookup"><span data-stu-id="ab133-188">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="ab133-189">Il client Web supporta le chiamate e le riunioni tramite webRTC, quindi non è necessario alcun plug-in o download per l'esecuzione di team in un Web browser.</span><span class="sxs-lookup"><span data-stu-id="ab133-189">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="ab133-190">Il browser deve essere configurato per consentire i cookie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ab133-190">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="ab133-191">Il client Web esegue il rilevamento della versione del browser [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)al momento della connessione.</span><span class="sxs-lookup"><span data-stu-id="ab133-191">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="ab133-192">Se viene rilevata una versione del browser non supportata, si bloccherà l'accesso all'interfaccia Web e si consiglia che l'utente scarichi il client desktop o l'app per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="ab133-192">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="ab133-193">Client per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ab133-193">Mobile clients</span></span>

<span data-ttu-id="ab133-194">Le app Microsoft teams per dispositivi mobili sono disponibili per Android e iOS e sono orientate per gli utenti che partecipano a conversazioni basate su chat e consentono chiamate audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="ab133-194">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="ab133-195">Per le app per dispositivi mobili, accedi ai negozi di dispositivi mobili di Google Play e all'App Store Apple.</span><span class="sxs-lookup"><span data-stu-id="ab133-195">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="ab133-196">L'app Windows Phone è stata ritirata il 20 luglio 2018 e potrebbe non funzionare più.</span><span class="sxs-lookup"><span data-stu-id="ab133-196">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="ab133-197">Le piattaforme mobili supportate per le app per dispositivi mobili Microsoft teams sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab133-197">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="ab133-198">**Android**: il supporto è limitato alle ultime quattro versioni principali di Android.</span><span class="sxs-lookup"><span data-stu-id="ab133-198">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="ab133-199">Quando viene rilasciata una nuova versione principale di Android, la nuova versione e le tre versioni precedenti sono supportate ufficialmente.</span><span class="sxs-lookup"><span data-stu-id="ab133-199">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="ab133-200">**iOS**: il supporto è limitato alle due versioni principali più recenti di iOS.</span><span class="sxs-lookup"><span data-stu-id="ab133-200">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="ab133-201">Quando viene rilasciata una nuova versione principale di iOS, la nuova versione di iOS e la versione precedente sono supportate ufficialmente.</span><span class="sxs-lookup"><span data-stu-id="ab133-201">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="ab133-202">La versione per dispositivi mobili deve essere disponibile al pubblico in modo che i team funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="ab133-202">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="ab133-203">Le app per dispositivi mobili vengono distribuite e aggiornate solo nell'App Store della piattaforma mobile corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ab133-203">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="ab133-204">La distribuzione delle app per dispositivi mobili tramite MDM o il caricamento laterale non è supportata da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab133-204">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="ab133-205">Quando l'app per dispositivi mobili è stata installata in una piattaforma mobile supportata, l'app teams per dispositivi mobili verrà supportata purché la versione sia entro tre mesi dalla data di rilascio corrente.</span><span class="sxs-lookup"><span data-stu-id="ab133-205">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![Icona che descrive un punto decisionale](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="ab133-207">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="ab133-207">Decision Point</span></span>         |<span data-ttu-id="ab133-208">Esistono restrizioni per impedire agli utenti di installare il client Microsoft teams appropriato nei propri dispositivi?</span><span class="sxs-lookup"><span data-stu-id="ab133-208">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![Icona che descrive i passaggi successivi](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="ab133-210">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="ab133-210">Next Steps</span></span>         |<span data-ttu-id="ab133-211">Se l'organizzazione limita l'installazione del software, verificare che il processo sia compatibile con Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ab133-211">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="ab133-212">Nota: i diritti di amministratore non sono necessari per l'installazione del client PC, ma sono necessari per l'installazione in un Mac.</span><span class="sxs-lookup"><span data-stu-id="ab133-212">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="ab133-213">Gestione degli aggiornamenti client</span><span class="sxs-lookup"><span data-stu-id="ab133-213">Client update management</span></span>

<span data-ttu-id="ab133-214">I client sono attualmente aggiornati automaticamente dal servizio Microsoft teams senza l'intervento dell'amministratore IT richiesto.</span><span class="sxs-lookup"><span data-stu-id="ab133-214">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="ab133-215">Se è disponibile un aggiornamento, il client scaricherà automaticamente l'aggiornamento e quando l'app verrà inattiva per un periodo di tempo, il processo di aggiornamento inizierà.</span><span class="sxs-lookup"><span data-stu-id="ab133-215">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="ab133-216">Configurazioni lato client</span><span class="sxs-lookup"><span data-stu-id="ab133-216">Client-side configurations</span></span>

<span data-ttu-id="ab133-217">Attualmente non sono disponibili opzioni supportate per configurare il client tramite l'amministratore del tenant, PowerShell, gli oggetti Criteri di gruppo o il registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="ab133-217">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="ab133-218">Impostazioni di notifica</span><span class="sxs-lookup"><span data-stu-id="ab133-218">Notification settings</span></span>

<span data-ttu-id="ab133-219">Al momento non sono disponibili opzioni per gli amministratori IT per configurare le impostazioni di notifica sul lato client.</span><span class="sxs-lookup"><span data-stu-id="ab133-219">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="ab133-220">Tutte le opzioni di notifica vengono impostate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ab133-220">All notification options are set by the user.</span></span> <span data-ttu-id="ab133-221">La figura seguente illustra le impostazioni predefinite del client.</span><span class="sxs-lookup"><span data-stu-id="ab133-221">The figure below outlines the default client settings.</span></span>

![Screenshot delle impostazioni delle notifiche.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="ab133-223">Esempio di script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab133-223">Sample PowerShell Script</span></span>

<span data-ttu-id="ab133-224">Questo script di esempio, che deve essere eseguito nei computer client nel contesto di un account di amministratore con privilegi elevati, creerà una nuova regola del firewall in ingresso per ogni cartella utente trovata in c:\Users.</span><span class="sxs-lookup"><span data-stu-id="ab133-224">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="ab133-225">Quando teams trova questa regola, impedirà all'applicazione teams di richiedere agli utenti di creare regole del firewall quando gli utenti effettuano la prima chiamata da teams.</span><span class="sxs-lookup"><span data-stu-id="ab133-225">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

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
