---
title: 'Lync Server 2013: distribuzione di un Survivable Branch Appliance o server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445df692041e24f8a4e134836ea9f6a63561a2ca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="34867-102">Distribuzione di un Survivable Branch Appliance o server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34867-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34867-103">_**Ultimo argomento modificato:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="34867-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="34867-104">Resiliente Enterprise Voice si riferisce alla resilienza dei siti di succursale, ovvero la possibilità di fornire un servizio di VoIP aziendale continuo per la succursale degli utenti del sito nel caso in cui il collegamento al sito centrale non diventi disponibile.</span><span class="sxs-lookup"><span data-stu-id="34867-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="34867-105">Per i siti di succursale di piccole e medie dimensioni (siti di succursale con utenti da 25 a 1.000), è consigliabile distribuire un Survivable Branch Appliance, che consente di terminare le chiamate PSTN (Public Switched Telephone Network) tramite il gateway PSTN incorporato o un trunk SIP a un telefono provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="34867-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="34867-106">Un Survivable Branch Appliance è un dispositivo di terze parti che include un server blade che esegue il sistema operativo Windows Server 2008 R2, il servizio di registrazione di Lync Server 2013, il software Mediation Server e un gateway PSTN, tutto in un singolo chassis di appliance.</span><span class="sxs-lookup"><span data-stu-id="34867-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="34867-107">Per i siti di succursale con 1.000 a 5.000 utenti e nessuna WAN resiliente, è consigliabile un Survivable Branch Server connesso a un gateway PSTN o a un trunk SIP a un provider di servizi di telefonia.</span><span class="sxs-lookup"><span data-stu-id="34867-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="34867-108">Survivable Branch Server è un computer basato su Windows Server in cui è installato il software di registrazione e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="34867-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34867-109">Per i siti di succursale con più di 5.000 utenti e amministratori dedicati di Lync Server, è consigliabile disporre di una distribuzione completa di Lync Server 2013, separata da quella del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="34867-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="34867-110">Per informazioni dettagliate sulla scelta della soluzione di resilienza ottimale per i siti di succursale nell'organizzazione, inclusi i prerequisiti e le considerazioni relative alla pianificazione, vedere <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisiti di resilienza dei siti di succursale per Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="34867-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="34867-111">Gli utenti ospitati in un Survivable Branch Appliance di Lync Server non sono in grado di creare nuove chat room o di visualizzare la scheda sala per le sale esistenti.</span><span class="sxs-lookup"><span data-stu-id="34867-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="34867-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="34867-112">In This Section</span></span>

  - [<span data-ttu-id="34867-113">Distribuzione di un Survivable Branch Appliance o server con Lync Server 2013-attività del sito centrale</span><span class="sxs-lookup"><span data-stu-id="34867-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="34867-114">Distribuire un Survivable Branch Appliance o server con Lync Server 2013-Branch site Task</span><span class="sxs-lookup"><span data-stu-id="34867-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="34867-115">Configurazione degli utenti per la resilienza dei siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34867-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="34867-116">Utenti domestici in un Survivable Branch Appliance o server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34867-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="34867-117">Appendici: Survivable Branch Appliance e server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34867-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34867-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34867-118">See Also</span></span>


[<span data-ttu-id="34867-119">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34867-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

