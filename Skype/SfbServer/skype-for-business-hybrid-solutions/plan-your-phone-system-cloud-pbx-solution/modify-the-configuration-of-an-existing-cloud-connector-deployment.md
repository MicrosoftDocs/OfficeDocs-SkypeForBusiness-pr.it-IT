---
title: Modificare la configurazione di una distribuzione del connettore cloud esistente
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
ms.openlocfilehash: 77e9940e10cc356afbade5592bf41a0cdba66b0f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779382"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="17a32-103">Modificare la configurazione di una distribuzione del connettore cloud esistente</span><span class="sxs-lookup"><span data-stu-id="17a32-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="17a32-104">Seguire la procedura descritta in questo argomento per modificare la configurazione di una distribuzione di Skype for Business Cloud Connector Edition 1.4.1 o versione successiva esistente.</span><span class="sxs-lookup"><span data-stu-id="17a32-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="17a32-105">Modificare la configurazione di un singolo sito</span><span class="sxs-lookup"><span data-stu-id="17a32-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="17a32-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="17a32-107">Se nel sito è presente un solo dispositivo, quando si desidera modificare le impostazioni di configurazione dopo la distribuzione dell'accessorio, è possibile modificare il file CloudConnector. ini e avviare di nuovo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="17a32-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="17a32-108">Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nel server host:</span><span class="sxs-lookup"><span data-stu-id="17a32-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="17a32-109">Eseguire il seguente cmdlet per annullare la registrazione dell'accessorio:</span><span class="sxs-lookup"><span data-stu-id="17a32-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="17a32-110">Aggiornare il file CloudConnector. ini nella directory appliance.</span><span class="sxs-lookup"><span data-stu-id="17a32-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="17a32-111">Eseguire il cmdlet seguente per aggiornare la configurazione: (questo passaggio è applicabile solo per la versione 2, per le versioni precedenti, passare al passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="17a32-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="17a32-112">Eseguire il cmdlet seguente per registrare nuovamente l'accessorio:</span><span class="sxs-lookup"><span data-stu-id="17a32-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="17a32-113">Eseguire il seguente cmdlet per installare Skype for Business Cloud Connector Edition:</span><span class="sxs-lookup"><span data-stu-id="17a32-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="17a32-114">Se nel sito sono presenti più dispositivi, è necessario attenersi alla procedura seguente, modificare il file CloudConnector. ini e ridistribuire gli elettrodomestici uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="17a32-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="17a32-115">Eseguire il cmdlet seguente per disinstallare tutte le macchine virtuali esistenti nell'accessorio corrente:</span><span class="sxs-lookup"><span data-stu-id="17a32-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="17a32-116">Eseguire il seguente cmdlet per annullare la registrazione dell'accessorio:</span><span class="sxs-lookup"><span data-stu-id="17a32-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="17a32-117">Aggiornare il file CloudConnector. ini nella directory appliance.</span><span class="sxs-lookup"><span data-stu-id="17a32-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="17a32-118">Eseguire il cmdlet seguente per aggiornare la configurazione: (questo passaggio è applicabile solo per la versione 2, per le versioni precedenti, passare al passaggio successivo).</span><span class="sxs-lookup"><span data-stu-id="17a32-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="17a32-119">Eseguire il cmdlet seguente per registrare nuovamente l'accessorio:</span><span class="sxs-lookup"><span data-stu-id="17a32-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="17a32-120">Eseguire il cmdlet seguente in tutti gli altri dispositivi del sito per raccogliere la configurazione più recente:</span><span class="sxs-lookup"><span data-stu-id="17a32-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="17a32-121">Eseguire il cmdlet seguente per ridistribuire il connettore Cloud nell'accessorio corrente:</span><span class="sxs-lookup"><span data-stu-id="17a32-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="17a32-122">Modificare la configurazione di più siti</span><span class="sxs-lookup"><span data-stu-id="17a32-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="17a32-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="17a32-124">Per modificare la configurazione di più siti in una distribuzione, seguire la procedura per un singolo sito, aggiornando un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="17a32-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="17a32-125">Modificare la configurazione dell'organizzazione di Office 365 per abilitare gli aggiornamenti automatici</span><span class="sxs-lookup"><span data-stu-id="17a32-125">Modify the configuration of your Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="17a32-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="17a32-127">Per abilitare gli aggiornamenti automatici del sistema operativo e gli aggiornamenti automatici dei bit, è necessario utilizzare l'account di amministratore del tenant di Skype for business per la gestione online e utilizzare Remote PowerShell tenant come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="17a32-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="17a32-128">Se sono stati disabilitati gli aggiornamenti automatici dei bit o degli aggiornamenti automatici del sistema operativo, l'host e la macchina virtuale potrebbero non essere più importanti per gli aggiornamenti di Windows e Cloud Connector non verrà aggiornato automaticamente alla nuova versione.</span><span class="sxs-lookup"><span data-stu-id="17a32-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="17a32-129">È consigliabile abilitare gli aggiornamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="17a32-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="17a32-130">È necessario che la proprietà EnableAutoUpdate del sito sia impostata su true (il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="17a32-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="17a32-131">Eseguire il cmdlet seguente per assicurarsi che EnableAutoUpdate sia impostato su true:</span><span class="sxs-lookup"><span data-stu-id="17a32-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="17a32-132">Creare la finestra di tempo di aggiornamento automatico per il tenant.</span><span class="sxs-lookup"><span data-stu-id="17a32-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="17a32-133">La finestra temporale può essere giornaliera, settimanale e mensile.</span><span class="sxs-lookup"><span data-stu-id="17a32-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="17a32-134">Tutte le finestre temporali necessitano di un'ora di inizio e una durata.</span><span class="sxs-lookup"><span data-stu-id="17a32-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="17a32-135">Per una finestra di tempo giornaliero, sono necessari solo l'ora di inizio e la durata.</span><span class="sxs-lookup"><span data-stu-id="17a32-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="17a32-136">Per una finestra di tempo settimanale, sono necessari giorni della settimana, che possono essere un solo giorno o più giorni.</span><span class="sxs-lookup"><span data-stu-id="17a32-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="17a32-137">Per una finestra di tempo mensile, possono essere presenti due tipi.</span><span class="sxs-lookup"><span data-stu-id="17a32-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="17a32-138">Il primo tipo è quello di specificare il giorno del mese, che può essere un solo giorno.</span><span class="sxs-lookup"><span data-stu-id="17a32-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="17a32-139">Il secondo tipo è quello di specificare le settimane del mese, insieme ai giorni della settimana, che possono essere entrambi un singolo elemento o più elementi.</span><span class="sxs-lookup"><span data-stu-id="17a32-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="17a32-140">Ogni tenant può disporre di 20 finestre temporali definite.</span><span class="sxs-lookup"><span data-stu-id="17a32-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="17a32-141">La finestra di tempo predefinita verrà creata per un nuovo tenant come finestra temporale predefinita per l'aggiornamento dei sistemi operativi e l'aggiornamento dei bit.</span><span class="sxs-lookup"><span data-stu-id="17a32-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="17a32-142">Eseguire i seguenti cmdlet per impostare la finestra di tempo giornaliero, settimanale o mensile:</span><span class="sxs-lookup"><span data-stu-id="17a32-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="17a32-143">Assegnare le finestre di tempo di aggiornamento al sito.</span><span class="sxs-lookup"><span data-stu-id="17a32-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="17a32-144">Le finestre dell'ora di aggiornamento dei bit e del sistema operativo sono configurate separatamente.</span><span class="sxs-lookup"><span data-stu-id="17a32-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="17a32-145">Entrambe possono essere assegnate a una o più finestre temporali.</span><span class="sxs-lookup"><span data-stu-id="17a32-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="17a32-146">Ogni finestra di tempo può essere assegnata a siti diversi e a un altro scopo (aggiornamento dei bit e aggiornamento del sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="17a32-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="17a32-147">Eseguire il cmdlet seguente per impostare la finestra temporale per il sito:</span><span class="sxs-lookup"><span data-stu-id="17a32-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="17a32-148">Aggiornare le credenziali di amministratore tenant dedicate</span><span class="sxs-lookup"><span data-stu-id="17a32-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="17a32-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="17a32-150">Le modifiche amministrative nell'organizzazione di Office 365 per il connettore Cloud sono eseguite da un account con le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="17a32-150">Administrative changes in the Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="17a32-151">Nelle versioni di connettori cloud precedenti all'2,0, quell'account è un account amministratore globale dedicato del tenant.</span><span class="sxs-lookup"><span data-stu-id="17a32-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="17a32-152">In Cloud Connector Versions 2,0 e versioni successive, quell'account può essere un account di Office 365 con i diritti di amministratore di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="17a32-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="17a32-153">Se le credenziali dell'account di amministratore cambiano in Office 365, è inoltre necessario aggiornare le credenziali memorizzate nella cache locale in Cloud Connector eseguendo il comando di PowerShell di amministratore seguente su ogni accessorio Cloud Connector distribuito:</span><span class="sxs-lookup"><span data-stu-id="17a32-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="17a32-154">Aggiornare la password per il server host</span><span class="sxs-lookup"><span data-stu-id="17a32-154">Update the password for the host server</span></span>
<span data-ttu-id="17a32-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="17a32-156">Questa sezione è applicabile al connettore Cloud versione 2,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="17a32-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="17a32-157">Tutte le credenziali del connettore Cloud sono archiviate nel file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="17a32-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="17a32-158">Quando la password sul server host cambia, sarà necessario aggiornare le credenziali memorizzate localmente.</span><span class="sxs-lookup"><span data-stu-id="17a32-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="17a32-159">Per aggiornare le credenziali memorizzate localmente nell'accessorio Cloud Connector, utilizzare i cmdlet [Get-CcCredential](get-cccredential.md) e [set-CcCredential](set-cccredential.md) e attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="17a32-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="17a32-160">Eseguire i seguenti comandi per recuperare le password necessarie in un secondo momento:</span><span class="sxs-lookup"><span data-stu-id="17a32-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="17a32-161">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="17a32-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="17a32-162">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="17a32-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="17a32-163">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="17a32-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="17a32-164">Modificare la password dell'account sul server host.</span><span class="sxs-lookup"><span data-stu-id="17a32-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="17a32-165">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="17a32-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="17a32-166">Eliminare il file seguente: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="17a32-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="17a32-167">Avviare una console di PowerShell come amministratore e quindi eseguire "Register-CcAppliance-local" per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="17a32-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="17a32-168">Assicurarsi di immettere la stessa password immessa prima per la distribuzione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="17a32-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="17a32-169">Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService.</span><span class="sxs-lookup"><span data-stu-id="17a32-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="17a32-170">Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="17a32-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="17a32-171">Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="17a32-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="17a32-172">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="17a32-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="17a32-173">Quando viene richiesto per la nuova credenziale account, immettere la password per la password di DomainAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="17a32-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="17a32-174">Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="17a32-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="17a32-175">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="17a32-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="17a32-176">Quando viene richiesto per la nuova credenziale account, immettere la password per la password di VmAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="17a32-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="17a32-177">Aggiornare la password per l'account CceService</span><span class="sxs-lookup"><span data-stu-id="17a32-177">Update the password for the CceService account</span></span>
<span data-ttu-id="17a32-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="17a32-179">Questa sezione è applicabile a Cloud Connector versione 2.0.1 e successive.</span><span class="sxs-lookup"><span data-stu-id="17a32-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="17a32-180">Il servizio Cloud Connector esegue il servizio di gestione Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="17a32-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="17a32-181">L'account CceService viene creato durante la distribuzione di Cloud Connector Edition e archiviato nei file seguenti: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "e"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".</span><span class="sxs-lookup"><span data-stu-id="17a32-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="17a32-182">Per assicurarsi che tutti gli apparecchi possano accedere alla condivisione directory del sito, la password per l'account CceService deve essere identica su tutti gli elettrodomestici distribuiti all'interno del sito.</span><span class="sxs-lookup"><span data-stu-id="17a32-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="17a32-183">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="17a32-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="17a32-184">Per impostazione predefinita, l'account CceService è configurato come "password non scade mai".</span><span class="sxs-lookup"><span data-stu-id="17a32-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="17a32-185">Quando si aggiorna la password, Microsoft consiglia di mantenere la configurazione.</span><span class="sxs-lookup"><span data-stu-id="17a32-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="17a32-186">È necessario aggiornare la password durante periodi di utilizzo non di picco e al di fuori delle finestre di tempo di aggiornamento automatico per i bit o gli aggiornamenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="17a32-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="17a32-187">Quando si aggiorna la password, l'accessorio deve essere svuotato e riavviato, che richiede un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="17a32-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="17a32-188">Il riavvio dell'accessorio interromperà le operazioni di aggiornamento automatico.</span><span class="sxs-lookup"><span data-stu-id="17a32-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="17a32-189">Quando si modifica la password dell'account CceService, sarà necessario specificare tutte le credenziali e aggiornarle nel file archiviato localmente.</span><span class="sxs-lookup"><span data-stu-id="17a32-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="17a32-190">Per ogni accessorio che appartiene allo stesso sito PSTN, è necessario specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="17a32-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="17a32-191">Eseguire i seguenti comandi per recuperare i nomi account e le password che verranno utilizzate in un secondo momento:</span><span class="sxs-lookup"><span data-stu-id="17a32-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="17a32-192">Eseguire il cmdlet Enter-CcUpdate per svuotare l'accessorio e spostarlo in modalità di manutenzione manuale.</span><span class="sxs-lookup"><span data-stu-id="17a32-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="17a32-193">Aggiornare la password dell'account CceService sul server host.</span><span class="sxs-lookup"><span data-stu-id="17a32-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="17a32-194">Riavviare il server host.</span><span class="sxs-lookup"><span data-stu-id="17a32-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="17a32-195">Eseguire il cmdlet Restore-CcCredentials per immettere di nuovo le password dopo la descrizione.</span><span class="sxs-lookup"><span data-stu-id="17a32-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="17a32-196">Assicurarsi di immettere la stessa password immessa prima per la distribuzione del connettore Cloud, ad eccezione dell'account CceService.</span><span class="sxs-lookup"><span data-stu-id="17a32-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="17a32-197">Per l'account CceService, immettere la nuova password.</span><span class="sxs-lookup"><span data-stu-id="17a32-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="17a32-198">Verificare che la nuova password per l'account CceService sia uguale per tutti gli elettrodomestici nel sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="17a32-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="17a32-199">Per impostazione predefinita, VmAdmin e DomainAdmin utilizzano la stessa password di CceService.</span><span class="sxs-lookup"><span data-stu-id="17a32-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="17a32-200">Se le password DomainAdmin, VMAdmin e CceService restituite nel passaggio 1 sono diverse, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="17a32-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="17a32-201">Eseguire set-CcCredential-AccountType DomainAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="17a32-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="17a32-202">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="17a32-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="17a32-203">Quando viene richiesto per la nuova credenziale account, immettere la password per la password di DomainAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="17a32-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="17a32-204">Eseguire set-CcCredential-AccountType VmAdmin come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="17a32-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="17a32-205">Quando viene richiesto di utilizzare le credenziali per l'account precedente, immettere le credenziali utilizzate per la password di CceService.</span><span class="sxs-lookup"><span data-stu-id="17a32-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="17a32-206">Quando viene richiesto per la nuova credenziale account, immettere la password per la password di VmAdmin restituita nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="17a32-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="17a32-207">Eseguire il cmdlet Exit-CcUpdate per spostare l'apparecchio fuori dalla modalità di manutenzione manuale.</span><span class="sxs-lookup"><span data-stu-id="17a32-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="17a32-208">Dopo aver completato la procedura in tutti gli elettrodomestici nello stesso sito PSTN, eliminare i seguenti file nella directory radice del sito:</span><span class="sxs-lookup"><span data-stu-id="17a32-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="17a32-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="17a32-209">CcLockFile</span></span>
    
    - <span data-ttu-id="17a32-210">FQDN\<del pool Sip esterno Site_ Edge\></span><span class="sxs-lookup"><span data-stu-id="17a32-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="17a32-211">FQDN\<del pool Sip esterno Tenant_ Edge\></span><span class="sxs-lookup"><span data-stu-id="17a32-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="17a32-212">FQDN\<del pool Sip esterno TenantConfigLock_ Edge\></span><span class="sxs-lookup"><span data-stu-id="17a32-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="17a32-213">Aggiungere un nuovo dominio SIP</span><span class="sxs-lookup"><span data-stu-id="17a32-213">Add a new SIP domain</span></span>
<span data-ttu-id="17a32-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="17a32-215">Per aggiungere un nuovo dominio SIP (o più domini SIP) alla distribuzione del connettore cloud esistente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="17a32-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="17a32-216">Assicurarsi di aver completato la procedura per aggiornare il dominio in Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="17a32-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="17a32-217">Per ulteriori informazioni su come configurare il dominio in Office 365, vedere [aggiungere un dominio a office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="17a32-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="17a32-218">Aggiornare il file di configurazione del connettore Cloud con il nuovo dominio SIP o i domini.</span><span class="sxs-lookup"><span data-stu-id="17a32-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="17a32-219">Richiedere un nuovo certificato esterno di Edge con nomi di SAN aggiuntivi per SIP. Domain per ogni dominio SIP definito nella configurazione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="17a32-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="17a32-220">Impostare il percorso per il nuovo certificato esterno del server perimetrale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="17a32-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="17a32-221">Seguire le istruzioni per [modificare la configurazione di un singolo sito](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) o [modificare la configurazione di più siti](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span><span class="sxs-lookup"><span data-stu-id="17a32-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="17a32-222">Modificare il dominio SIP principale</span><span class="sxs-lookup"><span data-stu-id="17a32-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="17a32-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="17a32-224">Se è necessario modificare il dominio SIP principale nella distribuzione del connettore Cloud, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="17a32-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="17a32-225">Assicurarsi di aver completato la procedura per aggiornare il dominio in Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="17a32-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="17a32-226">Per ulteriori informazioni su come configurare il dominio in Office 365, vedere [aggiungere un dominio a office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="17a32-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="17a32-227">Aggiornare il file di configurazione del connettore Cloud con il nuovo dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="17a32-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="17a32-228">Richiedere un nuovo certificato esterno di Edge con nomi di SAN aggiuntivi per SIP. Domain per ogni dominio SIP definito nella configurazione del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="17a32-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="17a32-229">Impostare il percorso per il nuovo certificato esterno del server perimetrale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="17a32-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="17a32-230">Rimuovere la registrazione del tenant per ogni accessorio in un sito eseguendo il cmdlet seguente in PowerShell amministratore su cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="17a32-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="17a32-231">Rimuovere la registrazione del sito per ogni sito eseguendo il seguente cmdlet in PowerShell per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="17a32-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="17a32-232">Disinstallare ogni accessorio eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="17a32-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="17a32-233">Registrare ogni accessorio eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="17a32-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="17a32-234">Installare ogni dispositivo, uno alla volta, eseguendo il cmdlet seguente in PowerShell Administrator sul connettore Cloud:</span><span class="sxs-lookup"><span data-stu-id="17a32-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="17a32-235">Sostituire il certificato del perimetro esterno con un nuovo certificato</span><span class="sxs-lookup"><span data-stu-id="17a32-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="17a32-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="17a32-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="17a32-237">Quando è necessario sostituire il certificato perimetrale esterno negli apparecchi del connettore Cloud, è necessario ottenere un nuovo certificato Edge, preparare il file PFX contenente la chiave privata e la catena di certificati completi e quindi eseguire le operazioni seguenti in ogni accessorio:</span><span class="sxs-lookup"><span data-stu-id="17a32-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="17a32-238">Utilizzare il cmdlet Enter-CcUpdate per attivare la modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="17a32-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="17a32-239">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="17a32-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="17a32-240">Se la password del nuovo certificato è identica alla vecchia, l'importazione avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="17a32-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="17a32-241">Se la password è diversa, verrà visualizzato un messaggio di errore che indica che la password è errata e sarà necessario reimpostare la password eseguendo il cmdlet Register-CcAppliance con il parametro-local e quindi ripetendo il passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="17a32-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="17a32-242">Estrarre l'apparecchio dalla modalità di manutenzione utilizzando il cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="17a32-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

