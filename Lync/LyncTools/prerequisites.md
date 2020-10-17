---
title: Prerequisiti
description: Prerequisiti.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 936e52961539ed57fe1b610d42fb1c9cf35589b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560102"
---
# <a name="prerequisites"></a><span data-ttu-id="b063e-103">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b063e-103">Prerequisites</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b063e-104">_**Ultimo argomento modificato:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="b063e-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="b063e-105">Sono disponibili diversi requisiti di configurazione hardware, software e di sistema che è necessario eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b063e-105">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="b063e-106">Requisiti hardware client</span><span class="sxs-lookup"><span data-stu-id="b063e-106">Client Hardware Requirements</span></span>

<span data-ttu-id="b063e-107">Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 nella distribuzione di Lync Server 2013, per tutti gli utenti di 4.500 di cui si desidera simulare il carico, è necessario almeno un computer dedicato che soddisfi i requisiti hardware minimi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b063e-107">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="b063e-108">1 scheda di rete Gigabit</span><span class="sxs-lookup"><span data-stu-id="b063e-108">1 gigabit network adapter</span></span>

  - <span data-ttu-id="b063e-109">RAM da 8 GB</span><span class="sxs-lookup"><span data-stu-id="b063e-109">8-GB ram</span></span>

  - <span data-ttu-id="b063e-110">2 unità di elaborazione centrale Dual Core (CPU)</span><span class="sxs-lookup"><span data-stu-id="b063e-110">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="b063e-111">Requisiti software client</span><span class="sxs-lookup"><span data-stu-id="b063e-111">Client Software Requirements</span></span>

<span data-ttu-id="b063e-112">Per eseguire lo strumento di gestione dello stress e delle prestazioni di Lync Server 2013 nella distribuzione di Lync Server 2013, i sistemi operativi supportati sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="b063e-112">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="b063e-113">Sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b063e-113">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="b063e-114">Sistema operativo Windows Server 2008 (versione 64 bit)</span><span class="sxs-lookup"><span data-stu-id="b063e-114">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="b063e-115">Il computer client deve soddisfare i requisiti software seguenti:</span><span class="sxs-lookup"><span data-stu-id="b063e-115">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="b063e-116">È necessario che sia installato [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) Runtime.</span><span class="sxs-lookup"><span data-stu-id="b063e-116">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="b063e-117">In Windows Server 2008/Windows Server 2012, è necessario abilitare la funzionalità Desktop Experience.</span><span class="sxs-lookup"><span data-stu-id="b063e-117">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="b063e-118">È necessario che [Microsoft Visual C++ 2012 Redistributable Package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) sia installato.</span><span class="sxs-lookup"><span data-stu-id="b063e-118">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="b063e-119">Distribuzione di Lync Server 2013 completamente configurata.</span><span class="sxs-lookup"><span data-stu-id="b063e-119">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b063e-120">Le raccolte di Microsoft Unified Communications Managed API (UCMA) 4,0 sono incluse nel pacchetto di installazione, pertanto UCMA non è necessario e non deve essere installato nei computer client.</span><span class="sxs-lookup"><span data-stu-id="b063e-120">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="b063e-121">Requisiti di configurazione</span><span class="sxs-lookup"><span data-stu-id="b063e-121">Configuration Requirements</span></span>

<span data-ttu-id="b063e-122">I computer in cui verrà eseguito lo strumento di stress e prestazioni di Lync Server 2013 devono essere configurati in base ai requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b063e-122">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="b063e-123">È necessario essere connessi come membri del gruppo Domain o local Admins.</span><span class="sxs-lookup"><span data-stu-id="b063e-123">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="b063e-124">Lync Server 2013 stress and Performance Tool (LyncPerfTool.exe) non può essere eseguito in un computer che esegue anche i componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b063e-124">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="b063e-125">È necessario eseguire lo strumento di creazione degli utenti di Lync Server 2013 (UserProvisioningTool.exe) nel front end server o nel server Standard Edition in cui si trovano gli account utente.</span><span class="sxs-lookup"><span data-stu-id="b063e-125">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="b063e-126">Quando lo strumento viene eseguito più volte, tutti gli utenti abilitati per le comunicazioni unificate di Microsoft devono disporre di un numero di telefono univoco.</span><span class="sxs-lookup"><span data-stu-id="b063e-126">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="b063e-127">Le dimensioni del file di paging devono essere gestite dal sistema o devono essere almeno 1,5 volte la quantità di RAM del sistema.</span><span class="sxs-lookup"><span data-stu-id="b063e-127">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

