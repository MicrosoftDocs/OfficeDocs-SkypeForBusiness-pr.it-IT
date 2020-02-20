---
title: 'Lync Server 2013: requisiti di Lync per Android'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc9b7eb673e4c5593a622fca3c37cafde2c22110
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="16371-102">Requisiti di Lync per Android in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16371-102">Lync for Android requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16371-103">_**Ultimo argomento modificato:** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="16371-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="16371-104">Microsoft Lync 2013 Microsoft Lync 2013 per Android fornisce funzionalità di messaggistica istantanea, presenza avanzata e capacità di partecipazione alle riunioni di Lync per gli utenti dell'organizzazione che si connettono da un dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="16371-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="16371-105">In questo argomento vengono descritte le considerazioni relative a Lync 2013 per Android, inclusi i prerequisiti, i requisiti tecnici e i componenti necessari.</span><span class="sxs-lookup"><span data-stu-id="16371-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="16371-106">Prerequisito per Lync per Android</span><span class="sxs-lookup"><span data-stu-id="16371-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="16371-107">Per supportare Lync 2013 per Android, il dispositivo Android deve soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="16371-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="16371-108">Il dispositivo Android deve eseguire Android 4,0 o un sistema operativo successivo o basato su tavolette, incluse le tavolette, ad eccezione di quelle con il chip Tegra2.</span><span class="sxs-lookup"><span data-stu-id="16371-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="16371-109">Il dispositivo deve avere una CPU dual core 1,2 GHz o superiore.</span><span class="sxs-lookup"><span data-stu-id="16371-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="16371-110">La risoluzione della fotocamera del dispositivo (anteriore/posteriore) deve essere VGA o superiore.</span><span class="sxs-lookup"><span data-stu-id="16371-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="16371-111">Altri requisiti hardware devono essere allineati al documento di definizione della compatibilità con Android 4,0.</span><span class="sxs-lookup"><span data-stu-id="16371-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="16371-112">Altre considerazioni di carattere tecnico</span><span class="sxs-lookup"><span data-stu-id="16371-112">Other Technical Considerations</span></span>

<span data-ttu-id="16371-113">Nella piattaforma del dispositivo Android, l'applicazione Lync può essere eseguita in background.</span><span class="sxs-lookup"><span data-stu-id="16371-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="16371-114">Pertanto, a differenza di altre piattaforme per dispositivi mobili, le notifiche push non sono necessarie per i dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="16371-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="16371-115">L'unico modo per uscire dall'applicazione Lync su un dispositivo Android è di disconnettersi in modo esplicito da Lync.</span><span class="sxs-lookup"><span data-stu-id="16371-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="16371-116">Questa versione dell'applicazione Lync non è supportata nei dispositivi con chipset Tegra 2.</span><span class="sxs-lookup"><span data-stu-id="16371-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

