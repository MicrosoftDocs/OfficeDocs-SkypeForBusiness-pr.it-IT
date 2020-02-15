---
title: 'Lync Server 2013: personalizzare la musica del parcheggio di chiamata in attesa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feebc353b48b3a6b8f9adb17c08ab9af778bb1ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="1c5f6-102">Personalizzare la musica del parcheggio di chiamata in attesa in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c5f6-102">Customize Call Park music on hold in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c5f6-103">_**Ultimo argomento modificato:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="1c5f6-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="1c5f6-104">È possibile specificare un file musicale personalizzato da utilizzare per la musica di attesa, anziché il file musicale predefinito fornito con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1c5f6-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="1c5f6-105">Per personalizzare la musica di attesa, utilizzare il cmdlet **Set-CsCallParkServiceMusicOnHoldFile**.</span><span class="sxs-lookup"><span data-stu-id="1c5f6-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c5f6-106">Se si Personalizza la musica di attesa e si desidera la stessa musica per più siti, è necessario configurare il file musicale per ogni sito che esegue l'applicazione Parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1c5f6-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="1c5f6-107">Per personalizzare il file musicale</span><span class="sxs-lookup"><span data-stu-id="1c5f6-107">To customize the music file</span></span>

1.  <span data-ttu-id="1c5f6-108">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1c5f6-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1c5f6-109">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1c5f6-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1c5f6-110">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="1c5f6-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1c5f6-111">Utilizzare il cmdlet <STRONG>Get-CsService</STRONG> per identificare il servizio.</span><span class="sxs-lookup"><span data-stu-id="1c5f6-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="1c5f6-112">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span><span class="sxs-lookup"><span data-stu-id="1c5f6-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="1c5f6-113">L'esempio seguente mostra come ottenere il contenuto del file soothingmusic.wma sotto forma di matrice di byte e come assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="1c5f6-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="1c5f6-114">Il file audio viene quindi assegnato come file di musica di attesa per Call Park.</span><span class="sxs-lookup"><span data-stu-id="1c5f6-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="1c5f6-115">Per informazioni dettagliate, vedere [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span><span class="sxs-lookup"><span data-stu-id="1c5f6-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c5f6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c5f6-116">See Also</span></span>


[<span data-ttu-id="1c5f6-117">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="1c5f6-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="1c5f6-118">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="1c5f6-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

