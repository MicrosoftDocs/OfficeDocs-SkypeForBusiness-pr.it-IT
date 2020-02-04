---
title: 'Lync Server 2013: Configurazione degli annunci per i numeri non assegnati'
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
ms.openlocfilehash: 52d7e8ad1aa4fcfe3db9aabee61e317810707194
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="3323d-102">Configurazione degli annunci per i numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3323d-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3323d-103">_**Argomento Ultima modifica:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="3323d-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="3323d-104">L'applicazione di annuncio è una caratteristica di VoIP aziendale che consente di configurare le chiamate alle estensioni non assegnate (estensioni valide per l'organizzazione, ma non assegnate a una persona o a un telefono).</span><span class="sxs-lookup"><span data-stu-id="3323d-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="3323d-105">Ad esempio, puoi configurare le chiamate a numeri non assegnati per riprodurre un messaggio o per essere trasferito a una destinazione diversa o entrambe.</span><span class="sxs-lookup"><span data-stu-id="3323d-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="3323d-106">L'applicazione annuncio viene installata come caratteristica dell'applicazione Response Group nel server front-end o Standard Edition quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3323d-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="3323d-107">È necessario configurare gli annunci caricando i file audio o configurando la sintesi vocale (TTS) e configurando la tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="3323d-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="3323d-108">Questa sezione illustra la configurazione degli annunci di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3323d-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="3323d-109">Si presuppone che siano già state lette le sezioni di pianificazione correlate agli annunci e che sia stato distribuito un server Enterprise Edition o un server Standard Edition con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="3323d-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3323d-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3323d-110">In This Section</span></span>

  - [<span data-ttu-id="3323d-111">Prerequisiti e ruoli per la configurazione degli annunci in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3323d-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="3323d-112">Processo di distribuzione per l'applicazione di annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3323d-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="3323d-113">Creare un annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3323d-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="3323d-114">Configurare la tabella dei numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3323d-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="3323d-115">Opzionale Verificare la distribuzione degli annunci in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3323d-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3323d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3323d-116">See Also</span></span>


[<span data-ttu-id="3323d-117">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3323d-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

