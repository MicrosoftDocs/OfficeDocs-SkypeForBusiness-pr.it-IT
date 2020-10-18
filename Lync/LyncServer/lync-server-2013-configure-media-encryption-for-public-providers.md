---
title: 'Lync Server 2013: configurare la crittografia multimediale per i provider pubblici'
description: 'Lync Server 2013: configurare la crittografia multimediale per i provider pubblici.'
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
ms.openlocfilehash: 177c19f151b67d741c7e26506f7ebc98b3ce831a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577622"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Configurare la crittografia multimediale per i provider pubblici in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-12_

Se si sta implementando la Federazione audio/video (A/V) con Windows Live Messenger, sono disponibili due parametri che è necessario modificare: il livello di crittografia di Lync Server e i criteri di EnablePublicCloudAccess. Per impostazione predefinita, il livello di crittografia è impostato su RequireEncryption. È necessario impostarlo su SupportEncryption. Se il criterio EnablePublicCloudAccess è impostato su False, deve essere impostato su **True**. È possibile eseguire questa operazione da Lync Server Management Shell.

<div>

## <a name="configure-federation-for-windows-live"></a>Configurare la federazione per Windows Live

1.  Avviare Lync Server Management Shell nel front end server: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.

2.  Al prompt dei comandi digitare i comandi seguenti:
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Questo passaggio è necessario perché Windows Live Messenger non supporta la crittografia dei dati audio/video. Il comando configura il criterio globale su un'impostazione di crittografia supportata anziché di crittografia richiesta per tali dati. I client che supportano la crittografia utilizzeranno comunque la crittografia, ad esempio Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

