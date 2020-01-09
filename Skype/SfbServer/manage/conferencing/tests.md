---
title: Testare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Riepilogo: informazioni su come testare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: a19adba9d36fd7f862b9b40d3c7c239933fa7847
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992273"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="622aa-103">Testare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="622aa-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="622aa-104">**Riepilogo:** Informazioni su come testare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="622aa-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="622aa-105">Come verifica finale della configurazione dei servizi di conferenza telefonica con accesso esterno, è possibile cercare piani di chiamata con un'area dei servizi di conferenza telefonica con accesso esterno non utilizzata da qualsiasi numero di Access e per i numeri di Access che non hanno specificato un'area di conferenza telefonica con chiamata in ingresso.</span><span class="sxs-lookup"><span data-stu-id="622aa-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="622aa-106">È inoltre necessario verificare che la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno e i numeri delle connessioni in ingresso funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="622aa-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="622aa-107">Trovare i piani di chiamata con un'area di conferenza telefonica con accesso esterno che non viene usata da un numero di Access</span><span class="sxs-lookup"><span data-stu-id="622aa-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="622aa-108">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="622aa-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="622aa-109">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="622aa-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="622aa-110">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="622aa-110">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="622aa-111">Questo cmdlet restituisce tutti i dial plan che hanno un'area di conferenza telefonica con accesso esterno che non viene usata da un numero di Access.</span><span class="sxs-lookup"><span data-stu-id="622aa-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="622aa-112">Per altre informazioni, vedere [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="622aa-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="622aa-113">Trovare i numeri di accesso senza aree assegnate</span><span class="sxs-lookup"><span data-stu-id="622aa-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="622aa-114">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="622aa-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="622aa-115">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="622aa-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="622aa-116">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="622aa-116">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="622aa-117">Questo cmdlet restituisce tutti i numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso che non sono associati a un'area geografica.</span><span class="sxs-lookup"><span data-stu-id="622aa-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="622aa-118">Per altre informazioni, vedere [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="622aa-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="622aa-119">Testare i numeri di pagina Web e di accesso</span><span class="sxs-lookup"><span data-stu-id="622aa-119">Test webpage and access numbers</span></span>

<span data-ttu-id="622aa-120">Per verificare che la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno e i numeri per le connessioni in ingresso funzionino correttamente, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="622aa-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="622aa-121">Testare la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno accedendo all'URL semplice.</span><span class="sxs-lookup"><span data-stu-id="622aa-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="622aa-122">Verificare che i numeri di accesso funzionino correttamente per un pool specifico eseguendo lo script più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="622aa-122">Test that access numbers work correctly for a specific pool by running the script later in this topic.</span></span> <span data-ttu-id="622aa-123">Questo script simula le chiamate ai numeri di accesso.</span><span class="sxs-lookup"><span data-stu-id="622aa-123">This script simulates calls to access numbers.</span></span> <span data-ttu-id="622aa-124">È necessario l'indirizzo SIP e le credenziali di un client Unified Communications (UC) ospitato nel pool specifico per l'uso di questo script.</span><span class="sxs-lookup"><span data-stu-id="622aa-124">You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="622aa-125">Per testare i numeri di accesso per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="622aa-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="622aa-126">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="622aa-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="622aa-127">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="622aa-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="622aa-128">Eseguire la procedura seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="622aa-128">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="622aa-129">Il report risultante Mostra l'esito positivo o negativo, insieme a specifiche informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="622aa-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="622aa-130">Il contrassegno-Verbose fornisce informazioni più dettagliate sul numero di numeri di accesso trovati e sui relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="622aa-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="622aa-131">Per altre informazioni, vedere [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="622aa-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

