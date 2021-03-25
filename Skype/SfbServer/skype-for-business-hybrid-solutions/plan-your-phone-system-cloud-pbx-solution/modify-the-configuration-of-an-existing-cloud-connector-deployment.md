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
description: Seguire i passaggi descritti in questo argomento per modificare la configurazione di una distribuzione esistente di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva.
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109172"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="522f5-103">Modificare la configurazione di una distribuzione di Cloud Connector esistente</span><span class="sxs-lookup"><span data-stu-id="522f5-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="522f5-104">Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="522f5-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="522f5-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="522f5-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="522f5-106">Seguire i passaggi descritti in questo argomento per modificare la configurazione di una distribuzione esistente di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="522f5-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="522f5-107">Modificare la configurazione di un singolo sito</span><span class="sxs-lookup"><span data-stu-id="522f5-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="522f5-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="522f5-109">Se nel sito è presente un solo dispositivo, quando si desidera modificare le impostazioni di configurazione dopo la distribuzione dell'appliance, è possibile modificare il file CloudConnector.ini e avviare di nuovo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="522f5-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="522f5-110">Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nel server host:</span><span class="sxs-lookup"><span data-stu-id="522f5-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="522f5-111">Eseguire il cmdlet seguente per annullare la registrazione dell'appliance:</span><span class="sxs-lookup"><span data-stu-id="522f5-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="522f5-112">Aggiornare il CloudConnector.ini file nella directory appliance.</span><span class="sxs-lookup"><span data-stu-id="522f5-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="522f5-113">Eseguire il cmdlet seguente per aggiornare la configurazione: Questo passaggio è applicabile solo alla versione 2. Per le versioni precedenti, passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="522f5-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="522f5-114">Eseguire il cmdlet seguente per registrare di nuovo l'appliance:</span><span class="sxs-lookup"><span data-stu-id="522f5-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="522f5-115">Eseguire il cmdlet seguente per installare Skype for Business Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="522f5-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="522f5-116">Se nel sito sono presenti più appliance, è necessario eseguire la procedura seguente, modificare il file CloudConnector.ini e ridistribuire le appliance una alla volta.</span><span class="sxs-lookup"><span data-stu-id="522f5-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="522f5-117">Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nell'appliance corrente:</span><span class="sxs-lookup"><span data-stu-id="522f5-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="522f5-118">Eseguire il cmdlet seguente per annullare la registrazione dell'appliance:</span><span class="sxs-lookup"><span data-stu-id="522f5-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="522f5-119">Aggiornare il CloudConnector.ini file nella directory appliance.</span><span class="sxs-lookup"><span data-stu-id="522f5-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="522f5-120">Eseguire il cmdlet seguente per aggiornare la configurazione: Questo passaggio è applicabile solo alla versione 2. Per le versioni precedenti, passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="522f5-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="522f5-121">Eseguire il cmdlet seguente per registrare di nuovo l'appliance:</span><span class="sxs-lookup"><span data-stu-id="522f5-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="522f5-122">Eseguire il cmdlet seguente in tutte le altre appliance del sito per prelevare la configurazione più recente:</span><span class="sxs-lookup"><span data-stu-id="522f5-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="522f5-123">Eseguire il cmdlet seguente per ridistribuire Cloud Connector nell'appliance corrente:</span><span class="sxs-lookup"><span data-stu-id="522f5-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="522f5-124">Modificare la configurazione di più siti</span><span class="sxs-lookup"><span data-stu-id="522f5-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="522f5-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="522f5-126">Per modificare la configurazione per più siti in una distribuzione, seguire i passaggi per un singolo sito, aggiornando un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="522f5-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="522f5-127">Modificare la configurazione dell'organizzazione di Microsoft 365 o Office 365 per abilitare gli aggiornamenti automatici</span><span class="sxs-lookup"><span data-stu-id="522f5-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="522f5-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="522f5-129">Per abilitare gli aggiornamenti automatici del sistema operativo e gli aggiornamenti automatici bit, devi usare l'account di amministratore tenant di Skype for Business per la gestione online e usare PowerShell remoto tenant come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="522f5-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="522f5-130">Se sono stati disabilitati gli aggiornamenti automatici del sistema operativo o gli aggiornamenti automatici di Bits, l'host e la macchina virtuale potrebbero perdere aggiornamenti importanti di Windows e Cloud Connector non verrà aggiornato automaticamente alla nuova versione.</span><span class="sxs-lookup"><span data-stu-id="522f5-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="522f5-131">È consigliabile abilitare gli aggiornamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="522f5-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="522f5-132">La proprietà EnableAutoUpdate del sito deve essere impostata su true (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="522f5-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="522f5-133">Eseguire il cmdlet seguente per assicurarsi che EnableAutoUpdate sia impostato su true:</span><span class="sxs-lookup"><span data-stu-id="522f5-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="522f5-134">Creare un intervallo di tempo di aggiornamento automatico per il tenant.</span><span class="sxs-lookup"><span data-stu-id="522f5-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="522f5-135">L'intervallo di tempo può essere giornaliero, settimanale e mensile.</span><span class="sxs-lookup"><span data-stu-id="522f5-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="522f5-136">Tutte le finestre di tempo necessitano di un'ora di inizio e di una durata.</span><span class="sxs-lookup"><span data-stu-id="522f5-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="522f5-137">Per un intervallo di tempo giornaliero, sono necessarie solo l'ora di inizio e la durata.</span><span class="sxs-lookup"><span data-stu-id="522f5-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="522f5-138">Per un intervallo di tempo settimanale, sono necessari giorni della settimana, che possono essere un solo giorno o più giorni.</span><span class="sxs-lookup"><span data-stu-id="522f5-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="522f5-139">Per un intervallo di tempo mensile, possono essere disponibili due tipi.</span><span class="sxs-lookup"><span data-stu-id="522f5-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="522f5-140">Il primo tipo è specificare il giorno del mese, che può essere un singolo giorno.</span><span class="sxs-lookup"><span data-stu-id="522f5-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="522f5-141">Il secondo tipo è specificare le settimane del mese, insieme ai giorni della settimana, che possono essere entrambi un singolo elemento o più elementi.</span><span class="sxs-lookup"><span data-stu-id="522f5-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="522f5-142">Ogni tenant può avere 20 finestre di tempo definite.</span><span class="sxs-lookup"><span data-stu-id="522f5-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="522f5-143">L'intervallo di tempo predefinito verrà creato per un nuovo tenant come intervallo di tempo predefinito per l'aggiornamento del sistema operativo e l'aggiornamento dei bit.</span><span class="sxs-lookup"><span data-stu-id="522f5-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="522f5-144">Eseguire i cmdlet seguenti per impostare l'intervallo di tempo giornaliero, settimanale o mensile:</span><span class="sxs-lookup"><span data-stu-id="522f5-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="522f5-145">Assegnare le finestre dell'ora di aggiornamento al sito.</span><span class="sxs-lookup"><span data-stu-id="522f5-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="522f5-146">Le finestre Ora aggiornamento bit e Ora aggiornamento sistema operativo sono configurate separatamente.</span><span class="sxs-lookup"><span data-stu-id="522f5-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="522f5-147">A entrambi è possibile assegnare finestre singole o multiple.</span><span class="sxs-lookup"><span data-stu-id="522f5-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="522f5-148">Ogni intervallo di tempo può essere assegnato a siti diversi e a scopi diversi (aggiornamento dei bit e aggiornamento del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="522f5-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="522f5-149">Eseguire il cmdlet seguente per impostare l'intervallo di tempo per il sito:</span><span class="sxs-lookup"><span data-stu-id="522f5-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="522f5-150">Aggiornare le credenziali di amministratore tenant dedicato</span><span class="sxs-lookup"><span data-stu-id="522f5-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="522f5-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="522f5-152">Le modifiche amministrative nell'organizzazione di Microsoft 365 o Office 365 per Cloud Connector vengono apportate da un account con le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="522f5-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="522f5-153">Nelle versioni di Cloud Connector precedenti alla 2.0, tale account è un account amministratore tenant globale dedicato.</span><span class="sxs-lookup"><span data-stu-id="522f5-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="522f5-154">In Cloud Connector versioni 2.0 e successive, tale account può essere un account di Microsoft 365 o Office 365 con diritti di amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="522f5-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="522f5-155">Se le credenziali dell'account amministratore cambiano in Microsoft 365 o Office 365, è inoltre necessario aggiornare le credenziali memorizzate localmente nella cache in Cloud Connector eseguendo il seguente comando di Amministratore PowerShell in ogni appliance del connettore cloud distribuita:</span><span class="sxs-lookup"><span data-stu-id="522f5-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="522f5-156">Aggiornare la password per il server host</span><span class="sxs-lookup"><span data-stu-id="522f5-156">Update the password for the host server</span></span>
<span data-ttu-id="522f5-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="522f5-158">Questa sezione è applicabile a Cloud Connector versione 2.0 e successive.</span><span class="sxs-lookup"><span data-stu-id="522f5-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="522f5-159">Tutte le credenziali del connettore cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".</span><span class="sxs-lookup"><span data-stu-id="522f5-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="522f5-160">Quando la password nel server host cambia, sarà necessario aggiornare le credenziali archiviate localmente.</span><span class="sxs-lookup"><span data-stu-id="522f5-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="522f5-161">Per aggiornare le credenziali archiviate localmente nell'appliance Cloud Connector, utilizzare i cmdlet [Get-CcCredential](get-cccredential.md) e [Set-CcCredential](set-cccredential.md) ed eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="522f5-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="522f5-162">Eseguire i comandi seguenti per recuperare le password necessarie in un secondo momento:</span><span class="sxs-lookup"><span data-stu-id="522f5-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="522f5-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="522f5-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="522f5-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="522f5-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="522f5-165">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="522f5-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="522f5-166">Modificare la password dell'account nel server host.</span><span class="sxs-lookup"><span data-stu-id="522f5-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="522f5-167">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="522f5-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="522f5-168">Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="522f5-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="522f5-169">Avviare una console di PowerShell come amministratore, quindi eseguire "Register-CcAppliance -Local" per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="522f5-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="522f5-170">Assicurati di immettere la stessa password immessa prima per la distribuzione di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="522f5-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="522f5-171">Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService.</span><span class="sxs-lookup"><span data-stu-id="522f5-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="522f5-172">Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="522f5-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="522f5-173">Eseguire Set-CcCredential -AccountType DomainAdmin come segue:</span><span class="sxs-lookup"><span data-stu-id="522f5-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="522f5-174">Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="522f5-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="522f5-175">Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password DomainAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="522f5-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="522f5-176">Eseguire Set-CcCredential -AccountType VmAdmin come segue:</span><span class="sxs-lookup"><span data-stu-id="522f5-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="522f5-177">Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="522f5-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="522f5-178">Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password VmAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="522f5-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="522f5-179">Aggiornare la password per l'account CceService</span><span class="sxs-lookup"><span data-stu-id="522f5-179">Update the password for the CceService account</span></span>
<span data-ttu-id="522f5-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="522f5-181">Questa sezione è applicabile a Cloud Connector versione 2.0.1 e successive.</span><span class="sxs-lookup"><span data-stu-id="522f5-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="522f5-182">Il servizio Cloud Connector esegue il servizio di gestione dei connettori cloud.</span><span class="sxs-lookup"><span data-stu-id="522f5-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="522f5-183">L'account CceService viene creato durante la distribuzione di Cloud Connector Edition e archiviato nei file seguenti: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" e "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span><span class="sxs-lookup"><span data-stu-id="522f5-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="522f5-184">Per garantire che tutte le appliance possano accedere alla condivisione di directory del sito, la password per l'account CceService deve essere la stessa in tutte le appliance distribuite all'interno del sito.</span><span class="sxs-lookup"><span data-stu-id="522f5-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="522f5-185">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="522f5-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="522f5-186">Per impostazione predefinita, l'account CceService è configurato come "Password never expires".</span><span class="sxs-lookup"><span data-stu-id="522f5-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="522f5-187">Quando si aggiorna la password, Microsoft consiglia di mantenere questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="522f5-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="522f5-188">È consigliabile aggiornare la password durante i periodi di utilizzo non di picco e al di fuori delle finestre di tempo di aggiornamento automatico per bit o aggiornamenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="522f5-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="522f5-189">Quando si aggiorna la password, l'appliance deve essere svuotata e riavviata, il che richiede tempo.</span><span class="sxs-lookup"><span data-stu-id="522f5-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="522f5-190">Il riavvio dell'appliance interromperà le operazioni di aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="522f5-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="522f5-191">Quando si modifica la password dell'account CceService, sarà necessario specificare tutte le credenziali e aggiornarle nel file archiviato localmente.</span><span class="sxs-lookup"><span data-stu-id="522f5-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="522f5-192">Per ogni appliance appartenente allo stesso sito PSTN, è necessario specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="522f5-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="522f5-193">Eseguire i comandi seguenti per recuperare i nomi e le password degli account che verranno utilizzati in seguito:</span><span class="sxs-lookup"><span data-stu-id="522f5-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="522f5-194">Eseguire il cmdlet Enter-CcUpdate per svuotare l'appliance e spostarlo in modalità di manutenzione manuale.</span><span class="sxs-lookup"><span data-stu-id="522f5-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="522f5-195">Aggiornare la password dell'account CceService nel server host.</span><span class="sxs-lookup"><span data-stu-id="522f5-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="522f5-196">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="522f5-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="522f5-197">Eseguire il cmdlet Restore-CcCredentials per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="522f5-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="522f5-198">Assicurati di immettere la stessa password immessa in precedenza per la distribuzione di Cloud Connector ad eccezione dell'account CceService.</span><span class="sxs-lookup"><span data-stu-id="522f5-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="522f5-199">Per l'account CceService, immettere la nuova password.</span><span class="sxs-lookup"><span data-stu-id="522f5-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="522f5-200">Verificare che la nuova password per l'account CceService sia la stessa per tutte le appliance nel sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="522f5-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="522f5-201">Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService.</span><span class="sxs-lookup"><span data-stu-id="522f5-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="522f5-202">Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="522f5-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="522f5-203">Eseguire Set-CcCredential -AccountType DomainAdmin come segue:</span><span class="sxs-lookup"><span data-stu-id="522f5-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="522f5-204">Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="522f5-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="522f5-205">Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password DomainAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="522f5-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="522f5-206">Eseguire Set-CcCredential -AccountType VmAdmin come segue:</span><span class="sxs-lookup"><span data-stu-id="522f5-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="522f5-207">Quando viene richiesto di immettere la credenziale dell'account precedente, immettere la credenziale utilizzata per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="522f5-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="522f5-208">Quando viene richiesta la nuova credenziale dell'account, immettere la password per la password VmAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="522f5-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="522f5-209">Eseguire il cmdlet Exit-CcUpdate per spostare l'appliance fuori dalla modalità di manutenzione manuale.</span><span class="sxs-lookup"><span data-stu-id="522f5-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="522f5-210">Dopo aver completato questi passaggi in tutte le appliance nello stesso sito PSTN, eliminare i file seguenti nella directory radice del sito:</span><span class="sxs-lookup"><span data-stu-id="522f5-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="522f5-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="522f5-211">CcLockFile</span></span>
    
    - <span data-ttu-id="522f5-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="522f5-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="522f5-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="522f5-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="522f5-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="522f5-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="522f5-215">Aggiungere un nuovo dominio SIP</span><span class="sxs-lookup"><span data-stu-id="522f5-215">Add a new SIP domain</span></span>
