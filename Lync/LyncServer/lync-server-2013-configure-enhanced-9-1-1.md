---
title: 'Lync Server 2013: Configurare i servizi di emergenza avanzati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="2ac89-102">Configurare i servizi di emergenza avanzati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac89-102">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ac89-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="2ac89-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="2ac89-104">Enhanced 9-1-1 (E9-1-1) è una funzionalità di notifica di emergenza che associa il numero di telefono della parte chiamante a un indirizzo civico o stradale.</span><span class="sxs-lookup"><span data-stu-id="2ac89-104">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address.</span></span> <span data-ttu-id="2ac89-105">Usando queste informazioni, il PSAP (Public Safety Answering Point) può immediatamente inviare i servizi di emergenza al chiamante in difficoltà.</span><span class="sxs-lookup"><span data-stu-id="2ac89-105">Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="2ac89-106">Per supportare E9-1-1, Lync Server 2013 deve essere in grado di associare correttamente una posizione a un client e verificare che queste informazioni vengano usate per instradare la chiamata di emergenza al PSAP più vicino.</span><span class="sxs-lookup"><span data-stu-id="2ac89-106">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="2ac89-107">Per informazioni dettagliate sulla pianificazione di una distribuzione di E9-1-1, vedere [pianificazione per i servizi di emergenza (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="2ac89-107">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2ac89-108">Lync Server 2013 supporta solo E9-1-1 negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="2ac89-108">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="2ac89-109">Per distribuire E9-1-1, è necessario configurare una connessione SIP a un provider di servizi E9-1-1 qualificato oppure distribuire un gateway ELIN (Emergency Location Identification Number) a un provider di servizi E9-1-1 Basato su PSTN (Public Switched Telephone).</span><span class="sxs-lookup"><span data-stu-id="2ac89-109">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="2ac89-110">Per informazioni dettagliate, vedere <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) e Mediation Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2ac89-110">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="2ac89-111">Per informazioni dettagliate sulla configurazione delle connessioni trunk, vedere <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">configurare un trunk con il bypass multimediale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2ac89-111">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2ac89-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2ac89-112">In This Section</span></span>

  - [<span data-ttu-id="2ac89-113">Configurare una route vocale E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac89-113">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="2ac89-114">Creare criteri di posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac89-114">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="2ac89-115">Configurare le informazioni sul sito per E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac89-115">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="2ac89-116">Configurare il database della posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac89-116">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="2ac89-117">Configurare le funzionalità di E9-1-1 avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac89-117">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

