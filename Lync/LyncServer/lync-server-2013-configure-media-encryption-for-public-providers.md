---
title: 'Lync Server 2013: Configurare la crittografia multimediale per i provider pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 270035730b8268c56b1730d8c212e90c8a9f1a30
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40980848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="88235-102">Configurare la crittografia multimediale per i provider pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88235-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88235-103">_**Argomento Ultima modifica:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="88235-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="88235-104">Se stai implementando una Federazione audio/video (A/V) con Windows Live Messenger, devi modificare due parametri: il livello di crittografia del server Lync e i criteri di EnablePublicCloudAccess.</span><span class="sxs-lookup"><span data-stu-id="88235-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="88235-105">Per impostazione predefinita, il livello di crittografia è impostato su obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="88235-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="88235-106">È necessario modificare questa impostazione in supported.</span><span class="sxs-lookup"><span data-stu-id="88235-106">You must change this setting to Supported.</span></span> <span data-ttu-id="88235-107">Se il criterio EnablePublicCloudAccess è impostato su false, deve essere impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="88235-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="88235-108">Puoi eseguire questa operazione da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="88235-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="88235-109">Configurare la Federazione per Windows Live</span><span class="sxs-lookup"><span data-stu-id="88235-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="88235-110">Avviare Lync Server Management Shell nel server front-end: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="88235-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="88235-111">Dal prompt dei comandi digitare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="88235-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="88235-112">Questo è il passaggio necessario perché Windows Live Messenger non supporta la crittografia di audio/video.</span><span class="sxs-lookup"><span data-stu-id="88235-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="88235-113">Il comando imposta il criterio globale su un'impostazione di crittografia del supporto invece di richiedere la crittografia dei dati audio/video.</span><span class="sxs-lookup"><span data-stu-id="88235-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="88235-114">I client che supportano la crittografia continueranno a usare la crittografia, ad esempio Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="88235-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

