---
title: 'App pazienti per amministratori Teams '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: App pazienti per amministratori Teams
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749558"
---
# <a name="patients-app-overview"></a><span data-ttu-id="264e3-103">Panoramica delle app pazienti</span><span class="sxs-lookup"><span data-stu-id="264e3-103">Patients app overview</span></span>

<span data-ttu-id="264e3-104">L'applicazione patients è un'app Store di Microsoft teams disponibile per tutti gli utenti di teams.</span><span class="sxs-lookup"><span data-stu-id="264e3-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="264e3-105">L'app consente ai team di assistenza paziente costituiti da operatori clinici (ad esempio infermieri, medici, assistenti sociali) di curare e rivedere elenchi di pazienti per scenari che spaziano da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="264e3-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="264e3-106">L'app ha due modalità:</span><span class="sxs-lookup"><span data-stu-id="264e3-106">The app has two modes:</span></span> 

- <span data-ttu-id="264e3-107">La modalità connessa EMR che si connette a EMR tramite FHIR.</span><span class="sxs-lookup"><span data-stu-id="264e3-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="264e3-108">L'app modalità connessa EMR rimane in anteprima privata e i clienti interessati o gli amministratori possono richiedere l'accesso all'app eliminando Microsoft un messaggio di posta elettronica su teamsforhealthcare@service.microsoft.com con le informazioni sul tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="264e3-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="264e3-109">La modalità manuale che consente ai team di assistenza di aggiungere/apportare manualmente le informazioni sul paziente.</span><span class="sxs-lookup"><span data-stu-id="264e3-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="264e3-110">L'applicazione è disponibile nell'app teams Store per gli utenti finali da scaricare per impostazione predefinita ed è in anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="264e3-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="264e3-111">L'app può essere limitata a determinate sezioni di utenti che usano [criteri di configurazione delle app in Microsoft teams](../../teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="264e3-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="264e3-112">Esempio di utilizzo</span><span class="sxs-lookup"><span data-stu-id="264e3-112">Usage example</span></span>

<span data-ttu-id="264e3-113">Durante le sessioni di arrotondamento su ogni turno in reparto medico, i clinici si radunano presso la stazione di cura per discutere gli ultimi aggiornamenti sullo stato di avanzamento dei pazienti nel reparto.</span><span class="sxs-lookup"><span data-stu-id="264e3-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="264e3-114">Evidenziano le metriche chiave critiche (non necessariamente mediche o che esplicitano sulle cartelle cliniche dei pazienti) e assicurano che il paziente sia sul percorso di scorrimento a destra per il discarico in base alla diagnosi.</span><span class="sxs-lookup"><span data-stu-id="264e3-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="264e3-115">Per aggirare questi pazienti, l'infermiera di carica configura l'app paziente in un team in cui vengono aggiunti tutti i clinici e aggiunge i pazienti a un elenco di pazienti.</span><span class="sxs-lookup"><span data-stu-id="264e3-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="264e3-116">Durante i turni, gli infermieri e gli altri responsabili della cura per il paziente accedono a Microsoft teams e l'app patients sui loro dispositivi mobili e aggiornano le informazioni pertinenti sul paziente nel dispositivo e quindi tutti gli altri membri del team di assistenza possono vedere gli aggiornamenti e le note e rimanere sincronizzati. Due volte al giorno, all'inizio e alla fine di un turno, hanno anche riunioni di Team displicinary per passare all'elenco dei pazienti e usare l'app pazienti per mettere a terra se stessi e condividere informazioni su ogni paziente usando l'app pazienti in uno schermo di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="264e3-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="264e3-117">Spesso, alcuni clinici possono anche accedere a queste riunioni di team in remoto ed essere ancora parte della discussione.</span><span class="sxs-lookup"><span data-stu-id="264e3-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="264e3-118">Configurare l'app pazienti</span><span class="sxs-lookup"><span data-stu-id="264e3-118">Configure Patients app</span></span>

<span data-ttu-id="264e3-119">Per informazioni su come preparare l'ambiente per l'uso dell'app pazienti in modalità EMR, vedere [integrazione di record sanitari elettronici in Microsoft teams](patients-app.md).</span><span class="sxs-lookup"><span data-stu-id="264e3-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="264e3-120">Dovrai anche vedere gestire i [criteri di configurazione delle app in Microsoft teams](../../teams-app-setup-policies.md) per abilitare l'app patients per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="264e3-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a><span data-ttu-id="264e3-121">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="264e3-121">Related topics</span></span>

[<span data-ttu-id="264e3-122">Integrare cartelle cliniche elettroniche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="264e3-122">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
