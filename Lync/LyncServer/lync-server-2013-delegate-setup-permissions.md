---
title: 'Lync Server 2013: delegare le autorizzazioni di installazione'
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
ms.openlocfilehash: 453da166895c79cafe9f9637163e93a63ebccd75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504283"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="47e14-102">Delegare le autorizzazioni di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47e14-102">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47e14-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="47e14-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="47e14-104">Se non si desidera concedere l'appartenenza al gruppo Domain Admins agli utenti o ai gruppi che stanno distribuendo Lync Server 2013, è possibile consentire ai membri del gruppo RTCUniversalServerAdmins di eseguire il cmdlet **Enable-CsTopology**di   Windows PowerShell nei server che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47e14-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="47e14-105">Per impostazione predefinita, i membri del gruppo RTCUniversalServerAdmins non hanno la possibilità di eseguire questo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="47e14-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="47e14-106">È possibile concedere i diritti e le autorizzazioni di amministratore per eseguire **Enable-CsTopology** nei server che eseguono Lync Server utilizzando il cmdlet **Grant-CsSetupPermission** e specificando un'unità organizzativa in cui si trovano gli oggetti computer per il server che esegue Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47e14-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="47e14-107">La preparazione del dominio che si verifica quando si installa Lync Server non aggiunge automaticamente le autorizzazioni che consentono ai membri del gruppo RTCUniversalServerAdmins di eseguire il cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="47e14-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="47e14-108">Per questo motivo, per impostazione predefinita è necessario essere amministratori di dominio per abilitare una topologia.</span><span class="sxs-lookup"><span data-stu-id="47e14-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="47e14-109">Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di abilitare una topologia, è necessario eseguire il cmdlet Grant-CsSetupPermissions.</span><span class="sxs-lookup"><span data-stu-id="47e14-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="47e14-110">Inoltre, è necessario eseguire questo cmdlet su ogni contenitore di Active Directory che ospita i computer che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47e14-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="47e14-111">Questo cmdlet concede esclusivamente le autorizzazioni al gruppo RTCUniversalServerAdmins; non può essere utilizzato per concedere le autorizzazioni ad altri gruppi di sicurezza o a singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="47e14-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47e14-112"><STRONG>Enable-CsTopology</STRONG> è il cmdlet Key che consente ai membri del gruppo RTCUniversalServerAdmins di configurare e distribuire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47e14-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="47e14-113">Per aggiungere la possibilità di eseguire Enable-CsTopology al gruppo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="47e14-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="47e14-114">Accedere a un server come membro del gruppo Domain Admins per il dominio in cui l'utente delegato verrà eseguito **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="47e14-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="47e14-115">Aprire Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="47e14-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="47e14-116">Lync Server 2013 Management Shell viene installato automaticamente in ogni Front End Server o in qualsiasi computer in cui sono stati installati gli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47e14-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="47e14-117">Per informazioni dettagliate su Lync Server 2013 Management Shell, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="47e14-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="47e14-118">Eseguire il cmdlet seguente da Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="47e14-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47e14-119">Se l'unità organizzativa non è di livello principale, è necessario specificare il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="47e14-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="47e14-120">Nell'esempio seguente l'unità organizzativa è "Lync Server", che si trova nel dominio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="47e14-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

