---
title: 'Lync Server 2013: distribuzione del portale Web amministrativo di Lync room System'
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
ms.openlocfilehash: 945532f4f0514263ed0d72e00ac5224aa6d7120b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="ac94b-102">Distribuzione del portale Web amministrativo di Lync room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac94b-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac94b-103">_**Ultimo argomento modificato:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="ac94b-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="ac94b-104">Il portale Web amministrativo di Microsoft Lync Server 2013 Lync room System (LRS) è un portale Web che può essere utilizzato dalle organizzazioni per gestire le sale conferenze di Lync room System.</span><span class="sxs-lookup"><span data-stu-id="ac94b-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="ac94b-105">Gli amministratori possono utilizzare il portale Web amministrativo di LRS per monitorare l'integrità di LRS, ad esempio monitorando i dispositivi audio/video connessi.</span><span class="sxs-lookup"><span data-stu-id="ac94b-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="ac94b-106">Con questo portale, gli amministratori possono raccogliere informazioni diagnostiche in remoto per monitorare l'integrità della sala riunioni.</span><span class="sxs-lookup"><span data-stu-id="ac94b-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="ac94b-107">Il portale Web amministrativo di LRS è distribuito in tutti i Front End Server Lync.</span><span class="sxs-lookup"><span data-stu-id="ac94b-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="ac94b-108">In questa guida vengono fornite istruzioni per gli amministratori su come installare e configurare il portale Web amministrativo di LRS.</span><span class="sxs-lookup"><span data-stu-id="ac94b-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="ac94b-109">È destinato agli amministratori che dispongono della conoscenza dell'amministrazione di Lync Server e che dispongono di diritti utente di amministratore per modificare la topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac94b-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="ac94b-110">Dopo la distribuzione del portale Web amministrativo di LRS nel server, gli amministratori possono controllare lo stato di tutte le sale di LRS accedendo al sito dal proprio computer o laptop.</span><span class="sxs-lookup"><span data-stu-id="ac94b-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ac94b-111">Quando si installa il portale Web di amministrazione di LRS in una distribuzione di Microsoft Lync Server 2013, è necessario utilizzare il <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">portale Web amministrativo di Microsoft Lync room per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ac94b-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="ac94b-112">È disponibile una nuova versione del portale Web amministrativo di LRS per Skype for Business Server 2015, ma non è necessario installare tale versione a meno che non sia stato distribuito Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ac94b-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="ac94b-113">Scaricare il <A href="http://go.microsoft.com/fwlink/?linkid=544807">portale Web amministrativo di Microsoft Lync room System per Skype for Business Server 2015</A>.</span><span class="sxs-lookup"><span data-stu-id="ac94b-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac94b-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="ac94b-114">In This Section</span></span>

[<span data-ttu-id="ac94b-115">Configurazione dell'ambiente Lync Server 2013 per il portale Web amministrativo di Lync room System</span><span class="sxs-lookup"><span data-stu-id="ac94b-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="ac94b-116">Installazione del portale Web amministrativo di Lync room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac94b-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="ac94b-117">Utilizzo del portale Web amministrativo di Lync room System in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac94b-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac94b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac94b-118">See Also</span></span>


[<span data-ttu-id="ac94b-119">Distribuzione di servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac94b-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

