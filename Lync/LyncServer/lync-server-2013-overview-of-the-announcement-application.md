---
title: "Lync Server 2013: Panoramica dell'applicazione di annunci"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4c1b9210fcb0734b305a30d27c77b4e81257909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="c289b-102">Panoramica dell'applicazione di annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c289b-102">Overview of the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c289b-103">_**Argomento Ultima modifica:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="c289b-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="c289b-104">Quando si distribuisce l'applicazione di annuncio, è necessario configurare una tabella dei numeri non assegnati che determina l'azione da eseguire quando un utente compone un numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="c289b-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="c289b-105">La tabella numero non assegnati contiene gli intervalli di numeri di telefono validi per l'organizzazione e specifica l'applicazione di un annuncio che gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="c289b-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="c289b-106">Quando un chiamante compone un numero di telefono valido per l'organizzazione ma non viene assegnato a nessuno, Lync Server cerca il numero nella tabella di routing dei numeri non assegnati, identifica l'intervallo in cui il numero rientra e instrada la chiamata all'annuncio. applicazione specificata per tale intervallo.</span><span class="sxs-lookup"><span data-stu-id="c289b-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="c289b-107">L'applicazione di annuncio risponde alla chiamata e riproduce un messaggio audio (se è stato configurato per farlo) e quindi disconnette la chiamata o la trasferisce a una destinazione predeterminata, ad esempio a un operatore.</span><span class="sxs-lookup"><span data-stu-id="c289b-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="c289b-108">Puoi usare i cmdlet di Lync Server Management Shell per configurare più messaggi audio o per trasferire destinazioni.</span><span class="sxs-lookup"><span data-stu-id="c289b-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="c289b-109">La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa.</span><span class="sxs-lookup"><span data-stu-id="c289b-109">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="c289b-110">Se si hanno numeri specifici che non sono più in uso e si vogliono riprodurre i messaggi personalizzati per ogni numero, è possibile immettere i numeri specifici nella tabella dei numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="c289b-110">If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table.</span></span> <span data-ttu-id="c289b-111">Se ad esempio è stato modificato il numero per il servizio di assistenza clienti, è possibile immettere il vecchio numero di servizio clienti e associarlo a un annuncio che fornisce il nuovo numero.</span><span class="sxs-lookup"><span data-stu-id="c289b-111">For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number.</span></span> <span data-ttu-id="c289b-112">Se si vuole riprodurre un messaggio generale a chiunque chiami un numero non assegnato, ad esempio per i dipendenti che hanno lasciato l'organizzazione, è possibile immettere gli intervalli per tutte le estensioni valide dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c289b-112">If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization.</span></span> <span data-ttu-id="c289b-113">La tabella numeri non assegnati viene richiamata ogni volta che il chiamante compone un numero che non è attualmente assegnato.</span><span class="sxs-lookup"><span data-stu-id="c289b-113">The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="c289b-114">In Lync Server 2013 l'applicazione annuncio viene installata automaticamente con l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="c289b-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="c289b-115">Le applicazioni per l'annuncio e il gruppo di risposta sono componenti standard di una distribuzione di VoIP aziendale: quando si distribuisce VoIP aziendale, entrambe le applicazioni vengono distribuite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c289b-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

