---
title: Modificare la configurazione di una distribuzione di Cloud Connector esistente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Seguire la procedura descritta in questo argomento per modificare la configurazione di una distribuzione di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva esistente.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359112"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="7dfbc-103">Modificare la configurazione di una distribuzione di Cloud Connector esistente</span><span class="sxs-lookup"><span data-stu-id="7dfbc-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="7dfbc-104">Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="7dfbc-105">Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="7dfbc-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="7dfbc-106">Seguire la procedura descritta in questo argomento per modificare la configurazione di una distribuzione di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva esistente.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="7dfbc-107">Modificare la configurazione di un singolo sito</span><span class="sxs-lookup"><span data-stu-id="7dfbc-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="7dfbc-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="7dfbc-109">Se nel sito è presente un solo dispositivo, quando si desidera modificare le impostazioni di configurazione dopo la distribuzione dell'accessorio, è possibile modificare il file CloudConnector.ini e riavviare di nuovo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="7dfbc-110">Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nel server host:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="7dfbc-111">Eseguire il seguente cmdlet per annullare la registrazione dell'accessorio:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="7dfbc-112">Aggiornare il file CloudConnector.ini nella directory appliance.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="7dfbc-113">Eseguire il cmdlet seguente per aggiornare la configurazione: (questo passaggio è applicabile solo per la versione 2, per le versioni precedenti, passare al passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="7dfbc-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="7dfbc-114">Eseguire il cmdlet seguente per registrare nuovamente l'accessorio:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="7dfbc-115">Eseguire il seguente cmdlet per installare Skype for Business Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="7dfbc-116">Se nel sito sono presenti più dispositivi, è necessario attenersi alla seguente procedura, modificare il file CloudConnector.ini e ridistribuire gli elettrodomestici uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="7dfbc-117">Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nell'accessorio corrente:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="7dfbc-118">Eseguire il seguente cmdlet per annullare la registrazione dell'accessorio:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="7dfbc-119">Aggiornare il file CloudConnector.ini nella directory appliance.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="7dfbc-120">Eseguire il cmdlet seguente per aggiornare la configurazione: (questo passaggio è applicabile solo per la versione 2, per le versioni precedenti, passare al passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="7dfbc-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="7dfbc-121">Eseguire il cmdlet seguente per registrare nuovamente l'accessorio:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="7dfbc-122">Eseguire il cmdlet seguente in tutti gli altri dispositivi del sito per raccogliere la configurazione più recente:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="7dfbc-123">Eseguire il cmdlet seguente per ridistribuire il connettore Cloud nell'accessorio corrente:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="7dfbc-124">Modificare la configurazione di più siti</span><span class="sxs-lookup"><span data-stu-id="7dfbc-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="7dfbc-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="7dfbc-126">Per modificare la configurazione di più siti in una distribuzione, seguire la procedura per un singolo sito, aggiornando un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="7dfbc-127">Modificare la configurazione dell'organizzazione Microsoft 365 o Office 365 per abilitare gli aggiornamenti automatici</span><span class="sxs-lookup"><span data-stu-id="7dfbc-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="7dfbc-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="7dfbc-129">Per abilitare gli aggiornamenti automatici del sistema operativo e gli aggiornamenti automatici dei bit, è necessario utilizzare l'account di amministratore del tenant di Skype for business per la gestione online e utilizzare Remote PowerShell tenant come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="7dfbc-130">Se sono stati disabilitati gli aggiornamenti automatici dei bit o degli aggiornamenti automatici del sistema operativo, l'host e la macchina virtuale potrebbero non essere più importanti per gli aggiornamenti di Windows e Cloud Connector non verrà aggiornato automaticamente alla nuova versione.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="7dfbc-131">È consigliabile abilitare gli aggiornamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="7dfbc-132">È necessario che la proprietà EnableAutoUpdate del sito sia impostata su true (il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="7dfbc-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="7dfbc-133">Eseguire il cmdlet seguente per assicurarsi che EnableAutoUpdate sia impostato su true:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="7dfbc-134">Creare la finestra di tempo di aggiornamento automatico per il tenant.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="7dfbc-135">La finestra temporale può essere giornaliera, settimanale e mensile.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="7dfbc-136">Tutte le finestre temporali necessitano di un'ora di inizio e una durata.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="7dfbc-137">Per una finestra di tempo giornaliero, sono necessari solo l'ora di inizio e la durata.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="7dfbc-138">Per una finestra di tempo settimanale, sono necessari giorni della settimana, che possono essere un solo giorno o più giorni.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="7dfbc-139">Per una finestra di tempo mensile, possono essere presenti due tipi.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="7dfbc-140">Il primo tipo è quello di specificare il giorno del mese, che può essere un solo giorno.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="7dfbc-141">Il secondo tipo è quello di specificare le settimane del mese, insieme ai giorni della settimana, che possono essere entrambi un singolo elemento o più elementi.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="7dfbc-142">Ogni tenant può disporre di 20 finestre temporali definite.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="7dfbc-143">La finestra di tempo predefinita verrà creata per un nuovo tenant come finestra temporale predefinita per l'aggiornamento dei sistemi operativi e l'aggiornamento dei bit.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="7dfbc-144">Eseguire i seguenti cmdlet per impostare la finestra di tempo giornaliero, settimanale o mensile:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="7dfbc-145">Assegnare le finestre di tempo di aggiornamento al sito.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="7dfbc-146">Le finestre dell'ora di aggiornamento dei bit e del sistema operativo sono configurate separatamente.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="7dfbc-147">Entrambe possono essere assegnate a una o più finestre temporali.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="7dfbc-148">Ogni finestra di tempo può essere assegnata a siti diversi e a un altro scopo (aggiornamento dei bit e aggiornamento del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="7dfbc-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="7dfbc-149">Eseguire il cmdlet seguente per impostare la finestra temporale per il sito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="7dfbc-150">Aggiornare le credenziali di amministratore tenant dedicate</span><span class="sxs-lookup"><span data-stu-id="7dfbc-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="7dfbc-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="7dfbc-152">Le modifiche amministrative nell'organizzazione di Microsoft 365 o Office 365 per il connettore Cloud sono eseguite da un account con le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="7dfbc-153">Nelle versioni di connettori cloud precedenti all'2,0, quell'account è un account amministratore globale dedicato del tenant.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="7dfbc-154">In Cloud Connector Versions 2,0 e versioni successive, quell'account può essere un account Microsoft 365 o Office 365 con i diritti di amministratore di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="7dfbc-155">Se le credenziali dell'account di amministratore cambiano in Microsoft 365 o Office 365, è inoltre necessario aggiornare le credenziali memorizzate nella cache locale in Cloud Connector eseguendo il comando di PowerShell di amministratore seguente su ogni accessorio Cloud Connector distribuito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="7dfbc-156">Aggiornare la password per il server host</span><span class="sxs-lookup"><span data-stu-id="7dfbc-156">Update the password for the host server</span></span>
<span data-ttu-id="7dfbc-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="7dfbc-158">Questa sezione è applicabile al connettore Cloud versione 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="7dfbc-159">Tutte le credenziali del connettore Cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="7dfbc-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="7dfbc-160">Quando la password sul server host cambia, sarà necessario aggiornare le credenziali memorizzate localmente.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="7dfbc-161">Per aggiornare le credenziali memorizzate localmente nell'accessorio Cloud Connector, utilizzare i cmdlet [Get-CcCredential](get-cccredential.md) e [set-CcCredential](set-cccredential.md) e attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="7dfbc-162">Eseguire i seguenti comandi per recuperare le password necessarie in un secondo momento:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="7dfbc-163">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="7dfbc-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="7dfbc-164">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="7dfbc-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="7dfbc-165">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="7dfbc-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="7dfbc-166">Modificare la password dell'account sul server host.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="7dfbc-167">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="7dfbc-168">Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML ".</span><span class="sxs-lookup"><span data-stu-id="7dfbc-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="7dfbc-169">Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="7dfbc-170">Assicurarsi di immettere la stessa password immessa prima per la distribuzione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="7dfbc-171">Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="7dfbc-172">Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="7dfbc-173">Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="7dfbc-174">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="7dfbc-175">Quando viene richiesto per la nuova credenziale account, immettere la password per la password di DomainAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="7dfbc-176">Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="7dfbc-177">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="7dfbc-178">Quando viene richiesto per la nuova credenziale account, immettere la password per la password di VmAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="7dfbc-179">Aggiornare la password per l'account CceService</span><span class="sxs-lookup"><span data-stu-id="7dfbc-179">Update the password for the CceService account</span></span>
<span data-ttu-id="7dfbc-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="7dfbc-181">Questa sezione è applicabile a Cloud Connector versione 2.0.1 e successive.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="7dfbc-182">Il servizio Cloud Connector esegue il servizio di gestione Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="7dfbc-183">L'account CceService viene creato durante la distribuzione di Cloud Connector Edition e archiviato nei seguenti file: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML "e"% SystemDrive% \Programdata\Cloudconnector\credentials..CceService.xml ".</span><span class="sxs-lookup"><span data-stu-id="7dfbc-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="7dfbc-184">Per assicurarsi che tutti gli apparecchi possano accedere alla condivisione directory del sito, la password per l'account CceService deve essere identica su tutti gli elettrodomestici distribuiti all'interno del sito.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="7dfbc-185">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="7dfbc-186">Per impostazione predefinita, l'account CceService è configurato come "password non scade mai".</span><span class="sxs-lookup"><span data-stu-id="7dfbc-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="7dfbc-187">Quando si aggiorna la password, Microsoft consiglia di mantenere la configurazione.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="7dfbc-188">È necessario aggiornare la password durante periodi di utilizzo non di picco e al di fuori delle finestre di tempo di aggiornamento automatico per i bit o gli aggiornamenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="7dfbc-189">Quando si aggiorna la password, l'accessorio deve essere svuotato e riavviato, che richiede un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="7dfbc-190">Il riavvio dell'accessorio interromperà le operazioni di aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="7dfbc-191">Quando si modifica la password dell'account CceService, sarà necessario specificare tutte le credenziali e aggiornarle nel file archiviato localmente.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="7dfbc-192">Per ogni accessorio che appartiene allo stesso sito PSTN, è necessario specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="7dfbc-193">Eseguire i seguenti comandi per recuperare i nomi account e le password che verranno utilizzate in un secondo momento:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="7dfbc-194">Eseguire il cmdlet Enter-CcUpdate per svuotare l'accessorio e spostarlo in modalità di manutenzione manuale.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="7dfbc-195">Aggiornare la password dell'account CceService sul server host.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="7dfbc-196">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="7dfbc-197">Eseguire il cmdlet Restore-CcCredentials per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="7dfbc-198">Assicurarsi di immettere la stessa password immessa prima per la distribuzione del connettore Cloud, ad eccezione dell'account CceService.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="7dfbc-199">Per l'account CceService, immettere la nuova password.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="7dfbc-200">Verificare che la nuova password per l'account CceService sia uguale per tutti gli elettrodomestici nel sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="7dfbc-201">Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="7dfbc-202">Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="7dfbc-203">Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="7dfbc-204">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="7dfbc-205">Quando viene richiesto per la nuova credenziale account, immettere la password per la password di DomainAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="7dfbc-206">Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="7dfbc-207">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="7dfbc-208">Quando viene richiesto per la nuova credenziale account, immettere la password per la password di VmAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="7dfbc-209">Eseguire il cmdlet Exit-CcUpdate per spostare l'apparecchio fuori dalla modalità di manutenzione manuale.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="7dfbc-210">Dopo aver completato la procedura in tutti gli elettrodomestici nello stesso sito PSTN, eliminare i seguenti file nella directory radice del sito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="7dfbc-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="7dfbc-211">CcLockFile</span></span>
    
    - <span data-ttu-id="7dfbc-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="7dfbc-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="7dfbc-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="7dfbc-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="7dfbc-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="7dfbc-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="7dfbc-215">Aggiungere un nuovo dominio SIP</span><span class="sxs-lookup"><span data-stu-id="7dfbc-215">Add a new SIP domain</span></span>
<span data-ttu-id="7dfbc-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="7dfbc-217">Per aggiungere un nuovo dominio SIP (o più domini SIP) alla distribuzione del connettore cloud esistente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="7dfbc-218">Assicurarsi di aver completato la procedura per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="7dfbc-219">Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere [aggiungere un dominio a microsoft 365 o office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="7dfbc-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="7dfbc-220">Aggiornare il file di configurazione del connettore Cloud con il nuovo dominio SIP o i domini.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="7dfbc-221">Richiedere un nuovo certificato esterno di Edge con nomi di SAN aggiuntivi per SIP. Domain per ogni dominio SIP definito nella configurazione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="7dfbc-222">Impostare il percorso per il nuovo certificato esterno del server perimetrale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="7dfbc-223">Seguire le istruzioni per [modificare la configurazione di un singolo sito](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [modificare la configurazione di più siti](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="7dfbc-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="7dfbc-224">Modificare il dominio SIP principale</span><span class="sxs-lookup"><span data-stu-id="7dfbc-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="7dfbc-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="7dfbc-226">Se è necessario modificare il dominio SIP principale nella distribuzione del connettore Cloud, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="7dfbc-227">Assicurarsi di aver completato la procedura per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="7dfbc-228">Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere [aggiungere un dominio a microsoft 365 o office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="7dfbc-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="7dfbc-229">Aggiornare il file di configurazione del connettore Cloud con il nuovo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="7dfbc-230">Richiedere un nuovo certificato esterno di Edge con nomi di SAN aggiuntivi per SIP. Domain per ogni dominio SIP definito nella configurazione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="7dfbc-231">Impostare il percorso per il nuovo certificato esterno del server perimetrale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="7dfbc-232">Rimuovere la registrazione del tenant per ogni accessorio in un sito eseguendo il cmdlet seguente in PowerShell amministratore su cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="7dfbc-233">Rimuovere la registrazione del sito per ogni sito eseguendo il seguente cmdlet in PowerShell per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="7dfbc-234">Disinstallare ogni accessorio eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="7dfbc-235">Registrare ogni accessorio eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="7dfbc-236">Installare ogni dispositivo, uno alla volta, eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="7dfbc-237">Sostituire il certificato del perimetro esterno con un nuovo certificato</span><span class="sxs-lookup"><span data-stu-id="7dfbc-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="7dfbc-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="7dfbc-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="7dfbc-239">Quando è necessario sostituire il certificato perimetrale esterno negli apparecchi del connettore Cloud, è necessario ottenere un nuovo certificato Edge, preparare il file PFX contenente la chiave privata e la catena di certificati completi e quindi eseguire le operazioni seguenti in ogni accessorio:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="7dfbc-240">Utilizzare il cmdlet Enter-CcUpdate per attivare la modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="7dfbc-241">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7dfbc-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="7dfbc-242">Se la password del nuovo certificato è identica alla vecchia, l'importazione avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="7dfbc-243">Se la password è diversa, verrà visualizzato un messaggio di errore che indica che la password è errata e sarà necessario reimpostare la password eseguendo il cmdlet Register-CcAppliance con il parametro-local e quindi ripetendo il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="7dfbc-244">Estrarre l'apparecchio dalla modalità di manutenzione utilizzando il cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="7dfbc-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

