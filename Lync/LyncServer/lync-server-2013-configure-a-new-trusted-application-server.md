---
title: 'Lync Server 2013: configurare un nuovo server applicazioni attendibile'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e053629eae42bc7fcd83b0002b3aad40f3550f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507713"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="81176-102">Configurare un nuovo server applicazioni attendibile in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81176-102">Configure a new trusted application server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81176-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="81176-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="81176-104">Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK che è considerato attendibile da Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81176-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="81176-105">Per informazioni dettagliate sulle applicazioni di UCMA, vedere la documentazione relativa a Unified Communications Managed API 3,0 Core SDK [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) .</span><span class="sxs-lookup"><span data-stu-id="81176-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="81176-106">Per informazioni sulla configurazione di Microsoft Outlook Web Access (OWA) e Lync Server 2013, vedere la sezione relativa alla configurazione di Outlook Web App e Lync Server 2010 Integration nella documentazione relativa a Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81176-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="81176-107">Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario avere eseguito l'accesso come membro dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="81176-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="81176-108">È inoltre possibile delegare le autorizzazioni e i diritti di amministratore appropriati per l'aggiunta di ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="81176-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="81176-109">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="81176-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="81176-110">Per poter apportare altre modifiche relative alla configurazione, è necessario appartenere solo al gruppo RTCUniversalServerAdmins..</span><span class="sxs-lookup"><span data-stu-id="81176-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="81176-111">Per configurare un server applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="81176-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="81176-112">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="81176-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="81176-113">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="81176-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="81176-114">Selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="81176-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="81176-115">Nella finestra di dialogo **Salva topologia con nome** fare clic sul file del generatore di topologie che si desidera utilizzare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="81176-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="81176-116">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili**e quindi scegliere **nuovo pool di applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="81176-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="81176-117">Immettere il valore di **FQDN pool** per il pool di applicazioni attendibili, specificare se sarà un pool a server singolo o a più server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="81176-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="81176-118">Nell'elenco nella pagina **selezionare l'hop successivo** selezionare il pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81176-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="81176-119">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="81176-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="81176-120">Selezionare il nodo principale **Lync Server 2013**e quindi fare clic su **Pubblica topologia**dal menu **azioni** .</span><span class="sxs-lookup"><span data-stu-id="81176-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="81176-121">È necessario che il **pool di applicazioni attendibili** sia stato creato correttamente e sia associato al pool Front end corretto.</span><span class="sxs-lookup"><span data-stu-id="81176-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

