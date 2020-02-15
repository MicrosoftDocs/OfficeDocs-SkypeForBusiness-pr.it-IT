---
title: 'Lync Server 2013: distribuzione del plug-in VDI di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6802be2d2191c057e35ac25618d74c1e338899a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="f5177-102">Distribuzione del plug-in VDI di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5177-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5177-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f5177-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f5177-104">Il client Lync 2013 supporta l'audio e il video in un ambiente VDI (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="f5177-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="f5177-105">Un utente può connettere un dispositivo audio o video (ad esempio un auricolare o una videocamera) al computer locale (ad esempio un thin client o un computer ricondizionato).</span><span class="sxs-lookup"><span data-stu-id="f5177-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="f5177-106">L'utente può connettersi alla macchina virtuale, accedere al client Lync 2013 in esecuzione nella macchina virtuale e partecipare a comunicazioni audio e video in tempo reale come se il client è in esecuzione localmente.</span><span class="sxs-lookup"><span data-stu-id="f5177-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="f5177-107">Il plug-in VDI di Lync è un'applicazione autonoma che viene installata nel computer locale e consente l'utilizzo di dispositivi audio e video locali con il client Lync 2013 in esecuzione nella macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="f5177-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="f5177-108">Per il plug-in non è necessario che Lync sia installato nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="f5177-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="f5177-109">Dopo che l'utente ha eseguito l'accesso al client Lync 2013 in esecuzione nella macchina virtuale, Lync richiede all'utente di immettere di nuovo le proprie credenziali per stabilire una connessione con il plug-in VDI di Lync in esecuzione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="f5177-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="f5177-110">Una volta effettuata questa connessione, l'utente può effettuare e ricevere chiamate audio e video.</span><span class="sxs-lookup"><span data-stu-id="f5177-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5177-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f5177-111">In This Section</span></span>

  - [<span data-ttu-id="f5177-112">Prerequisiti del plug-in VDI di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5177-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="f5177-113">Preparazione dell'ambiente Lync Server 2013 per VDI</span><span class="sxs-lookup"><span data-stu-id="f5177-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="f5177-114">Accesso e utilizzo di Lync 2013 nella macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="f5177-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="f5177-115">Risoluzione dei problemi relativi al plug-in VDI di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5177-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="f5177-116">Tecnologie di virtualizzazione supportate e limitazioni note in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5177-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

