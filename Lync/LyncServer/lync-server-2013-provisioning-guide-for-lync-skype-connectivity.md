---
title: 'Lync Server 2013: Guida al provisioning della connettività Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f94da566e4322f9b8d1d039441c561f5ed60f6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="41d48-102">Guida al provisioning della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41d48-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d48-103">_**Argomento Ultima modifica:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="41d48-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="41d48-p101">Lync Server 2013 supporta la connettività con Skype, grazie alla quale gli utenti di Lync 2013 possono aggiungere contatti Skype usando l'account Microsoft (MSA) dell'utente Skype. È anche possibile aggiungere utenti Lync all'elenco contatti dei client Skype. In base ai criteri impostati a livello amministrativo in Lync Server, gli utenti Lync e Skype saranno in grado di comunicare tramite messaggistica istantanea, verificare la rispettiva presenza e avviare chiamate audio e video. La connettività Lync-Skype è anche una funzionalità di Lync Online e può essere abilitata per gli utenti di Lync Online tramite l'interfaccia di amministrazione di Lync nel portale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="41d48-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="41d48-p102">Se Lync Server è già configurato per la connessione con Windows Messenger tramite connettività per messaggistica istantanea pubblica (PIC, Public Instant Messaging Connectivity), la distribuzione è già configurata per la connettività Lync-Skype. L'unica modifica che potrebbe essere necessaria è la ridenominazione della voce PIC di Messenger esistente in Skype. Per dettagli, vedere Configurare l'impostazione per Lync del provider PIC di Skype, più avanti in questa guida.</span><span class="sxs-lookup"><span data-stu-id="41d48-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="41d48-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="41d48-112">In This Section</span></span>

  - [<span data-ttu-id="41d48-113">Nota sulla connettività di Lync-Skype in Lync Server 2013 per i clienti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="41d48-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="41d48-114">Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41d48-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="41d48-115">Abilitazione della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41d48-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="41d48-116">Uso della connettività Lync-Skype in Lync Server 2013 come utente finale</span><span class="sxs-lookup"><span data-stu-id="41d48-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="41d48-117">Domande frequenti: provisioning della connettività Lync Server 2013 per Skype</span><span class="sxs-lookup"><span data-stu-id="41d48-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

