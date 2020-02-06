---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La migrazione dei numeri di accesso esterno a Skype for Business Server 2019 richiede l'esecuzione del cmdlet Move-CsApplicationEndpoint per eseguire la migrazione degli oggetti contatto. Durante l'installazione legacy e il periodo di coesistenza di Skype for Business Server 2019, i numeri di accesso esterno creati in Skype for Business Server 2019 si comportano in modo simile ai numeri di accesso per la chiamata in ingresso creati nell'installazione legacy, come descritto in questo sezione.
ms.openlocfilehash: 5333cc7cb835fc6bf324de9ab12a868f95b72972
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813504"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="c1cd0-104">Eseguire la migrazione dei numeri di accesso esterno</span><span class="sxs-lookup"><span data-stu-id="c1cd0-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="c1cd0-105">La migrazione dei numeri di accesso esterno a Skype for Business Server 2019 richiede l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="c1cd0-106">Durante l'installazione legacy e il periodo di coesistenza di Skype for Business Server 2019, i numeri di accesso esterno creati in Skype for Business Server 2019 si comportano in modo simile ai numeri di accesso per la chiamata in ingresso creati nell'installazione legacy, come descritto in questo sezione.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="c1cd0-107">I numeri di accesso esterno creati nell'installazione legacy, ma spostati in Skype for Business Server 2019 o creati in Skype for Business Server 2019 prima, durante o dopo la migrazione, hanno le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1cd0-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="c1cd0-108">Non vengono visualizzati negli inviti alle riunioni di Office Communications Server 2007 R2 e nella pagina numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c1cd0-109">Vengono visualizzati gli inviti alle riunioni di installazione legacy e la pagina numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c1cd0-110">Visualizzare gli inviti alle riunioni di Skype for Business Server 2019 e la pagina numero di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c1cd0-111">Non è possibile visualizzare o modificare lo strumento di amministrazione di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="c1cd0-112">Può essere visualizzato e modificato nel pannello di controllo installazione legacy e nell'installazione legacy di Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="c1cd0-113">Può essere visualizzato e modificato nel pannello di controllo di Skype for Business Server 2019 e in Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="c1cd0-114">Può essere risequenziata all'interno dell'area geografica usando il cmdlet Set-CsDialinConferencingAccessNumber con il parametro Priority.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="c1cd0-115">È necessario completare la migrazione dei numeri di accesso esterno che puntano al pool di installazione legacy prima di rimuovere la Commissione dal pool di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="c1cd0-116">Se non si completa la migrazione dei numeri di accesso per la chiamata in ingresso, come descritto nella procedura seguente, le chiamate in arrivo ai numeri di accesso avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1cd0-117">È necessario eseguire questa procedura prima della disattivazione del pool di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="c1cd0-118">È consigliabile trasferire i numeri di accesso esterno quando l'utilizzo della rete è basso, in caso di un breve periodo di interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="c1cd0-119">Per identificare e cambiare i numeri di accesso per la chiamata in ingresso</span><span class="sxs-lookup"><span data-stu-id="c1cd0-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="c1cd0-120">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c1cd0-121">Per trasferire ogni numero di accesso esterno a un pool ospitato in Skype for Business Server 2019, dalla riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="c1cd0-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="c1cd0-122">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="c1cd0-123">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="c1cd0-124">Fare clic sulla scheda **numero di accesso** esterno.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="c1cd0-125">Verificare che non rimangano numeri di accesso in ingresso per il pool di installazione legacy da cui si esegue la migrazione.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1cd0-126">Quando tutti i numeri di accesso esterno puntano al pool di Skype for Business Server 2019, è possibile rimuovere il pool di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c1cd0-127">Verificare la migrazione dei numeri di accesso esterno tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1cd0-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c1cd0-128">Da un account utente assegnato al ruolo **CsUserAdministrator** o **CsAdministrator** , accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="c1cd0-129">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="c1cd0-130">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="c1cd0-131">Fare clic sulla scheda **numero di accesso** esterno.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="c1cd0-132">Verificare che tutti i numeri di accesso per la chiamata in ingresso vengano migrati nel pool ospitati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c1cd0-133">Verificare la migrazione dei numeri di accesso esterno con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="c1cd0-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c1cd0-134">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="c1cd0-135">Per restituire tutti i numeri di accesso per le conferenze telefoniche con chiamata in ingresso migrati, dalla riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="c1cd0-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="c1cd0-136">Verificare che tutti i numeri di accesso per la chiamata in ingresso vengano migrati nel pool ospitati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c1cd0-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


