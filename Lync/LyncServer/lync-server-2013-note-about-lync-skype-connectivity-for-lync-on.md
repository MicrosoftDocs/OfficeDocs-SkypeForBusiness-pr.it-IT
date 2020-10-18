---
title: 'Lync Server 2013: Note sulla connettività Lync-Skype per Lync'
description: 'Lync Server 2013: Note sulla connettività Lync-Skype per Lync su.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f7d9758f277f2f987677c2c0ffa0a4447ba31d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579202"
---
# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="2c7e7-103">Note sulla connettività Lync-Skype in Lync Server 2013 per i clienti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="2c7e7-103">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c7e7-104">_**Ultimo argomento modificato:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="2c7e7-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="2c7e7-105">Questo documento è stato scritto per aiutare gli amministratori locali di Lync Server a configurare Lync-Skype connettività.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-105">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="2c7e7-106">Lync-Skype la connettività è anche una funzionalità di Lync Online, che fa parte di Office 365 e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-106">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365 and Microsoft 365.</span></span> <span data-ttu-id="2c7e7-107">È possibile abilitare la funzionalità di connettività Lync-Skype dall'interfaccia di amministrazione di Lync all'interno dell'interfaccia di amministratore.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-107">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the admin center.</span></span>

<span data-ttu-id="2c7e7-108">Per Microsoft 365 medie imprese, Office 365 Enterprise, Microsoft 365 Education e Office 365 for Government: accedere al portale di Office 365 o all'interfaccia di amministrazione di Microsoft 365 e passare all'interfaccia di **gestione di Lync**.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-108">For Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education, and Office 365 for Government: Sign in to the Office 365 portal or Microsoft 365 admin center and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="2c7e7-109">Passare a **comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-109">Go to **External Communications**.</span></span> <span data-ttu-id="2c7e7-110">In **provider di servizi di messaggistica istantanea**fare clic su **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-110">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="2c7e7-111">Se si desidera controllare l'accesso di singoli utenti alla connettività Lync-Skype, è possibile modificarne le impostazioni di comunicazione esterna per singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-111">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="2c7e7-112">Per Microsoft 365 Small Business Premium: accedere a Microsoft 365 e passare a impostazioni del **servizio di amministrazione per \> \> messaggistica istantanea, riunioni e conferenze**.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-112">For Microsoft 365 Small Business Premium: Sign in to Microsoft 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="2c7e7-113">Attiva comunicazioni esterne.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-113">Turn on External communications.</span></span> <span data-ttu-id="2c7e7-114">L'opzione comunicazioni esterne attiva sia la connettività Lync-Skype che le comunicazioni con altre organizzazioni che utilizzano Lync.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-114">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="2c7e7-115">A seconda del momento in cui è stato avviato l'utilizzo di Lync Online, l'opzione di comunicazione esterna in uno stato "on" può inizialmente indicare solo che le comunicazioni con altre organizzazioni Lync sono attivate.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-115">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="2c7e7-116">Per attivare la connettività Lync-Skype, è sufficiente alternare lo spegnimento e quindi di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2c7e7-116">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

