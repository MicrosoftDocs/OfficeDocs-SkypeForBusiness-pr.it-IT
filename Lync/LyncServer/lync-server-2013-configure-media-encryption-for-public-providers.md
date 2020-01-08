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

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Configurare la crittografia multimediale per i provider pubblici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-12-12_

Se stai implementando una Federazione audio/video (A/V) con Windows Live Messenger, devi modificare due parametri: il livello di crittografia del server Lync e i criteri di EnablePublicCloudAccess. Per impostazione predefinita, il livello di crittografia è impostato su obbligatorio. È necessario modificare questa impostazione in supported. Se il criterio EnablePublicCloudAccess è impostato su false, deve essere impostato su **true**. Puoi eseguire questa operazione da Lync Server Management Shell.

<div>

## <a name="configure-federation-for-windows-live"></a>Configurare la Federazione per Windows Live

1.  Avviare Lync Server Management Shell nel server front-end: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Dal prompt dei comandi digitare i comandi seguenti:
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Questo è il passaggio necessario perché Windows Live Messenger non supporta la crittografia di audio/video. Il comando imposta il criterio globale su un'impostazione di crittografia del supporto invece di richiedere la crittografia dei dati audio/video. I client che supportano la crittografia continueranno a usare la crittografia, ad esempio Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

