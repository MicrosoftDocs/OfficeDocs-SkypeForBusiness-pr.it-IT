---
title: 'Lync Server 2013: delegare le autorizzazioni di installazione'
description: 'Lync Server 2013: delegare le autorizzazioni di installazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7038cf729bad459dbcd2a84a308b14aa56b68dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545342"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="af1b3-103">Delegare le autorizzazioni di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af1b3-103">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af1b3-104">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="af1b3-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="af1b3-105">Se non si desidera concedere l'appartenenza al gruppo Domain Admins agli utenti o ai gruppi che stanno distribuendo Lync Server 2013, è possibile consentire ai membri del gruppo RTCUniversalServerAdmins di eseguire il cmdlet **Enable-CsTopology**di   Windows PowerShell nei server che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af1b3-105">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="af1b3-106">Per impostazione predefinita, i membri del gruppo RTCUniversalServerAdmins non hanno la possibilità di eseguire questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="af1b3-106">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="af1b3-107">È possibile concedere i diritti e le autorizzazioni di amministratore per eseguire **Enable-CsTopology** nei server che eseguono Lync Server utilizzando il cmdlet **Grant-CsSetupPermission** e specificando un'unità organizzativa in cui si trovano gli oggetti computer per il server che esegue Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af1b3-107">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="af1b3-108">La preparazione del dominio che si verifica quando si installa Lync Server non aggiunge automaticamente le autorizzazioni che consentono ai membri del gruppo RTCUniversalServerAdmins di eseguire il cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="af1b3-108">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="af1b3-109">Per questo motivo, per impostazione predefinita è necessario essere amministratori di dominio per abilitare una topologia.</span><span class="sxs-lookup"><span data-stu-id="af1b3-109">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="af1b3-110">Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di abilitare una topologia, è necessario eseguire il cmdlet Grant-CsSetupPermissions.</span><span class="sxs-lookup"><span data-stu-id="af1b3-110">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="af1b3-111">Inoltre, è necessario eseguire questo cmdlet su ogni contenitore di Active Directory che ospita i computer che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af1b3-111">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="af1b3-112">Questo cmdlet concede esclusivamente le autorizzazioni al gruppo RTCUniversalServerAdmins; non può essere utilizzato per concedere le autorizzazioni ad altri gruppi di sicurezza o a singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="af1b3-112">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af1b3-113"><STRONG>Enable-CsTopology</STRONG> è il cmdlet Key che consente ai membri del gruppo RTCUniversalServerAdmins di configurare e distribuire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af1b3-113"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="af1b3-114">Per aggiungere la possibilità di eseguire Enable-CsTopology al gruppo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="af1b3-114">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="af1b3-115">Accedere a un server come membro del gruppo Domain Admins per il dominio in cui l'utente delegato verrà eseguito **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="af1b3-115">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="af1b3-116">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="af1b3-116">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="af1b3-117">Lync Server 2013 Management Shell viene installato automaticamente in ogni Front End Server o in qualsiasi computer in cui sono stati installati gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af1b3-117">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="af1b3-118">Per informazioni dettagliate su Lync Server 2013 Management Shell, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="af1b3-118">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="af1b3-119">Eseguire il cmdlet seguente da Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="af1b3-119">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af1b3-120">Se l'unità organizzativa non è di livello principale, è necessario specificare il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="af1b3-120">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="af1b3-121">Nell'esempio seguente l'unità organizzativa è "Lync Server", che si trova nel dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="af1b3-121">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

