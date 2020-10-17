---
title: Gestione del server chat persistente di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 306d12d35bc73935467a9b29812a614fac21f8e9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527553"
---
# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="3c169-102">Gestione del server chat persistente di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c169-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c169-103">_**Ultimo argomento modificato:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="3c169-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="3c169-104">È possibile utilizzare Lync Server 2013, il server Chat persistente per consentire a più utenti di partecipare a conversazioni in cui post e accesso al contenuto su argomenti specifici, inclusi testo, collegamenti e file.</span><span class="sxs-lookup"><span data-stu-id="3c169-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="3c169-105">Sebbene gli utenti possano comunicare in tempo reale durante una sessione, il contenuto di ogni sessione può essere salvato in modo permanente e quindi restare disponibile anche al termine di una sessione.</span><span class="sxs-lookup"><span data-stu-id="3c169-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="3c169-106">Il contenuto delle chat room permanenti è costituito principalmente da brevi messaggi di testo, anche se può includere messaggi più lunghi, riferiti a *storie*e anche collegamenti ipertestuali, emoticon e documenti caricati.</span><span class="sxs-lookup"><span data-stu-id="3c169-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c169-107">Il caricamento e il download dei file non sono supportati dal client Lync 2013. Tuttavia, è ancora supportato da Lync Server 2013, il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3c169-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="3c169-108">Il client di chat di gruppo legacy può inserire e visualizzare i file, ma se si accede alla stessa chat tramite il client Lync 2013, non sarà possibile accedere ai file.</span><span class="sxs-lookup"><span data-stu-id="3c169-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="3c169-109">L'accesso a una chat è controllato da un elenco di appartenenze.</span><span class="sxs-lookup"><span data-stu-id="3c169-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="3c169-110">L'intera cronologia della chat è disponibile per tutti i membri per un esame cronologico o una ricerca globale.</span><span class="sxs-lookup"><span data-stu-id="3c169-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="3c169-111">Per informazioni dettagliate sull'utilizzo del client di chat persistente, vedere [Planning for clients in Lync server 2013](lync-server-2013-planning-for-clients.md) nella documentazione relativa alla pianificazione e [distribuzione di client e dispositivi in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3c169-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3c169-112">Quando si configura il server Chat persistente per l'organizzazione, è necessario specificare la configurazione iniziale durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3c169-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="3c169-113">Tuttavia, è possibile che si verifichino momenti in cui si desidera modificare la modalità di implementazione del supporto del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3c169-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="3c169-114">Ad esempio, potrebbe essere necessario configurare il supporto e i controlli del server Chat persistente in modo diverso per un team o un gruppo specifico all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c169-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="3c169-115">In questa sezione vengono fornite informazioni e procedure che consentono di personalizzare la distribuzione del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3c169-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="3c169-116">Per informazioni dettagliate sulle caratteristiche e le funzionalità che è possibile configurare per il server Chat persistente, vedere [definizione dei requisiti dell'organizzazione per il server Chat persistente in Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) nella documentazione relativa alla pianificazione e [modalità di funzionamento del server Chat persistente in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3c169-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="3c169-117">Per informazioni dettagliate sulla distribuzione del server Chat persistente per Lync Server 2013, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3c169-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c169-118">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="3c169-118">In This Section</span></span>

  - [<span data-ttu-id="3c169-119">Funzionamento del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c169-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="3c169-120">Utilizzo di categorie per l'amministrazione del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="3c169-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="3c169-121">Informazioni sull'appartenenza di chat persistente</span><span class="sxs-lookup"><span data-stu-id="3c169-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="3c169-122">Procedure consigliate per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="3c169-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="3c169-123">Gestione di categorie, chat room e componenti aggiuntivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c169-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="3c169-124">Gestione dell'accesso degli utenti di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c169-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="3c169-125">Utilizzo e gestione del sistema di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c169-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

