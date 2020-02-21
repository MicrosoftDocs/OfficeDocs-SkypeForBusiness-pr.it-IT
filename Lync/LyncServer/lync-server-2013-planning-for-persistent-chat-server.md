---
title: 'Lync Server 2013: pianificazione del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Persistent Chat Server
ms:assetid: 57b2f574-234e-4a5a-bb78-8823369ba79e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398381(v=OCS.15)
ms:contentKeyID: 48184190
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ce92834cb866b0785523f4498663d7214e44c6a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="00a82-102">Pianificazione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a82-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00a82-103">_**Ultimo argomento modificato:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="00a82-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="00a82-104">È possibile utilizzare Lync Server 2013, il server Chat persistente per consentire a più utenti di partecipare a conversazioni in cui post e accesso al contenuto su argomenti specifici, inclusi testo, collegamenti e file.</span><span class="sxs-lookup"><span data-stu-id="00a82-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="00a82-105">Nonostante gli utenti possano comunicare in tempo reale durante una sessione, il contenuto di ogni sessione può essere salvato in modo permanente e quindi restare disponibile anche al termine di una sessione.</span><span class="sxs-lookup"><span data-stu-id="00a82-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="00a82-106">In questa sezione vengono descritte le considerazioni sulla pianificazione in una distribuzione di server Chat persistente di Lync Server 2013, inclusi i requisiti per la definizione, l'identificazione dei componenti e le topologie supportate e suggerimenti per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="00a82-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="00a82-107">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="00a82-107">In This Section</span></span>

  - [<span data-ttu-id="00a82-108">Panoramica del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a82-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="00a82-109">Funzionamento del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a82-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="00a82-110">Definizione dei requisiti dell'organizzazione per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a82-110">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="00a82-111">Componenti e topologie per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a82-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="00a82-112">Requisiti tecnici per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a82-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="00a82-113">Configurazione dei sistemi e dell'infrastruttura per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a82-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="00a82-114">Elenco di controllo di distribuzione per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00a82-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

