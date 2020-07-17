---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La migrazione dei numeri di accesso esterno a Skype for Business Server 2019 richiede l'esecuzione del cmdlet Move-CsApplicationEndpoint per eseguire la migrazione degli oggetti contatto. Durante l'installazione legacy e il periodo di coesistenza di Skype for Business Server 2019, i numeri di accesso esterno creati in Skype for Business Server 2019 si comportano in modo analogo ai numeri di accesso esterno creati nell'installazione legacy, come descritto in questa sezione.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752698"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="9066c-104">Eseguire la migrazione dei numeri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="9066c-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="9066c-105">La migrazione dei numeri di accesso esterno a Skype for Business Server 2019 richiede l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="9066c-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="9066c-106">Durante l'installazione legacy e il periodo di coesistenza di Skype for Business Server 2019, i numeri di accesso esterno creati in Skype for Business Server 2019 si comportano in modo analogo ai numeri di accesso esterno creati nell'installazione legacy, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="9066c-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="9066c-107">I numeri di accesso esterno creati nell'installazione legacy ma trasferiti in Skype for Business Server 2019 o creati in Skype for Business Server 2019 prima, durante o dopo la migrazione, hanno le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="9066c-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="9066c-108">Non sono visualizzati negli inviti alle riunioni di Office Communications Server 2007 R2 e nella pagina del numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="9066c-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="9066c-109">Sono visualizzati negli inviti alle riunioni di installazione legacy e nella pagina del numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="9066c-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="9066c-110">Sono visualizzati negli inviti alle riunioni di Skype for Business Server 2019 e nella pagina del numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="9066c-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="9066c-111">Possono essere visualizzati e modificati nello strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9066c-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="9066c-112">Possono essere visualizzati e modificati nel pannello di controllo installazione legacy e nel Legacy install Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9066c-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="9066c-113">Possono essere visualizzati e modificati nel pannello di controllo di Skype for Business Server 2019 e in Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9066c-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="9066c-114">Possono essere risequenziati nell'area tramite il cmdlet Set-CsDialinConferencingAccessNumber con il parametro Priority.</span><span class="sxs-lookup"><span data-stu-id="9066c-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="9066c-115">Prima di rimuovere il pool di installazione legacy, è necessario terminare la migrazione dei numeri di accesso esterno che puntano al pool di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="9066c-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="9066c-116">Se non si completa la migrazione come descritto nella procedura seguente, le chiamate in arrivo ai numeri di accesso avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="9066c-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9066c-117">È necessario eseguire questa procedura prima di rimuovere il pool di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="9066c-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="9066c-118">È consigliabile spostare i numeri di accesso esterno quando l'utilizzo della rete è ridotto, nel caso si verifichi una breve interruzione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="9066c-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="9066c-119">Per identificare e spostare i numeri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="9066c-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="9066c-120">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9066c-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="9066c-121">Per spostare ogni numero di accesso esterno in un pool ospitato in Skype for Business Server 2019, dalla riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="9066c-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="9066c-122">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9066c-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="9066c-123">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="9066c-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="9066c-124">Fare clic sulla scheda **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="9066c-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="9066c-125">Verificare che non rimangano numeri di accesso esterno per il pool di installazione legacy da cui si esegue la migrazione.</span><span class="sxs-lookup"><span data-stu-id="9066c-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9066c-126">Quando tutti i numeri di accesso esterno puntano al pool di Skype for Business Server 2019, è possibile rimuovere il pool di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="9066c-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9066c-127">Verificare la migrazione dei numeri di accesso esterno tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9066c-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9066c-128">Da un account utente assegnato al ruolo **CsUserAdministrator** o al ruolo **CsAdministrator** accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9066c-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="9066c-129">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9066c-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="9066c-130">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="9066c-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="9066c-131">Fare clic sulla scheda **Numero di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="9066c-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="9066c-132">Verificare che tutti i numeri di accesso esterno vengano migrati nel pool ospitato su Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9066c-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9066c-133">Verificare la migrazione dei numeri di accesso esterno tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9066c-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="9066c-134">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9066c-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="9066c-135">Per ottenere un elenco di tutti i numeri di accesso a conferenze telefoniche con accesso esterno di cui è stata eseguita la migrazione, dalla riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="9066c-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="9066c-136">Verificare che tutti i numeri di accesso esterno vengano migrati nel pool ospitato su Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9066c-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


