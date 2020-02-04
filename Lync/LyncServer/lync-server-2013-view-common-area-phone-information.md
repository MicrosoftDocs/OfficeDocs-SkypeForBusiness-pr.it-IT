---
title: 'Lync Server 2013: visualizzare le informazioni sul telefono di area comune'
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
ms.openlocfilehash: 38614b2993ddd9ad3fe3a662a334440a1d1287b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a>Visualizzare le informazioni sul telefono di area comune in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

Puoi visualizzare informazioni sui telefoni delle aree comuni configurati per l'uso nell'organizzazione usando il cmdlet **Get-CsCommonAreaPhone** . Usato senza parametri, questo cmdlet restituisce informazioni su tutti i telefoni delle aree comuni. I parametri facoltativi consentono di filtrare le informazioni in modo diverso. Ad esempio, puoi restituire tutti i telefoni delle aree comuni che hanno oggetti contatto in un'unità organizzativa specificata o in tutti gli oggetti contatti presenti in un edificio specificato. Per informazioni dettagliate sui parametri **Get-CsCommonAreaPhone** , vedere [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).

Eseguire **Get-CsCommonAreaPhone** da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a>Visualizzazione di informazioni su tutti i telefoni delle aree comuni

  - Per visualizzare informazioni su tutti i telefoni delle aree comuni, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsCommonAreaPhone
    
    Otterrai informazioni simili a queste:
    
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

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

