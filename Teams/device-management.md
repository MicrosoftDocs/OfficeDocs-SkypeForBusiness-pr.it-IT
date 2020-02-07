---
title: Gestire i dispositivi in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: Informazioni su come gestire i dispositivi usati con i team dell'organizzazione.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2557410adf0eda18fab0e5450f739baf2ec7d581
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824870"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="f8f49-103">Gestire i dispositivi in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8f49-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="f8f49-104">Come amministratore, puoi gestire tutti i dispositivi usati con i team dell'organizzazione dall'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f8f49-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="f8f49-105">È possibile visualizzare e gestire l'inventario dei dispositivi per l'organizzazione e svolgere attività come l'aggiornamento, il riavvio e il monitoraggio della diagnostica per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f8f49-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="f8f49-106">È anche possibile creare e assegnare profili di configurazione a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f8f49-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="f8f49-107">Quali dispositivi è possibile gestire?</span><span class="sxs-lookup"><span data-stu-id="f8f49-107">What devices can you manage?</span></span>
<span data-ttu-id="f8f49-108">I dispositivi devono essere certificati per i team e registrati in teams.</span><span class="sxs-lookup"><span data-stu-id="f8f49-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="f8f49-109">Un dispositivo viene automaticamente registrato la prima volta che un utente accede a teams nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f8f49-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="f8f49-110">Per un elenco dei dispositivi certificati che è possibile gestire, vedere [telefoni per conferenze](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16) e [telefoni da tavolo](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34).</span><span class="sxs-lookup"><span data-stu-id="f8f49-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="f8f49-111">Se si dispone di Microsoft Intune, i dispositivi vengono registrati automaticamente in Intune.</span><span class="sxs-lookup"><span data-stu-id="f8f49-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="f8f49-112">Dopo che un dispositivo è stato registrato, la conformità del dispositivo viene confermata e i criteri di accesso condizionale vengono applicati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f8f49-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="f8f49-113">Gestire i dispositivi in teams</span><span class="sxs-lookup"><span data-stu-id="f8f49-113">Manage devices in Teams</span></span>

<span data-ttu-id="f8f49-114">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="f8f49-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f8f49-115">Nella barra di spostamento sinistra passa a **dispositivi** > per la**gestione dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="f8f49-116">Selezionare **tutti i dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="f8f49-117">Da qui è possibile visualizzare e gestire tutti i dispositivi registrati in teams dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8f49-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="f8f49-118">Le informazioni che verranno visualizzate per ogni dispositivo includono il nome del dispositivo, il produttore, il modello, l'utente, lo stato, l'azione, l'ultima volta e la cronologia.</span><span class="sxs-lookup"><span data-stu-id="f8f49-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="f8f49-119">È possibile personalizzare la visualizzazione per visualizzare le informazioni adatte alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="f8f49-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="f8f49-120">Ecco alcuni esempi di come è possibile gestire i dispositivi teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8f49-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="f8f49-121">Per eseguire questa operazione...</span><span class="sxs-lookup"><span data-stu-id="f8f49-121">To do this...</span></span>  |<span data-ttu-id="f8f49-122">Operazione da eseguire</span><span class="sxs-lookup"><span data-stu-id="f8f49-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="f8f49-123">Modificare le informazioni sul dispositivo</span><span class="sxs-lookup"><span data-stu-id="f8f49-123">Change device information</span></span>   | <span data-ttu-id="f8f49-124">Selezionare un dispositivo > **modifica**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-124">Select a device > **Edit**.</span></span> <span data-ttu-id="f8f49-125">È possibile modificare i dettagli, ad esempio nome dispositivo, informazioni utente, tag asset e Aggiungi note.</span><span class="sxs-lookup"><span data-stu-id="f8f49-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="f8f49-126">Gestire gli aggiornamenti software</span><span class="sxs-lookup"><span data-stu-id="f8f49-126">Manage software updates</span></span>   |<span data-ttu-id="f8f49-127">Selezionare un dispositivo > **aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-127">Select a device > **Update**.</span></span> <span data-ttu-id="f8f49-128">È possibile visualizzare l'elenco degli aggiornamenti software e firmware disponibili per il dispositivo e scegliere gli aggiornamenti da installare.</span><span class="sxs-lookup"><span data-stu-id="f8f49-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="f8f49-129">Riavviare un dispositivo</span><span class="sxs-lookup"><span data-stu-id="f8f49-129">Restart a device</span></span>   |<span data-ttu-id="f8f49-130">Selezionare un dispositivo > **riavviare**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="f8f49-131">Visualizzare la cronologia dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="f8f49-131">View device history</span></span>  | <span data-ttu-id="f8f49-132">Selezionare un dispositivo > **cronologia**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-132">Select a device > **History**.</span></span> <span data-ttu-id="f8f49-133">È possibile visualizzare la cronologia degli aggiornamenti per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f8f49-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="f8f49-134">Visualizzazione diagnostica</span><span class="sxs-lookup"><span data-stu-id="f8f49-134">View diagnostics</span></span>  | <span data-ttu-id="f8f49-135">Selezionare un dispositivo > **diagnostica**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="f8f49-136">Usare i profili di configurazione in teams</span><span class="sxs-lookup"><span data-stu-id="f8f49-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="f8f49-137">Usare i profili di configurazione per gestire le impostazioni e le funzionalità per i dispositivi teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8f49-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="f8f49-138">È possibile creare o caricare profili di configurazione per includere le impostazioni e le caratteristiche da abilitare o disabilitare e quindi assegnare un profilo a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f8f49-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="f8f49-139">Creare un profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="f8f49-139">Create a configuration profile</span></span>

::: zone target="docs"

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="f8f49-141">Uso dell'interfaccia di amministrazione di Microsoft teams & Skype for business</span><span class="sxs-lookup"><span data-stu-id="f8f49-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="f8f49-142">Nella barra di spostamento sinistra passa a **dispositivi** > per la**gestione dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="f8f49-143">Selezionare **profili di configurazione**e quindi selezionare **nuovo profilo di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="f8f49-144">Immettere un nome per il profilo e, se si vuole, aggiungere una descrizione amichevole.</span><span class="sxs-lookup"><span data-stu-id="f8f49-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="f8f49-145">Specificare le impostazioni desiderate per il profilo e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="f8f49-146">Assegnare un profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="f8f49-146">Assign a configuration profile</span></span>

::: zone target="docs"

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="f8f49-148">Uso dell'interfaccia di amministrazione di Microsoft teams & Skype for business</span><span class="sxs-lookup"><span data-stu-id="f8f49-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="f8f49-149">Nella barra di spostamento sinistra passa a **dispositivi** > per la**gestione dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="f8f49-150">Selezionare **profilo di configurazione**e quindi in **assegnata al** profilo che si vuole assegnare fare clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="f8f49-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="f8f49-151">Nel riquadro **assegna dispositivi a un profilo di configurazione** cercare e selezionare i dispositivi che si desidera assegnare.</span><span class="sxs-lookup"><span data-stu-id="f8f49-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="f8f49-152">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f8f49-152">Click **Save**.</span></span>
