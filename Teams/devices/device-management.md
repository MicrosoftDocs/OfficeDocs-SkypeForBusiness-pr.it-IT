---
title: Gestire i dispositivi in Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
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
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366a24706a80f6fe96cc8a3733022cc64f78ba7e
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281724"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="1033d-103">Gestire i dispositivi in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1033d-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="1033d-104">Come amministratore, puoi gestire i dispositivi usati con i team dell'organizzazione dall'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="1033d-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="1033d-105">È possibile visualizzare e gestire l'inventario dei dispositivi per l'organizzazione e svolgere attività come l'aggiornamento, il riavvio e il monitoraggio della diagnostica per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1033d-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="1033d-106">È anche possibile creare e assegnare profili di configurazione a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1033d-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="1033d-107">Quali dispositivi è possibile gestire?</span><span class="sxs-lookup"><span data-stu-id="1033d-107">What devices can you manage?</span></span>
<span data-ttu-id="1033d-108">È possibile gestire tutti i dispositivi certificati e registrati in teams.</span><span class="sxs-lookup"><span data-stu-id="1033d-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="1033d-109">Un dispositivo viene automaticamente registrato la prima volta che un utente accede a teams nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1033d-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="1033d-110">Per un elenco dei dispositivi certificati che è possibile gestire, vedere:</span><span class="sxs-lookup"><span data-stu-id="1033d-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="1033d-111">Telefoni per conferenze</span><span class="sxs-lookup"><span data-stu-id="1033d-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="1033d-112">Telefoni da tavolo</span><span class="sxs-lookup"><span data-stu-id="1033d-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="1033d-113">Barre di collaborazione</span><span class="sxs-lookup"><span data-stu-id="1033d-113">Collaboration bars</span></span>

<span data-ttu-id="1033d-114">I dispositivi vengono gestiti nell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com) in **dispositivi** nella barra di spostamento sinistra.</span><span class="sxs-lookup"><span data-stu-id="1033d-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="1033d-115">Se si dispone di Microsoft Intune, i dispositivi vengono registrati automaticamente in Intune.</span><span class="sxs-lookup"><span data-stu-id="1033d-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="1033d-116">Dopo che un dispositivo è stato registrato, la conformità del dispositivo viene confermata e i criteri di accesso condizionale vengono applicati al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1033d-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="1033d-117">Gestire i telefoni e le barre di collaborazione in teams</span><span class="sxs-lookup"><span data-stu-id="1033d-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="1033d-118">Anche se i telefoni e le barre di collaborazione sono gestiti nello stesso modo nell'interfaccia di amministrazione di Microsoft teams, hanno le rispettive sezioni nella barra di spostamento sinistra in **dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="1033d-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="1033d-119">In questo modo è possibile gestire separatamente ogni tipo di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1033d-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="1033d-120">Da qui è possibile visualizzare e gestire i telefoni e le barre di collaborazione iscritti ai team dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1033d-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="1033d-121">Le informazioni che verranno visualizzate per ogni dispositivo includono il nome del dispositivo, il produttore, il modello, l'utente, lo stato, l'azione, l'ultima volta e la cronologia.</span><span class="sxs-lookup"><span data-stu-id="1033d-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="1033d-122">È possibile personalizzare la visualizzazione per visualizzare le informazioni adatte alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="1033d-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="1033d-123">Ecco alcuni esempi di come è possibile gestire i dispositivi teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1033d-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="1033d-124">Per eseguire questa operazione...</span><span class="sxs-lookup"><span data-stu-id="1033d-124">To do this...</span></span>  |<span data-ttu-id="1033d-125">Operazione da eseguire</span><span class="sxs-lookup"><span data-stu-id="1033d-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="1033d-126">Modificare le informazioni sul dispositivo</span><span class="sxs-lookup"><span data-stu-id="1033d-126">Change device information</span></span>   | <span data-ttu-id="1033d-127">Selezionare un dispositivo > **modifica**.</span><span class="sxs-lookup"><span data-stu-id="1033d-127">Select a device > **Edit**.</span></span> <span data-ttu-id="1033d-128">È possibile modificare i dettagli, ad esempio il nome del dispositivo, il tag asset e aggiungere note.</span><span class="sxs-lookup"><span data-stu-id="1033d-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="1033d-129">Gestire gli aggiornamenti software</span><span class="sxs-lookup"><span data-stu-id="1033d-129">Manage software updates</span></span>   |<span data-ttu-id="1033d-130">Selezionare un dispositivo > **aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="1033d-130">Select a device > **Update**.</span></span> <span data-ttu-id="1033d-131">È possibile visualizzare l'elenco degli aggiornamenti software e firmware disponibili per il dispositivo e scegliere gli aggiornamenti da installare.</span><span class="sxs-lookup"><span data-stu-id="1033d-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="1033d-132">Riavviare un dispositivo</span><span class="sxs-lookup"><span data-stu-id="1033d-132">Restart a device</span></span>   |<span data-ttu-id="1033d-133">Selezionare un dispositivo > **riavviare**.</span><span class="sxs-lookup"><span data-stu-id="1033d-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="1033d-134">Visualizzare la cronologia dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="1033d-134">View device history</span></span>  | <span data-ttu-id="1033d-135">Selezionare un dispositivo > **cronologia**.</span><span class="sxs-lookup"><span data-stu-id="1033d-135">Select a device > **History**.</span></span> <span data-ttu-id="1033d-136">È possibile visualizzare la cronologia degli aggiornamenti per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1033d-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="1033d-137">Visualizzazione diagnostica</span><span class="sxs-lookup"><span data-stu-id="1033d-137">View diagnostics</span></span>  | <span data-ttu-id="1033d-138">Selezionare un dispositivo > **diagnostica**.</span><span class="sxs-lookup"><span data-stu-id="1033d-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="1033d-139">Usare i profili di configurazione in teams</span><span class="sxs-lookup"><span data-stu-id="1033d-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="1033d-140">Usare i profili di configurazione per gestire le impostazioni e le funzionalità per i dispositivi teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1033d-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="1033d-141">È possibile creare o caricare profili di configurazione per includere le impostazioni e le caratteristiche da abilitare o disabilitare e quindi assegnare un profilo a un dispositivo o a un gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1033d-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="1033d-142">Creare un profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="1033d-142">Create a configuration profile</span></span>

1. <span data-ttu-id="1033d-143">Nella barra di spostamento sinistra passa a **Devices**  >  **profili di configurazione**dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1033d-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="1033d-144">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1033d-144">Click **Add**.</span></span>
3. <span data-ttu-id="1033d-145">Immettere un nome per il profilo e, se si vuole, aggiungere una descrizione amichevole.</span><span class="sxs-lookup"><span data-stu-id="1033d-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="1033d-146">Specificare le impostazioni desiderate per il profilo e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1033d-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="1033d-147">Assegnare un profilo di configurazione</span><span class="sxs-lookup"><span data-stu-id="1033d-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="1033d-148">Nella barra di spostamento sinistra passa a **Devices**  >  **profili di configurazione**dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1033d-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="1033d-149">Selezionare il **profilo di configurazione** che si vuole assegnare e quindi fare clic su **assegna al dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="1033d-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="1033d-150">Nel riquadro **assegna dispositivi a un profilo di configurazione** cercare e selezionare i dispositivi che si desidera assegnare.</span><span class="sxs-lookup"><span data-stu-id="1033d-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="1033d-151">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1033d-151">Click **Save**.</span></span>
