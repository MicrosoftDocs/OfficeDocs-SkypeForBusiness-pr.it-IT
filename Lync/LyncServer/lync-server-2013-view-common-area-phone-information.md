---
title: 'Lync Server 2013: visualizzare le informazioni sui telefoni delle aree comuni'
description: 'Lync Server 2013: visualizzare le informazioni sui telefoni delle aree comuni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4debe9a76118ac0bf1ca711426ce5487009a053
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572472"
---
# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Visualizzare le informazioni sui telefoni delle aree comuni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

È possibile visualizzare informazioni sui telefoni delle aree comuni configurati per l'utilizzo nell'organizzazione utilizzando il cmdlet **Get-CsCommonAreaPhone** . Utilizzato senza parametri, questo cmdlet restituisce informazioni su tutti i telefoni delle aree comuni. I parametri facoltativi consentono di filtrare le informazioni in modi diversi. Ad esempio, è possibile restituire tutti i telefoni delle aree comuni che dispongono di oggetti contatto in un'unità organizzativa specificata o in tutti gli oggetti contatti situati in un determinato edificio. Per informazioni dettagliate sui parametri **Get-CsCommonAreaPhone** , vedere [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).

Eseguire **Get-CsCommonAreaPhone** sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>Visualizzazione delle informazioni su tutti i telefoni delle aree comuni

  - Per visualizzare informazioni su tutti i telefoni delle aree comuni, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsCommonAreaPhone
    
    Otterrete informazioni simili alle seguenti:
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

