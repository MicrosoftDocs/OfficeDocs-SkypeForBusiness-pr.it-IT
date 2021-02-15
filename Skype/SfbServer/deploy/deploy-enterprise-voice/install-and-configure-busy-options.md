---
title: Installare e configurare le opzioni occupato per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Informazioni su come installare e configurare le opzioni occupato in Skype for Business Server.
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830806"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="c5d82-103">Installare e configurare le opzioni occupato per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c5d82-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="c5d82-104">Informazioni su come installare e configurare le opzioni occupato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c5d82-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="c5d82-105">Opzioni occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016 che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata messa in attesa.</span><span class="sxs-lookup"><span data-stu-id="c5d82-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="c5d82-106">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="c5d82-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="c5d82-107">Se l'opzione Opzioni occupato è abilitata per l'organizzazione, tutti gli utenti dell'organizzazione, sia VoIP aziendale che non VoIP aziendale, possono utilizzare le opzioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5d82-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="c5d82-108">Occupato: in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="c5d82-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="c5d82-109">Segreteria telefonica su occupato- In cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="c5d82-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="c5d82-110">Indipendentemente dalla configurazione delle opzioni di disponibilità, agli utenti di una chiamata o di una conferenza o agli utenti con una chiamata in attesa non viene impedito di avviare nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="c5d82-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="c5d82-111">Per ulteriori informazioni sulla funzionalità Opzioni occupato, vedere [Plan for Busy Options for Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="c5d82-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="c5d82-112">Installare</span><span class="sxs-lookup"><span data-stu-id="c5d82-112">Install</span></span>

<span data-ttu-id="c5d82-113">Assicurarsi di avere installato la versione più recente di Skype for Business Server e di aver installato la patch più recente.</span><span class="sxs-lookup"><span data-stu-id="c5d82-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="c5d82-114">A tale scopo, arrestare prima tutti i servizi e quindi eseguire il programma di installazione dell'aggiornamento di Skype for Business Server nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="c5d82-115">Eseguire il Stop-CsWindowsService comando.</span><span class="sxs-lookup"><span data-stu-id="c5d82-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="c5d82-116">Eseguire il SkypeServerUpdateInstaller.exe di installazione in ogni Front End Server di un pool.</span><span class="sxs-lookup"><span data-stu-id="c5d82-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="c5d82-117">Eseguire il SkypeServerUpdateInstaller.exe di installazione su ogni Survivable Branch Server (SBS), se si desidera garantire il supporto per il failover in SBS.</span><span class="sxs-lookup"><span data-stu-id="c5d82-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="c5d82-118">Il programma di installazione distribuirà la versione più recente dell'applicazione Opzioni occupato.</span><span class="sxs-lookup"><span data-stu-id="c5d82-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="c5d82-119">Tuttavia, l'applicazione non è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c5d82-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="c5d82-120">Per abilitare l'applicazione, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="c5d82-121">Eseguire il cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) per abilitare globalmente le opzioni occupato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="c5d82-122">Successivamente, se il sito dispone di un criterio vocale, è necessario abilitare le opzioni di disponibilità per il criterio vocale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="c5d82-123">Eseguire innanzitutto [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) per recuperare il nome del sito:</span><span class="sxs-lookup"><span data-stu-id="c5d82-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="c5d82-124">Utilizzare il valore Identity (ad esempio: Site:Redmond1) recuperato da Get-CsSite per recuperare i criteri vocali del sito nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="c5d82-125">Se per il sito esiste un criterio vocale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="c5d82-126">Eseguire quindi il cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) per aggiungere opzioni occupato all'elenco delle applicazioni server, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="c5d82-127">È necessario sostituire %FQDN% con il nome di dominio completo di un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="c5d82-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="c5d82-128">Successivamente, eseguire il cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) per aggiornare i ruoli RBAC (Controllo dell'accesso basato sui ruoli) per i cmdlet delle opzioni occupato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="c5d82-129">Infine, avviare i servizi di Windows di Skype for Business Server in tutti i Front End Server in tutti i pool in cui è stata installata e abilitata l'opzione Disponibilità eseguendo il [comando Start-CsWindowsService:](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c5d82-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="c5d82-130">Configurazione</span><span class="sxs-lookup"><span data-stu-id="c5d82-130">Configure</span></span>

<span data-ttu-id="c5d82-131">Per configurare le opzioni di disponibilità, utilizzare il cmdlet [Set-CsBusyOptions.](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5d82-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="c5d82-132">Ad esempio, il comando seguente configura le opzioni di occupato per l'utente "Ken Myer".</span><span class="sxs-lookup"><span data-stu-id="c5d82-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="c5d82-133">In questa configurazione, qualsiasi chiamata a "Ken Myer" restituirà un segnale di occupato quando è già in una chiamata:</span><span class="sxs-lookup"><span data-stu-id="c5d82-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="c5d82-134">Nell'esempio seguente, il comando configura le opzioni di occupato per l'utente "Ciccoli".</span><span class="sxs-lookup"><span data-stu-id="c5d82-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="c5d82-135">In questa configurazione, le nuove chiamate in arrivo a "Tutto il tempo" verranno inoltrate alla segreteria telefonica quando è già in una chiamata:</span><span class="sxs-lookup"><span data-stu-id="c5d82-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="c5d82-136">È possibile recuperare informazioni di configurazione sulle opzioni di disponibilità utilizzando il cmdlet [Get-CsBusyOptions.](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5d82-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="c5d82-137">Nell'esempio seguente viene restituita l'impostazione Opzioni occupato per "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="c5d82-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="c5d82-138">È possibile rimuovere le opzioni di disponibilità utilizzando il cmdlet [Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5d82-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="c5d82-139">Il comando seguente rimuove le opzioni di occupato per "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="c5d82-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="c5d82-140">Per informazioni dettagliate sui cmdlet utilizzati per configurare le opzioni occupato, vedere il contenuto di riferimento tecnico per [Set-CsBusyOptions,](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5d82-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="c5d82-141">Abilitare la registrazione</span><span class="sxs-lookup"><span data-stu-id="c5d82-141">Enable logging</span></span>

<span data-ttu-id="c5d82-142">Per abilitare la registrazione per le opzioni di occupato utilizzando il servizio di registrazione centralizzato, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c5d82-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="c5d82-143">Verificare e risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="c5d82-143">Verify and troubleshoot</span></span>

<span data-ttu-id="c5d82-144">Dopo aver installato Le opzioni occupato, è possibile verificare che l'installazione sia stata eseguita correttamente utilizzando il cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) per recuperare l'elenco delle applicazioni server.</span><span class="sxs-lookup"><span data-stu-id="c5d82-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="c5d82-145">Se le opzioni di occupato sono installate correttamente, l'output del cmdlet dovrebbe mostrare la configurazione delle opzioni occupato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c5d82-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="c5d82-146">È inoltre possibile utilizzare il Visualizzatore eventi di Windows per verificare che l'installazione delle opzioni di occupato sia stata eseguita correttamente e che Skype for Business Server sia stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c5d82-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="c5d82-147">Per verificare le opzioni di occupato, aprire Visualizzatore eventi - Registri applicazioni e servizi **\> - Skype \> (o Lync) Server** e cercare ID evento = 30253.</span><span class="sxs-lookup"><span data-stu-id="c5d82-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
