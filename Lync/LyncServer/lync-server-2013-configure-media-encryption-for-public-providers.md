---
title: 'Lync Server 2013: configurare la crittografia multimediale per i provider pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73d914e77f5ae53e5b7e22cdc3392fe6bc22ef64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="e1fbd-102">Configurare la crittografia multimediale per i provider pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1fbd-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1fbd-103">_**Ultimo argomento modificato:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="e1fbd-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="e1fbd-104">Se si sta implementando la Federazione audio/video (A/V) con Windows Live Messenger, sono disponibili due parametri che è necessario modificare: il livello di crittografia di Lync Server e i criteri di EnablePublicCloudAccess.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="e1fbd-105">Per impostazione predefinita, il livello di crittografia è impostato su RequireEncryption.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="e1fbd-106">È necessario impostarlo su SupportEncryption.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-106">You must change this setting to Supported.</span></span> <span data-ttu-id="e1fbd-107">Se il criterio EnablePublicCloudAccess è impostato su False, deve essere impostato su **True**.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="e1fbd-108">È possibile eseguire questa operazione da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="e1fbd-109">Configurare la federazione per Windows Live</span><span class="sxs-lookup"><span data-stu-id="e1fbd-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="e1fbd-110">Avviare Lync Server Management Shell nel front end server: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e1fbd-111">Al prompt dei comandi digitare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1fbd-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="e1fbd-112">Questo passaggio è necessario perché Windows Live Messenger non supporta la crittografia dei dati audio/video.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="e1fbd-113">Il comando configura il criterio globale su un'impostazione di crittografia supportata anziché di crittografia richiesta per tali dati.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="e1fbd-114">I client che supportano la crittografia utilizzeranno comunque la crittografia, ad esempio Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

