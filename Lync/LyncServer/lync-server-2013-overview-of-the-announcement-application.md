---
title: "Lync Server 2013: Panoramica dell'applicazione annuncio"
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
ms.openlocfilehash: d0bceaef7a165f4594d825a80b93ee167b68c85a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520813"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="7bbde-102">Panoramica dell'applicazione annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bbde-102">Overview of the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bbde-103">_**Ultimo argomento modificato:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="7bbde-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="7bbde-104">Quando si distribuisce l'applicazione annuncio, è necessario configurare una tabella dei numeri non assegnati che determina l'azione da eseguire quando un utente compone un numero non assegnato.</span><span class="sxs-lookup"><span data-stu-id="7bbde-104">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="7bbde-105">La tabella numeri non assegnati contiene gli intervalli di numeri di telefono validi per l'organizzazione e specifica quale applicazione di annuncio gestisce ogni intervallo.</span><span class="sxs-lookup"><span data-stu-id="7bbde-105">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="7bbde-106">Quando un chiamante compone un numero di telefono valido per l'organizzazione ma non è assegnato a nessuno, Lync Server cerca il numero nella tabella di routing dei numeri non assegnati, identifica l'intervallo in cui si trova il numero e instrada la chiamata all'applicazione annuncio specificata per tale intervallo.</span><span class="sxs-lookup"><span data-stu-id="7bbde-106">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="7bbde-107">L'applicazione Annuncio risponde alla chiamata e riproduce un messaggio audio (se è stata configurata per farlo) e quindi disconnette la chiamata o la trasferisce in una destinazione predeterminata, ad esempio a un operatore.</span><span class="sxs-lookup"><span data-stu-id="7bbde-107">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="7bbde-108">È possibile utilizzare i cmdlet di Lync Server Management Shell per configurare più messaggi audio o per trasferire le destinazioni.</span><span class="sxs-lookup"><span data-stu-id="7bbde-108">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="7bbde-p102">Il modo in cui configurare la tabella dei numeri non assegnati dipende da come si desidera usarla. Se si dispone di numeri specifici non più in uso e si desidera riprodurre messaggi personalizzati per ogni numero, è possibile immettere tali numeri specifici nella tabella dei numeri non assegnati. Se, ad esempio, è stato modificato il numero del Service Desk clienti, è possibile immettere il vecchio numero del servizio clienti e associarlo a un annuncio che fornisce il nuovo numero. Se si desidera riprodurre un messaggio generale a chiunque chiami un numero non assegnato, ad esempio per dipendenti che non lavorano più nell'organizzazione, è possibile immettere intervalli per tutti gli interni validi dell'organizzazione. La tabella dei numeri non assegnati viene richiamata ogni volta che il chiamante compone un numero attualmente non assegnato.</span><span class="sxs-lookup"><span data-stu-id="7bbde-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="7bbde-114">In Lync Server 2013, l'applicazione annuncio viene automaticamente installata con l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="7bbde-114">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="7bbde-115">Le applicazioni annuncio e Response Group sono componenti standard di una distribuzione di VoIP aziendale: quando si distribuisce VoIP aziendale, entrambe le applicazioni vengono distribuite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7bbde-115">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

