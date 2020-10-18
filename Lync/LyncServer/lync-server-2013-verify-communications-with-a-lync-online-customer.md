---
title: 'Lync Server 2013: verificare le comunicazioni con un cliente di Lync Online'
description: 'Lync Server 2013: verificare le comunicazioni con un cliente di Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 867b0f7ffffd563c869b9bcd5443a3cb91b156af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579442"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="39b75-103">Verificare le comunicazioni con un cliente di Lync online in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b75-103">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b75-104">_**Ultimo argomento modificato:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="39b75-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="39b75-105">Per consentire agli utenti di Lync nell'organizzazione di comunicare con gli utenti di un cliente di Microsoft Lync Online 2010, è necessario aver completato i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="39b75-105">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="39b75-106">Sono stati soddisfatti tutti i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="39b75-106">Met all prerequisites.</span></span> <span data-ttu-id="39b75-107">Ciò include la distribuzione dei server interni e perimetrali, l'abilitazione del supporto federativo per l'organizzazione e la configurazione degli account utente.</span><span class="sxs-lookup"><span data-stu-id="39b75-107">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="39b75-108">Per ulteriori informazioni, vedere [prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="39b75-108">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="39b75-109">Il supporto per l'accesso al dominio è stato configurato nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="39b75-109">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="39b75-110">Ciò include la creazione di una voce del provider host e la configurazione della distribuzione per consentire l'accesso dal dominio del cliente di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="39b75-110">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="39b75-111">Per ulteriori informazioni, vedere [Configure Federation support for a Lync Online Domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="39b75-111">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="39b75-112">Gli account utente sono stati configurati per il supporto della federazione.</span><span class="sxs-lookup"><span data-stu-id="39b75-112">Configured your user accounts to support federation.</span></span> <span data-ttu-id="39b75-113">Per ulteriori informazioni, vedere [configurare l'accesso utente per la Federazione con un cliente di Lync online in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="39b75-113">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="39b75-114">Dopo aver completato tutti questi passaggi e l'amministratore del cliente Lync Online 2010 ha completato tutta la configurazione dei servizi online per supportare la Federazione con l'organizzazione, verificare le comunicazioni verificando le comunicazioni tra un utente interno dell'organizzazione e un utente del cliente Lync Online.</span><span class="sxs-lookup"><span data-stu-id="39b75-114">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="39b75-115">Se la comunicazione non ha esito positivo, utilizzare lo strumento di registrazione dal server perimetrale per acquisire i file di log e di traccia per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="39b75-115">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="39b75-116">Per informazioni dettagliate sull'utilizzo dello strumento di registrazione, vedere [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="39b75-116">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="39b75-117">Per informazioni dettagliate sullo strumento di registrazione, vedere la documentazione dello strumento di registrazione di Lync Server 2010 nella libreria TechNet all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .</span><span class="sxs-lookup"><span data-stu-id="39b75-117">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

