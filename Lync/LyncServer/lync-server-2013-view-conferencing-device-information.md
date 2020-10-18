---
title: 'Lync Server 2013: visualizzare le informazioni sul dispositivo per i servizi di conferenza'
description: 'Lync Server 2013: visualizzare le informazioni sul dispositivo per i servizi di conferenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bbbdcecbc15ef59b2b9e22ffd2b28ff745d67a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574772"
---
# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="29275-103">Visualizzare le informazioni sui dispositivi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29275-103">View conferencing device information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29275-104">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="29275-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="29275-105">È possibile visualizzare informazioni sui dispositivi di conferenza configurati per l'utilizzo nell'organizzazione tramite Windows PowerShell e il cmdlet **Get-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="29275-105">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="29275-106">Eseguire il cmdlet **Get-CsMeetingRoom** da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29275-106">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29275-107">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="29275-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="29275-108">Se si utilizza il cmdlet **Get-CsMeetingRoom** senza parametri, vengono restituite informazioni su tutti i dispositivi per conferenze.</span><span class="sxs-lookup"><span data-stu-id="29275-108">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="29275-109">I parametri facoltativi consentono di filtrare le informazioni in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="29275-109">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="29275-110">Per informazioni dettagliate, vedere la sezione Parameters di [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span><span class="sxs-lookup"><span data-stu-id="29275-110">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="29275-111">Visualizzazione di informazioni su tutti i dispositivi per conferenze</span><span class="sxs-lookup"><span data-stu-id="29275-111">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="29275-112">Per visualizzare i dettagli su tutti i dispositivi per conferenze, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="29275-112">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="29275-113">Questo cmdlet restituisce informazioni simili alle seguenti per ogni dispositivo per conferenze.</span><span class="sxs-lookup"><span data-stu-id="29275-113">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="29275-114">Si noti che in questo esempio vengono mostrate solo alcune delle informazioni che verranno visualizzate quando si esegue questo cmdlet:</span><span class="sxs-lookup"><span data-stu-id="29275-114">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="29275-115">Visualizzazione di informazioni su uno specifico dispositivo per i servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="29275-115">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="29275-116">Per visualizzare le informazioni relative a un dispositivo Conferencing specifico, includere il parametro Identity seguito dall'identità del dispositivo per i servizi di conferenza (in genere, il nome visualizzato di Active Directory).</span><span class="sxs-lookup"><span data-stu-id="29275-116">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="29275-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="29275-117">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="29275-118">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="29275-118">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

