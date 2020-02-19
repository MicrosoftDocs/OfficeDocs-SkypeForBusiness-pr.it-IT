---
title: 'Lync Server 2013: Guida per il provisioning della connettività Lync-Skype'
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
ms.openlocfilehash: 8684fb619c73145baa627c07bab64be9478232ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="fa5dd-102">Guida al provisioning della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa5dd-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa5dd-103">_**Ultimo argomento modificato:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="fa5dd-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="fa5dd-104">Lync Server 2013 supporta la connettività con Skype.</span><span class="sxs-lookup"><span data-stu-id="fa5dd-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="fa5dd-105">Questa connettività consente agli utenti di Lync 2013 di aggiungere contatti Skype utilizzando l'account Microsoft dell'utente Skype (MSA).</span><span class="sxs-lookup"><span data-stu-id="fa5dd-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="fa5dd-106">I client Skype possono inoltre aggiungere utenti di Lync all'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="fa5dd-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="fa5dd-107">In base ai criteri configurati amministrativamente in Lync Server, gli utenti di Lync e Skype saranno in grado di comunicare utilizzando la messaggistica istantanea, vedere reciprocamente la presenza e avviare chiamate audio e video.</span><span class="sxs-lookup"><span data-stu-id="fa5dd-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="fa5dd-108">La connettività Lync-Skype è anche una funzionalità di Lync Online e può essere abilitata per i clienti di Lync Online dall'interfaccia di amministrazione di Lync all'interno del portale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="fa5dd-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="fa5dd-109">Se Lync Server è già configurato per la connessione con Windows Messenger tramite la connettività di messaggistica istantanea pubblica (PIC), la distribuzione è già configurata per la connettività Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="fa5dd-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="fa5dd-110">L'unica modifica che è possibile prendere in considerazione è quella di rinominare la voce del PIC Messenger esistente come Skype.</span><span class="sxs-lookup"><span data-stu-id="fa5dd-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="fa5dd-111">Per ulteriori informazioni, vedere Configure the Skype PIC provider setting for Lync più avanti in questa guida.</span><span class="sxs-lookup"><span data-stu-id="fa5dd-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fa5dd-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="fa5dd-112">In This Section</span></span>

  - [<span data-ttu-id="fa5dd-113">Note sulla connettività Lync-Skype in Lync Server 2013 per i clienti di Lync Online</span><span class="sxs-lookup"><span data-stu-id="fa5dd-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="fa5dd-114">Accesso al sito di provisioning di connettività per messaggistica istantanea pubblica di Lync Server da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa5dd-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="fa5dd-115">Abilitazione della connettività Lync-Skype in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa5dd-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="fa5dd-116">Utilizzo della connettività Lync-Skype in Lync Server 2013 come utente finale</span><span class="sxs-lookup"><span data-stu-id="fa5dd-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="fa5dd-117">Domande frequenti: provisioning di Lync Server 2013 per la connettività Skype</span><span class="sxs-lookup"><span data-stu-id="fa5dd-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

