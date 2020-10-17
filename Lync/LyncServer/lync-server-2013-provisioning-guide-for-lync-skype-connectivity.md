---
title: 'Lync Server 2013: Guida al provisioning per la connettività Lync-Skype'
description: 'Lync Server 2013: Guida al provisioning per la connettività Lync-Skype.'
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
ms.openlocfilehash: 9859a7a621ba4329fe0436fe50a0d9de1d0ae1ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569092"
---
# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="4aa92-103">Guida al provisioning per la connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa92-103">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aa92-104">_**Ultimo argomento modificato:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="4aa92-104">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="4aa92-105">Lync Server 2013 supporta la connettività con Skype.</span><span class="sxs-lookup"><span data-stu-id="4aa92-105">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="4aa92-106">Questa connettività consente agli utenti di Lync 2013 di aggiungere contatti Skype utilizzando l'account Microsoft dell'utente Skype (MSA).</span><span class="sxs-lookup"><span data-stu-id="4aa92-106">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="4aa92-107">I client Skype possono inoltre aggiungere utenti di Lync all'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="4aa92-107">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="4aa92-108">In base ai criteri configurati amministrativamente in Lync Server, gli utenti di Lync e Skype saranno in grado di comunicare utilizzando la messaggistica istantanea, vedere reciprocamente la presenza e avviare chiamate audio e video.</span><span class="sxs-lookup"><span data-stu-id="4aa92-108">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="4aa92-109">Lync-Skype la connettività è anche una funzionalità di Lync Online e può essere abilitata per i clienti di Lync Online dall'interfaccia di amministrazione di Lync all'interno dell'interfaccia utente di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4aa92-109">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="4aa92-110">Se Lync Server è già configurato per la connessione con Windows Messenger tramite la connettività per la messaggistica istantanea pubblica, la distribuzione è già configurata per la connettività Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="4aa92-110">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="4aa92-111">L'unica modifica che è possibile prendere in considerazione è quella di rinominare la voce del PIC Messenger esistente come Skype.</span><span class="sxs-lookup"><span data-stu-id="4aa92-111">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="4aa92-112">Per ulteriori informazioni, vedere Configure the Skype PIC provider setting for Lync più avanti in questa guida.</span><span class="sxs-lookup"><span data-stu-id="4aa92-112">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4aa92-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="4aa92-113">In This Section</span></span>

  - [<span data-ttu-id="4aa92-114">Note sulla connettività Lync-Skype in Lync Server 2013 per i clienti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="4aa92-114">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="4aa92-115">Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa92-115">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="4aa92-116">Abilitazione della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa92-116">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="4aa92-117">Utilizzo della connettività Lync-Skype in Lync Server 2013 come utente finale</span><span class="sxs-lookup"><span data-stu-id="4aa92-117">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="4aa92-118">Domande frequenti: provisioning di Lync Server 2013 per la connettività Skype</span><span class="sxs-lookup"><span data-stu-id="4aa92-118">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

