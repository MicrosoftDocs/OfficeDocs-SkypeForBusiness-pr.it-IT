---
title: Informazioni su ITAdmin per Microsoft Teams per il client RealWear (anteprima)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: A, procedura dettagliata per ITAdmin di Microsoft Teams per il client RealWear.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67f595e6b037eb6091d3b4e03e3258a13e12a4d1
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909390"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="c3065-103">Microsoft Teams per RealWear</span><span class="sxs-lookup"><span data-stu-id="c3065-103">Microsoft Teams for RealWear</span></span>

<span data-ttu-id="c3065-104">Questo articolo riguarda il client Microsoft Teams per dispositivi indossabili sulla testa RealWear.</span><span class="sxs-lookup"><span data-stu-id="c3065-104">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="c3065-105">Gli operatori sul campo che utilizzano RealWear HMT-1 e HMT-1Z1 ora possono collaborare con un esperto in remoto tramite videochiamata su Teams.</span><span class="sxs-lookup"><span data-stu-id="c3065-105">Frontline Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="c3065-106">Tramite un'interfaccia utente a comando vocale, Teams per RealWear consente agli operatori sul campo di lavorare completamente a mani libere mantenendo la consapevolezza della situazione in ambienti rumorosi e pericolosi.</span><span class="sxs-lookup"><span data-stu-id="c3065-106">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="c3065-107">Mostrando ciò che vedono in tempo reale, i lavoratori sul campo possono accelerare i tempi di risoluzione dei problemi e ridurre il rischio di costosi tempi di inattività.</span><span class="sxs-lookup"><span data-stu-id="c3065-107">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="c3065-108">Come distribuire Microsoft Teams per RealWear</span><span class="sxs-lookup"><span data-stu-id="c3065-108">How to deploy Microsoft Teams for RealWear</span></span>

- <span data-ttu-id="c3065-109">Dispositivi RealWear aggiornati alla versione 11.2 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c3065-109">RealWear devices updated to release 11.2 or above.</span></span> <span data-ttu-id="c3065-110">Per altre informazioni, fare clic [qui](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="c3065-110">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>
- <span data-ttu-id="c3065-111">Accesso a [RealWear Foresight](https://cloud.realwear.com/) per distribuire il client Microsoft Teams per Realwear.</span><span class="sxs-lookup"><span data-stu-id="c3065-111">Access to [RealWear Foresight](https://cloud.realwear.com/) for distributing the Microsoft Teams client for Realwear.</span></span>

## <a name="required-licenses"></a><span data-ttu-id="c3065-112">Licenze necessarie</span><span class="sxs-lookup"><span data-stu-id="c3065-112">Required Licenses</span></span>

<span data-ttu-id="c3065-113">Le licenze di Microsoft Teams fanno parte degli abbonamenti a Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="c3065-113">Microsoft Teams licenses are part of Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="c3065-114">Non sono richieste ulteriori licenze per utilizzare Teams per RealWear.</span><span class="sxs-lookup"><span data-stu-id="c3065-114">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="c3065-115">Per altre informazioni su come ottenere Teams, vedere [Come si accede a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span><span class="sxs-lookup"><span data-stu-id="c3065-115">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="c3065-116">Gestione dei dispositivi RealWear</span><span class="sxs-lookup"><span data-stu-id="c3065-116">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="c3065-117">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="c3065-117">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="c3065-118">I dispositivi RealWear possono essere gestiti utilizzando la modalità Amministratore di dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="c3065-118">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="c3065-119">Il supporto per la gestione tramite Android Enterprise è limitato, poiché attualmente i dispositivi non dispongono di Google Mobile Services (GMS).</span><span class="sxs-lookup"><span data-stu-id="c3065-119">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="c3065-120">Per altre informazioni sulla gestione dei dispositivi RealWear su Microsoft Endpoint Manager, vedere [Registrazione di tipo amministratore di dispositivi Android](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="c3065-120">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="c3065-121">Per altre informazioni sui criteri, vedere [Come usare Intune in ambienti che non dispongono di Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span><span class="sxs-lookup"><span data-stu-id="c3065-121">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="c3065-122">Enterprise Mobility Manager (EMMs) di terze parti</span><span class="sxs-lookup"><span data-stu-id="c3065-122">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="c3065-123">Per informazioni sugli EMM di terze parti, vedere [Provider di Enterprise Mobility Management supportati](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="c3065-123">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="c3065-124">Contenuto per l'utente finale</span><span class="sxs-lookup"><span data-stu-id="c3065-124">End-user content</span></span>

<span data-ttu-id="c3065-125">Per altre informazioni a riguardo dal punto di vista di un utente finale, vedere [Uso di Microsoft Teams per RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span><span class="sxs-lookup"><span data-stu-id="c3065-125">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
