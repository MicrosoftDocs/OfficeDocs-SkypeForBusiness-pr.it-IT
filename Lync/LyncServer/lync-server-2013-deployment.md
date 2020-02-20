---
title: 'Lync Server 2013: distribuzione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ac492e29cfb349d6cce4d3ff211d879414c2e6f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="6fca1-102">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fca1-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6fca1-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6fca1-104">La distribuzione del software di comunicazione di Lync Server 2013 include la preparazione di servizi di dominio Active Directory, la distribuzione di front end server e altri componenti interni di Lync Server 2013 di base e la distribuzione di eventuali ruoli e funzionalità del server aggiuntivi che l'organizzazione potrebbe richiedere, ad esempio l'accesso utente esterno e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="6fca1-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="6fca1-105">In questa documentazione vengono descritti tre scenari per la distribuzione di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6fca1-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="6fca1-106">Nuova distribuzione di Lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="6fca1-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="6fca1-107">Nuova distribuzione di Lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6fca1-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="6fca1-108">Nuova distribuzione di Lync Server 2013 Standard Edition o Enterprise Edition in una distribuzione di Lync Server 2010 Standard Edition o Enterprise Edition esistente</span><span class="sxs-lookup"><span data-stu-id="6fca1-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="6fca1-109">Per informazioni sulla distribuzione di Lync Server 2013 in un ambiente Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2 esistente, vedere la documentazione relativa alla [migrazione](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="6fca1-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6fca1-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="6fca1-110">In This Section</span></span>

  - [<span data-ttu-id="6fca1-111">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="6fca1-112">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="6fca1-113">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="6fca1-114">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="6fca1-115">Distribuzione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="6fca1-116">Configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="6fca1-117">Pianificazione e distribuzione di video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="6fca1-118">Distribuzione di siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="6fca1-119">Distribuzione del server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="6fca1-120">Distribuzione di client e dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="6fca1-121">Pianificazione e distribuzione dell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="6fca1-122">Gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="6fca1-123">Aggiornamento dalla versione di valutazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="6fca1-124">Distribuzione del controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="6fca1-125">Distribuzione di dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="6fca1-126">Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="6fca1-127">Configurazione dell'integrità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fca1-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

