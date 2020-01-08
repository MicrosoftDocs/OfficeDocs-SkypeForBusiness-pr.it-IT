---
title: 'Lync Server 2013: server Edge audio/video (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9738dbb11ce731ac832a5529d2013f3f9b2907
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="12019-102">Audio/video (A/V) Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12019-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12019-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12019-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12019-104">Il servizio A/V Edge consente agli utenti interni (utenti che hanno effettuato l'accesso alla rete organizzativa) di condividere audio e video con utenti esterni (utenti che non hanno eseguito l'accesso alla rete organizzativa).</span><span class="sxs-lookup"><span data-stu-id="12019-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="12019-105">Oltre all'audio e al video, l'A/V Edge service offre anche il supporto per la condivisione desktop e il trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="12019-105">In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="12019-106">Il servizio A/V Edge viene gestito principalmente tramite la configurazione A/V Edge; Queste impostazioni consentono di gestire la quantità massima di larghezza di banda da allocare per ogni porta e per utente e di specificare il periodo di tempo in cui può essere usato un token di autenticazione prima che il token debba essere rinnovato.</span><span class="sxs-lookup"><span data-stu-id="12019-106">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed.</span></span> <span data-ttu-id="12019-107">Le impostazioni di configurazione di Edge a/V possono essere applicate ai siti o ai singoli server a/V Edge.</span><span class="sxs-lookup"><span data-stu-id="12019-107">A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers.</span></span> <span data-ttu-id="12019-108">Per determinare quale raccolta di impostazioni avrà la priorità, usare la guida seguente:</span><span class="sxs-lookup"><span data-stu-id="12019-108">When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="12019-109">Le impostazioni configurate nell'ambito del servizio, ovvero su un singolo server, hanno la priorità su tutto.</span><span class="sxs-lookup"><span data-stu-id="12019-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="12019-110">Le impostazioni configurate nell'ambito del sito hanno la priorità sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="12019-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="12019-111">Tuttavia, le impostazioni dell'ambito del servizio sostituiranno anche le impostazioni dell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="12019-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="12019-112">Le impostazioni dell'ambito globale verranno usate solo se non sono state configurate impostazioni di servizio nel singolo server e se non sono presenti impostazioni del sito per il sito in cui si trova il server.</span><span class="sxs-lookup"><span data-stu-id="12019-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="12019-113">Il servizio A/V Edge può essere gestito solo tramite Lync Server PowerShell e i cmdlet CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="12019-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12019-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="12019-114">In This Section</span></span>

  - [<span data-ttu-id="12019-115">Restituire le informazioni di configurazione A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12019-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="12019-116">Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12019-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="12019-117">Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12019-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

