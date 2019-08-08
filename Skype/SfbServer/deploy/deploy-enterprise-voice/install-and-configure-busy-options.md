---
title: Installare e configurare le opzioni di occupato per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Leggere informazioni su come installare e configurare le opzioni di occupato in Skype for Business Server.
ms.openlocfilehash: a0fd235d5db645035ac9a6344c233dfe12a78b7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240555"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="b4c64-103">Installare e configurare le opzioni di occupato per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b4c64-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="b4c64-104">Leggere informazioni su come installare e configurare le opzioni di occupato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b4c64-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="b4c64-105">Opzioni di occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di 2016 di luglio che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o se è stata inserita una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="b4c64-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="b4c64-106">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="b4c64-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="b4c64-107">Se le opzioni di occupato sono abilitate per l'organizzazione, tutti gli utenti dell'azienda, sia VoIP aziendale che utenti non aziendali, possono usare le opzioni di configurazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4c64-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="b4c64-108">Occupato in busy-in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="b4c64-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="b4c64-109">Segreteria telefonica in occupato, in cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="b4c64-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="b4c64-110">Indipendentemente dal modo in cui sono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o quelli con una chiamata in attesa non vengono impediti di avviare nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="b4c64-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="b4c64-111">Per altre informazioni sulla funzionalità opzioni occupato, vedere [pianificare le opzioni di occupato per Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="b4c64-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="b4c64-112">Installare</span><span class="sxs-lookup"><span data-stu-id="b4c64-112">Install</span></span>

<span data-ttu-id="b4c64-113">Verificare di avere installato l'ultima versione di Skype for Business Server e di avere installato la patch più recente.</span><span class="sxs-lookup"><span data-stu-id="b4c64-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="b4c64-114">A tale scopo, prima di tutto arrestare tutti i servizi e quindi eseguire il programma di installazione di aggiornamento di Skype for Business Server come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b4c64-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="b4c64-115">Eseguire il comando Stop-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="b4c64-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="b4c64-116">Eseguire il programma di installazione SkypeServerUpdateInstaller. exe su ogni server front-end in un pool.</span><span class="sxs-lookup"><span data-stu-id="b4c64-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="b4c64-117">Eseguire il programma di installazione SkypeServerUpdateInstaller. exe in ogni Survivable Branch Server (SBS), se si vuole garantire il supporto per il failover su SBS.</span><span class="sxs-lookup"><span data-stu-id="b4c64-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="b4c64-118">Il programma di installazione distribuirà la versione più recente dell'applicazione Opzioni occupato.</span><span class="sxs-lookup"><span data-stu-id="b4c64-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="b4c64-119">Tuttavia, l'applicazione non è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b4c64-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="b4c64-120">Per abilitare l'applicazione, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c64-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="b4c64-121">Eseguire il cmdlet [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) per abilitare globalmente le opzioni di occupato, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c64-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="b4c64-122">Se quindi il sito ha un criterio vocale, è necessario abilitare le opzioni di occupato per il criterio vocale, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b4c64-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="b4c64-123">Eseguire prima di tutto [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) per recuperare il nome del sito:</span><span class="sxs-lookup"><span data-stu-id="b4c64-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```
   Get-CsSite
   ```

    <span data-ttu-id="b4c64-124">Usa il valore Identity (ad esempio: site: Redmond1) recuperato da Get-CsSite per recuperare i criteri vocali del sito nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c64-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="b4c64-125">Se per il sito esiste un criterio vocale, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c64-125">If a voice policy exists for the site, run the following command:</span></span>

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="b4c64-126">Eseguire quindi il cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) per aggiungere le opzioni di occupato all'elenco delle applicazioni server, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c64-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="b4c64-127">È necessario sostituire% FQDN% con il nome di dominio completo di un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="b4c64-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="b4c64-128">Eseguire quindi il cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) per aggiornare i ruoli di controllo di accesso basati sui ruoli per i cmdlet delle opzioni occupati, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c64-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="b4c64-129">Infine, avviare i servizi Windows di Skype for Business Server in tutti i server front-end in tutti i pool in cui sono state installate e abilitate le opzioni di occupato eseguendo il comando [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="b4c64-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="b4c64-130">Configurare</span><span class="sxs-lookup"><span data-stu-id="b4c64-130">Configure</span></span>

<span data-ttu-id="b4c64-131">Per configurare le opzioni di occupato, usare il cmdlet [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b4c64-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="b4c64-132">Ad esempio, il comando seguente configura le opzioni di occupato per l'utente "Ken".</span><span class="sxs-lookup"><span data-stu-id="b4c64-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="b4c64-133">In questa configurazione qualsiasi chiamata a "Ken" restituirà un segnale di occupato quando è già in corso una chiamata:</span><span class="sxs-lookup"><span data-stu-id="b4c64-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="b4c64-134">Nell'esempio seguente il comando Configura le opzioni di occupato per l'utente "Chrystal Velasquez".</span><span class="sxs-lookup"><span data-stu-id="b4c64-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="b4c64-135">In questa configurazione le nuove chiamate in arrivo a "Chrystal Velasquez" verranno inoltrate alla segreteria telefonica quando è già in corso una chiamata:</span><span class="sxs-lookup"><span data-stu-id="b4c64-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="b4c64-136">Puoi recuperare le informazioni di configurazione sulle opzioni di occupato usando il cmdlet [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b4c64-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="b4c64-137">L'esempio seguente restituisce l'impostazione delle opzioni di occupato per "KenMyer@Contoso.com":</span><span class="sxs-lookup"><span data-stu-id="b4c64-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="b4c64-138">È possibile rimuovere le opzioni di occupato usando il cmdlet [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b4c64-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="b4c64-139">Il comando seguente rimuove le opzioni di occupato per "Ken":</span><span class="sxs-lookup"><span data-stu-id="b4c64-139">The following command removes Busy Options for "Ken Myer":</span></span>

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="b4c64-140">Per informazioni dettagliate sui cmdlet usati per configurare le opzioni di occupato, vedere il contenuto di riferimento tecnico per [set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)e [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4c64-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="b4c64-141">Abilitare la registrazione</span><span class="sxs-lookup"><span data-stu-id="b4c64-141">Enable logging</span></span>

<span data-ttu-id="b4c64-142">Per abilitare la registrazione per le opzioni di occupato tramite il servizio di registrazione centralizzato, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b4c64-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="b4c64-143">Verificare e risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="b4c64-143">Verify and troubleshoot</span></span>

<span data-ttu-id="b4c64-144">Dopo aver installato le opzioni di occupato, è possibile verificare che l'installazione abbia avuto successo usando il cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) per recuperare l'elenco delle applicazioni server.</span><span class="sxs-lookup"><span data-stu-id="b4c64-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="b4c64-145">Se le opzioni di occupato sono installate correttamente, l'output del cmdlet dovrebbe mostrare la configurazione delle opzioni occupate nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b4c64-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="b4c64-146">Puoi anche usare il Visualizzatore eventi di Windows per verificare che l'installazione delle opzioni occupato abbia avuto successo e che Skype for Business Server abbia caricato correttamente le opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="b4c64-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="b4c64-147">Per verificare le opzioni di occupato, aprire il **Visualizzatore eventi-\> registri applicazioni\> e servizi-server Skype (o Lync)** e cercare ID evento = 30253.</span><span class="sxs-lookup"><span data-stu-id="b4c64-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
