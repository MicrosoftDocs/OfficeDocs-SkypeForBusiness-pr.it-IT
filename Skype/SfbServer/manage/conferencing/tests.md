---
title: Testare le conferenze telefoniche con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Riepilogo: informazioni su come testare le conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: be1cf5bba5a5bec2076f78880343582be19eda70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096732"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="40559-103">Testare le conferenze telefoniche con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40559-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="40559-104">**Riepilogo:** Informazioni su come testare le conferenze telefoniche con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40559-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="40559-105">Come verifica finale della configurazione delle conferenze telefoniche con accesso esterno, è possibile cercare dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di accesso e numeri di telefono per i quali non è specificata un'area di conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="40559-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="40559-106">È inoltre necessario verificare che la pagina Web Impostazioni conferenza telefonica con accesso esterno e i numeri di accesso esterno funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="40559-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="40559-107">Trovare dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da un numero di accesso</span><span class="sxs-lookup"><span data-stu-id="40559-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="40559-108">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="40559-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="40559-109">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="40559-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="40559-110">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="40559-110">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="40559-111">Questo cmdlet restituisce tutti i dial plan con un'area di conferenza telefonica con accesso esterno non utilizzata da alcun numero di accesso.</span><span class="sxs-lookup"><span data-stu-id="40559-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="40559-112">Per ulteriori informazioni, vedere [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="40559-112">For more information, see [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="40559-113">Trovare numeri di accesso senza aree assegnate</span><span class="sxs-lookup"><span data-stu-id="40559-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="40559-114">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="40559-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="40559-115">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="40559-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="40559-116">Eseguire il comando seguente al prompt:</span><span class="sxs-lookup"><span data-stu-id="40559-116">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="40559-117">Questo cmdlet restituisce tutti i numeri di accesso per conferenze telefoniche con accesso esterno non associati ad alcuna area.</span><span class="sxs-lookup"><span data-stu-id="40559-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="40559-118">Per ulteriori informazioni, vedere [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="40559-118">For more information, see [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="40559-119">Testare la pagina Web e i numeri di accesso</span><span class="sxs-lookup"><span data-stu-id="40559-119">Test webpage and access numbers</span></span>

<span data-ttu-id="40559-120">Per verificare che la pagina Web Impostazioni conferenza telefonica con accesso esterno e i numeri di accesso esterno funzionino correttamente, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40559-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="40559-121">Testare la pagina Web Impostazioni conferenza telefonica con accesso esterno eseguendo l'accesso all'URL semplice.</span><span class="sxs-lookup"><span data-stu-id="40559-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="40559-p102">Verificare che i numeri di accesso funzionino correttamente per un pool specifico eseguendo lo script riportato più avanti in questo argomento. Questo script simula le chiamate ai numeri di accesso. Per utilizzare lo script, sono necessari l'indirizzo SIP e le credenziali di un client per comunicazioni unificate ospitato nel pool specifico.</span><span class="sxs-lookup"><span data-stu-id="40559-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="40559-125">Per testare i numeri di accesso per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="40559-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="40559-126">Eseguire l'accesso al computer come membro del gruppo RTCUniversalServerAdmins oppure del ruolo Cs-ServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="40559-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="40559-127">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="40559-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="40559-128">Al prompt dei comandi eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="40559-128">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="40559-129">Nel rapporto risultante viene mostrato l'esito positivo o negativo, insieme a specifiche informazioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="40559-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="40559-130">Il flag -Verbose fornisce informazioni più dettagliate sul numero di numeri di accesso trovati e sui relativi dettagli.</span><span class="sxs-lookup"><span data-stu-id="40559-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="40559-131">Per ulteriori informazioni, vedere [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="40559-131">For more information, see [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
