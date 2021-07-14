---
title: Distribuire Teams telefoni e Teams display usando Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Questo articolo fornisce una panoramica delle funzionalità supportate Microsoft Teams display.
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420821"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="16c27-103">Distribuire Teams telefoni e Teams display usando Intune</span><span class="sxs-lookup"><span data-stu-id="16c27-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="16c27-104">Questo articolo offre una panoramica su come eseguire la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="16c27-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="16c27-105">Teams telefoni e Teams tramite Intune.</span><span class="sxs-lookup"><span data-stu-id="16c27-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="16c27-106">Accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="16c27-106">Conditional Access</span></span>

<span data-ttu-id="16c27-107">L'accesso condizionale è una Azure Active Directory (Azure AD) che consente di verificare che i dispositivi che accedono alle risorse Office 365 siano gestiti correttamente e sicuri.</span><span class="sxs-lookup"><span data-stu-id="16c27-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="16c27-108">Se si applicano criteri di accesso condizionale al servizio Teams, i dispositivi Android (inclusi i telefoni Teams e gli schermi Teams) che accedono Teams devono essere registrati in Intune e le relative impostazioni devono essere conformi ai criteri.</span><span class="sxs-lookup"><span data-stu-id="16c27-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="16c27-109">Se il dispositivo non è registrato in Intune o se è registrato ma le relative impostazioni non sono conformi ai criteri, l'accesso condizionale impedirà a un utente di accedere o usare l'app Teams nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="16c27-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="16c27-110">In genere, i criteri di conformità definiti in Intune vengono assegnati a gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="16c27-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="16c27-111">Questo significa che se si assegnano criteri di conformità Android a user@contoso.com, questi criteri verranno applicati allo stesso modo al proprio smartphone Android e a qualsiasi dispositivo Teams basato su Android a cui user@contoso.com accedere.</span><span class="sxs-lookup"><span data-stu-id="16c27-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="16c27-112">Se si usa l'accesso condizionale, che richiede l'applicazione della registrazione di Intune, nell'organizzazione è necessario configurare un paio di elementi per consentire la corretta registrazione di Intune:</span><span class="sxs-lookup"><span data-stu-id="16c27-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="16c27-113">**Licenza di Intune** L'utente che accede al Teams deve avere una licenza per Intune.</span><span class="sxs-lookup"><span data-stu-id="16c27-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="16c27-114">Finché il dispositivo Teams è connesso a un account utente con una licenza intune valida, il dispositivo verrà registrato automaticamente in Microsoft Intune come parte del processo di accesso.</span><span class="sxs-lookup"><span data-stu-id="16c27-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="16c27-115">**Configurare Intune** È necessario avere configurato correttamente un tenant di Intune per la registrazione dell'amministratore di dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="16c27-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="16c27-116">Configurare Intune per la registrazione Teams dispositivi basati su Android</span><span class="sxs-lookup"><span data-stu-id="16c27-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="16c27-117">Teams I dispositivi basati su Android sono gestiti da Intune tramite la gestione di Android Device Administrator (DA).</span><span class="sxs-lookup"><span data-stu-id="16c27-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="16c27-118">Prima che i dispositivi possano essere registrati in Intune, è necessario eseguire alcuni passaggi di base.</span><span class="sxs-lookup"><span data-stu-id="16c27-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="16c27-119">Se si stanno già gestendo i dispositivi con Intune oggi, è probabile che siano già state eseguite tutte queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="16c27-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="16c27-120">In caso contrario, ecco cosa fare:</span><span class="sxs-lookup"><span data-stu-id="16c27-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="16c27-121">Se gli amministratori del tenant vogliono che i telefoni di area comune siano registrati in Intune, devono aggiungere una licenza di Intune all'account e seguire i passaggi per la registrazione di Intune.</span><span class="sxs-lookup"><span data-stu-id="16c27-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="16c27-122">Se l'account utente usato per accedere a un dispositivo Teams non è concesso in licenza per Intune, i criteri di conformità di Intune e le restrizioni di registrazione devono essere disabilitati per l'account.</span><span class="sxs-lookup"><span data-stu-id="16c27-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="16c27-123">Impostare Intune MDM (gestione di dispositivi mobili) Authority.</span><span class="sxs-lookup"><span data-stu-id="16c27-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="16c27-124">Se intune non è mai stato usato in precedenza, è necessario impostare l'autorità MDM prima di poter registrare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="16c27-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="16c27-125">Per altre informazioni, vedere [Impostare l'autorità di gestione dei dispositivi mobili.](/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="16c27-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="16c27-126">Si tratta di un passaggio di una sola volta che deve essere eseguito quando si crea un nuovo tenant di Intune.</span><span class="sxs-lookup"><span data-stu-id="16c27-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="16c27-127">Abilitare la registrazione dell'amministratore di dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="16c27-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="16c27-128">I dispositivi Teams basati su Android vengono gestiti come dispositivi di amministratore di dispositivi con Intune.</span><span class="sxs-lookup"><span data-stu-id="16c27-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="16c27-129">La registrazione dell'amministratore del dispositivo è disattivata per impostazione predefinita per i tenant appena creati.</span><span class="sxs-lookup"><span data-stu-id="16c27-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="16c27-130">Vedere [Registrazione dell'amministratore di dispositivi Android](/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="16c27-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="16c27-131">Assegnare licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="16c27-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="16c27-132">Agli utenti Teams dispositivi di registrazione a Intune deve essere assegnata una licenza intune valida.</span><span class="sxs-lookup"><span data-stu-id="16c27-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="16c27-133">Per altre informazioni, vedere Assegnare licenze agli utenti in modo [che possano registrare i dispositivi in Intune.](/intune/fundamentals/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="16c27-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="16c27-134">Assegnare i criteri di conformità dell'amministratore di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="16c27-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="16c27-135">a.</span><span class="sxs-lookup"><span data-stu-id="16c27-135">a.</span></span> <span data-ttu-id="16c27-136">Creare criteri di conformità per l'amministratore di dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="16c27-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="16c27-137">b.</span><span class="sxs-lookup"><span data-stu-id="16c27-137">b.</span></span> <span data-ttu-id="16c27-138">Assegnarlo al gruppo Azure Active Directory che contiene gli utenti che accederanno ai Teams dispositivi.</span><span class="sxs-lookup"><span data-stu-id="16c27-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="16c27-139">Vedere [Usare i criteri di conformità per impostare regole per i dispositivi gestiti con Intune.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="16c27-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="16c27-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16c27-140">See also</span></span>

[<span data-ttu-id="16c27-141">Telefoni per Teams</span><span class="sxs-lookup"><span data-stu-id="16c27-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="16c27-142">Telefoni IP certificati per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16c27-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="16c27-143">Teams di testo</span><span class="sxs-lookup"><span data-stu-id="16c27-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="16c27-144">Gestire i dispositivi in Teams</span><span class="sxs-lookup"><span data-stu-id="16c27-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="16c27-145">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="16c27-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)