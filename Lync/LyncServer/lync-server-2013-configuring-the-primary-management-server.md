---
title: 'Lync Server 2013: configurazione del server di gestione principale'
description: 'Lync Server 2013: configurazione del server di gestione principale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43f986f4f03e96cafa27dfdd302bb98a00d8b2ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544162"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="b7937-103">Configurazione del server di gestione principale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7937-103">Configuring the primary management server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7937-104">_**Ultimo argomento modificato:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="b7937-104">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="b7937-105">Per sfruttare al meglio le nuove funzionalità di monitoraggio dell'integrità incluse negli amministratori di Microsoft Lync Server 2013, è necessario prima di tutto designare un computer che funga da server di gestione principale. in quel computer è necessario installare System Center Operations Manager 2007 R2 o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="b7937-105">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="b7937-106">Inoltre, è necessario installare una versione supportata di SQL Server per funzionare come database back-end di Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b7937-106">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="b7937-107">Se si utilizza System Center Operations Manager 2012, è possibile utilizzare una delle seguenti versioni di SQL Server come database back-end:</span><span class="sxs-lookup"><span data-stu-id="b7937-107">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="b7937-108">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="b7937-108">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="b7937-109">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="b7937-109">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="b7937-110">Se si utilizza System Center Operations Manager 2007 R2, è consigliabile installare SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3.</span><span class="sxs-lookup"><span data-stu-id="b7937-110">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="b7937-111">È inoltre possibile utilizzare SQL Server 2008 R2 come database back-end per System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b7937-111">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="b7937-112">Vedere l'appendice 1 di questa documentazione per ulteriori informazioni sulla configurazione di SQL Server 2008 R2 per l'utilizzo con System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b7937-112">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="b7937-113">Quando si installa System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, è necessario installare tutti i componenti del prodotto, tra cui:</span><span class="sxs-lookup"><span data-stu-id="b7937-113">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="b7937-114">Database operativo</span><span class="sxs-lookup"><span data-stu-id="b7937-114">Operational database</span></span>

  - <span data-ttu-id="b7937-115">Server</span><span class="sxs-lookup"><span data-stu-id="b7937-115">Server</span></span>

  - <span data-ttu-id="b7937-116">Console</span><span class="sxs-lookup"><span data-stu-id="b7937-116">Console</span></span>

  - <span data-ttu-id="b7937-117">Cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7937-117">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="b7937-118">Console Web</span><span class="sxs-lookup"><span data-stu-id="b7937-118">Web console</span></span>

  - <span data-ttu-id="b7937-119">Reporting</span><span class="sxs-lookup"><span data-stu-id="b7937-119">Reporting</span></span>

  - <span data-ttu-id="b7937-120">Data warehouse</span><span class="sxs-lookup"><span data-stu-id="b7937-120">Data warehouse</span></span>

<span data-ttu-id="b7937-121">Questi componenti e la relativa installazione non verranno esaminati in dettaglio in questo documento.</span><span class="sxs-lookup"><span data-stu-id="b7937-121">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="b7937-122">Per informazioni dettagliate su System Center Operations Manager 2007 R2, vedere la documentazione di Operations Manager 2007 R2 all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=257526> e la documentazione di System Center Operations manager 2012 all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=257527> .</span><span class="sxs-lookup"><span data-stu-id="b7937-122">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="b7937-123">Se si intende utilizzare SQL Server 2005 o SQL Server 2008 Service Pack 1 come database back-end, è consigliabile attenersi alle istruzioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b7937-123">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="b7937-124">Se si utilizza System Center Operations Manager 2012, è possibile utilizzare SQL Server 2012 come database back-end.</span><span class="sxs-lookup"><span data-stu-id="b7937-124">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="b7937-125">Per informazioni dettagliate su SQL Server 2012, vedere la documentazione online per SQL Server 2012 all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) .</span><span class="sxs-lookup"><span data-stu-id="b7937-125">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="b7937-126">Tenere presente che è possibile disporre di un solo server di gestione primario per la distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b7937-126">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="b7937-127">Inoltre, sebbene sia possibile utilizzare System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, non è possibile eseguire contemporaneamente le due applicazioni: è necessario sceglierne una o un'altra.</span><span class="sxs-lookup"><span data-stu-id="b7937-127">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="b7937-128">Ad esempio, se si esegue System Center Operations Manager 2012, tutti gli agenti del System Center devono anche eseguire System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="b7937-128">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="b7937-129">Non è possibile disporre di alcuni agenti che eseguono System Center Operations Manager 2012 e altri agenti che eseguono System Center Operations Manager 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b7937-129">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

