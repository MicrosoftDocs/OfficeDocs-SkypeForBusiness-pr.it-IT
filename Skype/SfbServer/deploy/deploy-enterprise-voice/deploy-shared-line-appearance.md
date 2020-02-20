---
title: Distribuire l'aspetto della linea condivisa in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Leggere questo argomento per informazioni su come distribuire l'aspetto di linea condiviso (SLA, Shared Line Appearance) in Skype for Business Server 2015, novembre 2015 Cumulative Update. SLA è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.
ms.openlocfilehash: 2009b313b343d9746f3eeff5f53fec4899c2f9a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129309"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="c2e47-104">Distribuire l'aspetto della linea condivisa in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c2e47-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="c2e47-105">Leggere questo argomento per informazioni su come distribuire l'aspetto di linea condiviso (SLA, Shared Line Appearance) in Skype for Business Server 2015, novembre 2015 Cumulative Update.</span><span class="sxs-lookup"><span data-stu-id="c2e47-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="c2e47-106">SLA è una funzionalità per la gestione di più chiamate su un numero specifico denominato numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="c2e47-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="c2e47-107">Per ulteriori informazioni su questa funzionalità, vedere [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="c2e47-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="c2e47-108">SLA (Shared Line Appearance) è una nuova funzionalità di Skype for Business Server, aggiornamento cumulativo di novembre 2015.</span><span class="sxs-lookup"><span data-stu-id="c2e47-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="c2e47-109">Per abilitare questa funzionalità, è necessario che sia stata distribuita per la prima volta questo aggiornamento cumulativo.</span><span class="sxs-lookup"><span data-stu-id="c2e47-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="c2e47-110">Installare l'aspetto della linea condivisa</span><span class="sxs-lookup"><span data-stu-id="c2e47-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="c2e47-111">Dopo aver distribuito l'aggiornamento cumulativo di Skype for Business Server, novembre 2015, `SkypeServerUpdateInstaller.exe` eseguire la patch su ogni Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="c2e47-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="c2e47-112">Il programma di installazione distribuirà la versione più recente dell'applicazione SLA, tuttavia, l'applicazione non è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c2e47-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="c2e47-113">Questa impostazione è abilitata attenendosi alla procedura descritta di seguito:</span><span class="sxs-lookup"><span data-stu-id="c2e47-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="c2e47-114">a.</span><span class="sxs-lookup"><span data-stu-id="c2e47-114">a.</span></span> <span data-ttu-id="c2e47-115">Registrare SLA come applicazione server eseguendo il comando seguente per ogni pool:</span><span class="sxs-lookup"><span data-stu-id="c2e47-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="c2e47-116">dove% FQDN% è il nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="c2e47-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="c2e47-117">b.</span><span class="sxs-lookup"><span data-stu-id="c2e47-117">b.</span></span> <span data-ttu-id="c2e47-118">Eseguire il seguente comando per aggiornare i ruoli RBAC per i cmdlet di SLA:</span><span class="sxs-lookup"><span data-stu-id="c2e47-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="c2e47-119">c.</span><span class="sxs-lookup"><span data-stu-id="c2e47-119">c.</span></span> <span data-ttu-id="c2e47-120">Riavviare tutti i Front End Server (servizio RTCSRV) in tutti i pool in cui è stato installato e abilitato SLA:</span><span class="sxs-lookup"><span data-stu-id="c2e47-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="c2e47-121">Creare un gruppo di SLA e aggiungervi gli utenti</span><span class="sxs-lookup"><span data-stu-id="c2e47-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="c2e47-122">Creare il gruppo di SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c2e47-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="c2e47-123">Il cmdlet Set-CsSlaConfiguration contrassegna l'account VoIP dell'organizzazione SLAGroup1 come entità SLA e il numero di SLAGroup1 diventa il numero del gruppo di SLA.</span><span class="sxs-lookup"><span data-stu-id="c2e47-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="c2e47-124">Tutte le chiamate a SLAGroup1 suoneranno l'intero gruppo del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="c2e47-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="c2e47-125">Nell'esempio seguente viene creato un gruppo di SLA per un utente VoIP aziendale esistente, SLAGroup1, e viene utilizzato il numero assegnato a SLAGroup1 come numero della linea principale del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="c2e47-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="c2e47-126">Il comando imposta il numero massimo di chiamate simultanee per il nuovo gruppo di SLA su 3 e per le chiamate superiori a quelle per ascoltare un segnale di occupato:</span><span class="sxs-lookup"><span data-stu-id="c2e47-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="c2e47-127">È possibile utilizzare set-CsSlaConfiguration per creare un nuovo gruppo di SLA o modificarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="c2e47-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2e47-128">Si noti che il valore specificato `-Identity` per deve essere un account utente esistente abilitato per VoIP aziendale valido.</span><span class="sxs-lookup"><span data-stu-id="c2e47-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="c2e47-129">Aggiungere delegati al gruppo utilizzando il cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c2e47-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="c2e47-130">Nell'esempio seguente viene aggiunto un utente al gruppo di SLA.</span><span class="sxs-lookup"><span data-stu-id="c2e47-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="c2e47-131">Ogni utente aggiunto al gruppo deve essere un utente abilitato VoIP aziendale valido:</span><span class="sxs-lookup"><span data-stu-id="c2e47-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="c2e47-132">Ripetere il cmdlet per ogni utente che si desidera aggiungere al gruppo.</span><span class="sxs-lookup"><span data-stu-id="c2e47-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="c2e47-133">Gli utenti possono appartenere solo a un singolo gruppo di SLA.</span><span class="sxs-lookup"><span data-stu-id="c2e47-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="c2e47-134">Configurare l'opzione occupato del gruppo di SLA</span><span class="sxs-lookup"><span data-stu-id="c2e47-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="c2e47-135">Configurare l'opzione occupato del gruppo di SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c2e47-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="c2e47-136">Nell'esempio seguente vengono impostate le chiamate che superano il numero massimo di chiamate simultanee da inoltrare al numero di telefono 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="c2e47-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="c2e47-137">La destinazione potrebbe essere un utente dell'organizzazione invece di un numero di telefono; in tal caso, la sintassi per la persona che riceve le chiamate inoltrate è la stessa di quando si specifica un delegato: `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="c2e47-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="c2e47-138">L'altro parametro possibile per `BusyOption` è `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="c2e47-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="c2e47-139">Configurare l'opzione di chiamata senza risposta del gruppo di SLA</span><span class="sxs-lookup"><span data-stu-id="c2e47-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="c2e47-140">Configurare l'opzione di chiamata senza risposta del gruppo SLA utilizzando il cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c2e47-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="c2e47-141">Nell'esempio seguente viene specificato che le chiamate perse devono essere inoltrate all'utente `sla_forward_number`denominato.</span><span class="sxs-lookup"><span data-stu-id="c2e47-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="c2e47-142">Le opzioni valide per il `-MissedCallOption` parametro sono `Forward` `BusySignal`, o `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="c2e47-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="c2e47-143">Se si sceglie `Forward`, è necessario includere anche il `-MissedCallForwardTarget` parametro, con un utente o un numero di telefono come destinazione:</span><span class="sxs-lookup"><span data-stu-id="c2e47-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="c2e47-144">Rimuovere un delegato da un gruppo</span><span class="sxs-lookup"><span data-stu-id="c2e47-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="c2e47-145">Rimuovere un delegato da un gruppo utilizzando il cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c2e47-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="c2e47-146">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c2e47-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="c2e47-147">Eliminare un gruppo di SLA</span><span class="sxs-lookup"><span data-stu-id="c2e47-147">Delete an SLA group</span></span>

- <span data-ttu-id="c2e47-148">Eliminare un gruppo di SLA utilizzando il cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c2e47-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="c2e47-149">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c2e47-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


