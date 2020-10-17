---
title: 'Lync Server 2013: configurazione degli annunci per i numeri non assegnati'
description: 'Lync Server 2013: configurazione degli annunci per i numeri non assegnati.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16ab636f0c6157118a00d5e46521555086c5e520
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570032"
---
# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="c8319-103">Configurazione degli annunci per i numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8319-103">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8319-104">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="c8319-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="c8319-105">L'applicazione annuncio è una funzionalità VoIP aziendale che consente di configurare le chiamate alle estensioni non assegnate (estensioni valide per la propria organizzazione, ma non vengono assegnate a una persona o a un telefono).</span><span class="sxs-lookup"><span data-stu-id="c8319-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="c8319-106">È ad esempio possibile configurare le chiamate a numeri non assegnati in modo che venga riprodotto un messaggio, in modo che vengano trasferite a un'altra destinazione oppure in modo che vengano eseguite entrambe queste azioni.</span><span class="sxs-lookup"><span data-stu-id="c8319-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="c8319-107">L'applicazione annuncio viene installata come caratteristica dell'applicazione Response Group nel server front end server o Standard Edition quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c8319-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c8319-108">È necessario configurare gli annunci caricando i file audio oppure configurando la sintesi vocale e la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="c8319-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="c8319-109">In questa sezione viene illustrata la configurazione degli annunci di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8319-109">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="c8319-110">Si presuppone che siano già state lette le sezioni di pianificazione relative agli annunci e che sia stato distribuito un server Enterprise Edition o un server Standard Edition con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c8319-110">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c8319-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="c8319-111">In This Section</span></span>

  - [<span data-ttu-id="c8319-112">Prerequisiti e ruoli per la configurazione degli annunci in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8319-112">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="c8319-113">Processo di distribuzione per l'applicazione annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8319-113">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="c8319-114">Creare un annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8319-114">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="c8319-115">Configurare la tabella dei numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8319-115">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="c8319-116">Optional Verificare la distribuzione degli annunci in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8319-116">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8319-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8319-117">See Also</span></span>


[<span data-ttu-id="c8319-118">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8319-118">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

