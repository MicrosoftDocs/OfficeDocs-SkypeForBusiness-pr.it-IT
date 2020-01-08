---
title: 'Lync Server 2013: configurare un nuovo server applicazioni attendibile'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc5a982724dd390ff97bf6dd4cad10f25572732
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="6a75b-102">Configurare un nuovo server applicazioni attendibile in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a75b-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a75b-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6a75b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6a75b-104">Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK attendibile per Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a75b-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6a75b-105">Per informazioni dettagliate sulle applicazioni di UCMA, vedere "documentazione su Unified Communications Managed API 3,0 Core [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)SDK" at.</span><span class="sxs-lookup"><span data-stu-id="6a75b-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="6a75b-106">Per informazioni sulla configurazione di Microsoft Outlook Web Access (OWA) e Lync Server 2013, vedere la pagina relativa alla configurazione di Outlook Web App e Lync Server 2010 Integration nella documentazione di Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a75b-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="6a75b-107">Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario essere connessi come utenti membri dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="6a75b-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="6a75b-108">È anche possibile delegare le autorizzazioni e i diritti di amministratore appropriati per l'aggiunta di ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="6a75b-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="6a75b-109">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6a75b-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="6a75b-110">Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6a75b-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="6a75b-111">Per configurare un server applicazioni attendibile</span><span class="sxs-lookup"><span data-stu-id="6a75b-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="6a75b-112">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6a75b-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6a75b-113">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6a75b-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="6a75b-114">Selezionare **Scarica topologia da distribuzione esistente**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a75b-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="6a75b-115">Nella finestra di dialogo **Salva topologia con nome** fare clic sul file di generatore di topologia che si vuole usare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a75b-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="6a75b-116">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili**e quindi scegliere **nuovo pool di applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="6a75b-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="6a75b-117">Immettere il **nome di dominio completo del pool** di applicazioni attendibili, selezionare se si tratta di un server singolo o di più server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6a75b-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="6a75b-118">Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool di front end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a75b-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="6a75b-119">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="6a75b-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="6a75b-120">Selezionare il nodo superiore **Lync Server 2013**e quindi, nel menu **azioni** , fare clic su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="6a75b-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="6a75b-121">Il **pool di applicazioni attendibili** deve essere stato creato correttamente e associato al pool Front-end corretto.</span><span class="sxs-lookup"><span data-stu-id="6a75b-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

