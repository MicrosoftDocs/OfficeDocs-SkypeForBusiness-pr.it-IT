---
title: "Lync Server 2013: procedure consigliate per l'infrastruttura di base"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a4de1357786e2d5089fdc632002107a6c7cc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="17b50-102">Procedure consigliate per l'infrastruttura di base in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17b50-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17b50-103">_**Ultimo argomento modificato:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="17b50-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="17b50-104">È probabile che siano già state intraprese azioni per progettare la tolleranza di errore nel sistema, ad esempio garantendo la ridondanza hardware, prendendo precauzioni in caso di interruzioni dell'alimentazione, installando con regolarità gli aggiornamenti antivirus e della sicurezza e monitorando l'attività dei server.</span><span class="sxs-lookup"><span data-stu-id="17b50-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="17b50-105">Queste procedure traggono vantaggio non solo dell'infrastruttura di Microsoft Lync Server 2013, ma anche dell'intera rete.</span><span class="sxs-lookup"><span data-stu-id="17b50-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="17b50-106">Se non sono state implementate queste procedure, è consigliabile farlo prima di distribuire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17b50-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="17b50-107">Per proteggere i server della distribuzione di Lync Server 2013 da un danno accidentale o intenzionale che potrebbe causare tempi di inattività, prendere le seguenti precauzioni:</span><span class="sxs-lookup"><span data-stu-id="17b50-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="17b50-108">Installare con regolarità gli aggiornamenti della sicurezza nei server.</span><span class="sxs-lookup"><span data-stu-id="17b50-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="17b50-109">Sottoscrivendo il servizio Microsoft Security Notification Service, è possibile ricevere una notifica immediata ogni volta che vengono pubblicati bollettini sulla sicurezza per i prodotti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17b50-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="17b50-110">Per effettuare la sottoscrizione, visitare il sito Web Microsoft Technical Security [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202)Notifications all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="17b50-110">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="17b50-111">Verificare che i diritti di accesso siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="17b50-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="17b50-p103">Posizionare i server in un ambiente fisico con accesso consentito soltanto a personale autorizzato. Verificare che in tutti i server sia installato il software antivirus appropriato. Mantenere il software aggiornato con i file delle impronte digitali dei virus più recenti. Utilizzare la funzionalità di aggiornamento automatico dell'applicazione antivirus per mantenere costantemente aggiornate le impronte digitali dei virus.</span><span class="sxs-lookup"><span data-stu-id="17b50-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="17b50-116">Si consiglia di disabilitare i servizi del sistema operativo Windows Server che non sono necessari nei computer in cui si installa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="17b50-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="17b50-117">Crittografare i sistemi operativi e le unità disco in cui sono archiviati i dati con un sistema di crittografia dell'intero volume, a meno che non sia possibile garantire il controllo completo e costante dei server, l'isolamento fisico totale e la rimozione delle autorizzazioni appropriata e sicura per le unità disco sostituite o guaste.</span><span class="sxs-lookup"><span data-stu-id="17b50-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="17b50-118">Disabilitare tutte le porte DMA (Direct Memory Access) esterne del server, a meno che non sia possibile garantire un controllo rigoroso dell'accesso fisico ai server.</span><span class="sxs-lookup"><span data-stu-id="17b50-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="17b50-119">Gli attacchi basati su DMA, che possono essere eseguiti piuttosto facilmente, rendono vulnerabili le informazioni riservate, ad esempio le chiavi di crittografia private.</span><span class="sxs-lookup"><span data-stu-id="17b50-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