<span data-ttu-id="522f5-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="522f5-217">Per aggiungere un nuovo dominio SIP (o più domini SIP) alla distribuzione esistente di Cloud Connector, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="522f5-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="522f5-218">Assicurarsi di aver completato i passaggi per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="522f5-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="522f5-219">Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere Aggiungere un dominio [a Microsoft 365 o Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="522f5-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="522f5-220">Aggiornare il file di configurazione del connettore cloud con il nuovo dominio SIP o i nuovi domini.</span><span class="sxs-lookup"><span data-stu-id="522f5-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="522f5-221">Richiedere un nuovo certificato esterno Edge con nomi SAN aggiuntivi per sip.domain per ogni dominio SIP definito nella configurazione del connettore cloud.</span><span class="sxs-lookup"><span data-stu-id="522f5-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="522f5-222">Impostare il percorso per il nuovo certificato esterno edge come segue:</span><span class="sxs-lookup"><span data-stu-id="522f5-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="522f5-223">Seguire le istruzioni per [Modificare la configurazione di un singolo sito](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o Modificare la configurazione di più [siti.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)</span><span class="sxs-lookup"><span data-stu-id="522f5-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="522f5-224">Modificare il dominio SIP primario</span><span class="sxs-lookup"><span data-stu-id="522f5-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="522f5-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="522f5-226">Se è necessario modificare il dominio SIP primario nella distribuzione di Cloud Connector, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="522f5-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="522f5-227">Assicurarsi di aver completato i passaggi per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="522f5-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="522f5-228">Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere Aggiungere un dominio [a Microsoft 365 o Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="522f5-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="522f5-229">Aggiornare il file di configurazione del connettore cloud con il nuovo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="522f5-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="522f5-230">Richiedere un nuovo certificato esterno Edge con nomi SAN aggiuntivi per sip.domain per ogni dominio SIP definito nella configurazione del connettore cloud.</span><span class="sxs-lookup"><span data-stu-id="522f5-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="522f5-231">Impostare il percorso per il nuovo certificato esterno edge come segue:</span><span class="sxs-lookup"><span data-stu-id="522f5-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="522f5-232">Rimuovere la registrazione tenant per ogni appliance in un sito eseguendo il cmdlet seguente in PowerShell per l'amministratore in Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="522f5-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="522f5-233">Rimuovere la registrazione del sito per ogni sito eseguendo il cmdlet seguente in PowerShell di Skype for Business online:</span><span class="sxs-lookup"><span data-stu-id="522f5-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="522f5-234">Disinstallare ogni appliance eseguendo il cmdlet seguente in PowerShell per l'amministratore nel connettore cloud:</span><span class="sxs-lookup"><span data-stu-id="522f5-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="522f5-235">Registrare ogni appliance eseguendo il cmdlet seguente in PowerShell per l'amministratore in Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="522f5-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="522f5-236">Installare ogni appliance, uno per uno, eseguendo il cmdlet seguente in PowerShell per l'amministratore in Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="522f5-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="522f5-237">Sostituire il certificato edge esterno con un nuovo certificato</span><span class="sxs-lookup"><span data-stu-id="522f5-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="522f5-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="522f5-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="522f5-239">Quando è necessario sostituire il certificato edge esterno nelle appliance Cloud Connector, è necessario ottenere un nuovo certificato Edge, preparare il file PFX contenente la chiave privata e la catena di certificati completa e quindi eseguire le operazioni seguenti in ogni appliance:</span><span class="sxs-lookup"><span data-stu-id="522f5-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="522f5-240">Impostare l'appliance in modalità manutenzione utilizzando il cmdlet Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="522f5-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="522f5-241">Eseguire il comando qui riportato:</span><span class="sxs-lookup"><span data-stu-id="522f5-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="522f5-242">Se la password del nuovo certificato è uguale a quella precedente, l'importazione avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="522f5-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="522f5-243">Se la password è diversa, verrà visualizzato un errore che indica che la password non è corretta e sarà necessario reimpostarla eseguendo il cmdlet Register-CcAppliance con il parametro -Local e quindi ripetendo il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="522f5-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="522f5-244">Rimuovere l'appliance dalla modalità di manutenzione utilizzando il cmdlet Exit -CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="522f5-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
