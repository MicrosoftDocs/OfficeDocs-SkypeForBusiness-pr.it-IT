---
title: 'Lync Server 2013: distribuzione del portale Web amministrativo di Lync room System'
description: 'Lync Server 2013: distribuzione del portale Web amministrativo di Lync room System.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e67723b3ddf3f452c53411e560420bb0b043128e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565982"
---
# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="f9d4b-103">Distribuzione del portale Web amministrativo di Lync room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9d4b-103">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9d4b-104">_**Ultimo argomento modificato:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="f9d4b-104">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="f9d4b-105">Il portale Web amministrativo di Microsoft Lync Server 2013 Lync room System (LRS) è un portale Web che può essere utilizzato dalle organizzazioni per gestire le sale conferenze di Lync room System.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-105">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="f9d4b-106">Gli amministratori possono utilizzare il portale Web amministrativo di LRS per monitorare l'integrità di LRS, ad esempio monitorando i dispositivi audio/video connessi.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-106">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="f9d4b-107">Con questo portale, gli amministratori possono raccogliere informazioni diagnostiche in remoto per monitorare l'integrità della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-107">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="f9d4b-108">Il portale Web amministrativo di LRS è distribuito in tutti i Front End Server Lync.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-108">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="f9d4b-109">In questa guida vengono fornite istruzioni per gli amministratori su come installare e configurare il portale Web amministrativo di LRS.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-109">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="f9d4b-110">È destinato agli amministratori che dispongono della conoscenza dell'amministrazione di Lync Server e che dispongono di diritti utente di amministratore per modificare la topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-110">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="f9d4b-111">Dopo la distribuzione del portale Web amministrativo di LRS nel server, gli amministratori possono controllare lo stato di tutte le sale di LRS accedendo al sito dal proprio computer o laptop.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-111">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9d4b-112">Quando si installa il portale Web di amministrazione di LRS in una distribuzione di Microsoft Lync Server 2013, è necessario utilizzare il <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">portale Web amministrativo di Microsoft Lync room per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-112">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="https://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="f9d4b-113">È disponibile una nuova versione del portale Web amministrativo di LRS per Skype for Business Server 2015, ma non è necessario installare tale versione a meno che non sia stato distribuito Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-113">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="f9d4b-114">Scaricare il <A href="https://go.microsoft.com/fwlink/?linkid=544807">portale Web amministrativo di Microsoft Lync room System per Skype for Business Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="f9d4b-114">Download the <A href="https://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f9d4b-115">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="f9d4b-115">In This Section</span></span>

[<span data-ttu-id="f9d4b-116">Configurazione dell'ambiente Lync Server 2013 per il portale Web amministrativo di Lync room System</span><span class="sxs-lookup"><span data-stu-id="f9d4b-116">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="f9d4b-117">Installazione del portale Web amministrativo di Lync room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9d4b-117">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="f9d4b-118">Utilizzo del portale Web amministrativo di Lync room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9d4b-118">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9d4b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9d4b-119">See Also</span></span>


[<span data-ttu-id="f9d4b-120">Distribuzione di servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9d4b-120">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

