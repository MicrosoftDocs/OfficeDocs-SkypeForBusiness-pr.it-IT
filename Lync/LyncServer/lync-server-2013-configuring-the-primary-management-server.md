---
title: 'Lync Server 2013: configurazione del server di gestione principale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b34c685ef59c6315b9d1a667f0715aa4300a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="52b2a-102">Configurazione del server di gestione principale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52b2a-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52b2a-103">_**Argomento Ultima modifica:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="52b2a-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="52b2a-104">Per sfruttare al meglio le nuove funzionalità di monitoraggio dell'integrità incluse negli amministratori di Microsoft Lync Server 2013, è necessario prima di tutto designare un computer per fungere da server di gestione principale. in tale computer è necessario installare System Center Operations Manager 2007 R2 o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="52b2a-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="52b2a-105">È inoltre necessario installare una versione supportata di SQL Server in modo che funzioni come database back-end di Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="52b2a-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="52b2a-106">Se si usa System Center Operations Manager 2012, è possibile usare una delle versioni seguenti di SQL Server come database back-end:</span><span class="sxs-lookup"><span data-stu-id="52b2a-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="52b2a-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="52b2a-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="52b2a-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="52b2a-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="52b2a-109">Se si usa System Center Operations Manager 2007 R2, è consigliabile installare SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="52b2a-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="52b2a-110">È anche possibile usare SQL Server 2008 R2 come database back-end per System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="52b2a-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="52b2a-111">Per altre informazioni sulla configurazione di SQL Server 2008 R2 per l'utilizzo di System Center Operations Manager 2007 R2, vedere l'appendice 1 della presente documentazione.</span><span class="sxs-lookup"><span data-stu-id="52b2a-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="52b2a-112">Quando si installa System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, è necessario installare tutti i componenti di tale prodotto, tra cui:</span><span class="sxs-lookup"><span data-stu-id="52b2a-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="52b2a-113">Database operativo</span><span class="sxs-lookup"><span data-stu-id="52b2a-113">Operational database</span></span>

  - <span data-ttu-id="52b2a-114">Server</span><span class="sxs-lookup"><span data-stu-id="52b2a-114">Server</span></span>

  - <span data-ttu-id="52b2a-115">Console</span><span class="sxs-lookup"><span data-stu-id="52b2a-115">Console</span></span>

  - <span data-ttu-id="52b2a-116">Cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="52b2a-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="52b2a-117">Console Web</span><span class="sxs-lookup"><span data-stu-id="52b2a-117">Web console</span></span>

  - <span data-ttu-id="52b2a-118">Reporting</span><span class="sxs-lookup"><span data-stu-id="52b2a-118">Reporting</span></span>

  - <span data-ttu-id="52b2a-119">Data warehouse</span><span class="sxs-lookup"><span data-stu-id="52b2a-119">Data warehouse</span></span>

<span data-ttu-id="52b2a-120">Questi componenti e la relativa installazione non verranno discussi in dettaglio in questo documento.</span><span class="sxs-lookup"><span data-stu-id="52b2a-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="52b2a-121">Per informazioni dettagliate su System Center Operations Manager 2007 R2, vedere la documentazione di Operations Manager 2007 <http://go.microsoft.com/fwlink/p/?linkid=257526> R2 all'indirizzo e la documentazione di System Center <http://go.microsoft.com/fwlink/p/?linkid=257527>Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="52b2a-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="52b2a-122">Seguire queste istruzioni se si intende usare SQL Server 2005 o SQL Server 2008 Service Pack 1 come database back-end.</span><span class="sxs-lookup"><span data-stu-id="52b2a-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="52b2a-123">Se si usa System Center Operations Manager 2012, è possibile usare SQL Server 2012 come database back-end.</span><span class="sxs-lookup"><span data-stu-id="52b2a-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="52b2a-124">Per informazioni dettagliate su SQL Server 2012, vedere la documentazione online per SQL Server [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)2012 at.</span><span class="sxs-lookup"><span data-stu-id="52b2a-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="52b2a-125">Tieni presente che puoi avere solo un singolo server di gestione principale per la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52b2a-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="52b2a-126">Anche se è possibile usare System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, non è possibile eseguire contemporaneamente le due applicazioni, ma è necessario sceglierne una o l'altra.</span><span class="sxs-lookup"><span data-stu-id="52b2a-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="52b2a-127">Ad esempio, se si esegue System Center Operations Manager 2012, è necessario che tutti gli agenti del centro di sistema eseguano anche System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="52b2a-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="52b2a-128">Non è possibile avere alcuni agenti che gestiscono System Center Operations Manager 2012 e altri agenti che utilizzano System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="52b2a-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

