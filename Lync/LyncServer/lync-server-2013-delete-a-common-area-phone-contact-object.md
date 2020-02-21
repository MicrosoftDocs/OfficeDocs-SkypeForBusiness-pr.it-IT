---
title: 'Lync Server 2013: eliminare un oggetto contatto telefonico di area comune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e0bd9d635cc745c10836c58a331d2e36380e446
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Eliminare un oggetto contatto telefonico di area comune in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

È possibile che si desideri eliminare l'oggetto contatto associato a un telefono di area comune. Ad esempio, se si rimuove il telefono da una sala per i dipendenti, non è necessario che un oggetto contatto sia associato a tale telefono. Il cmdlet **Remove-CsCommonAreaPhone** consente di eliminare gli account telefonici delle aree comuni. Quando si esegue questo cmdlet, il telefono viene eliminato dall'elenco dei telefoni delle aree comuni restituiti da **Get-CsCommonAreaPhone**. Inoltre, l'oggetto contatto associato a tale telefono viene eliminato da servizi di dominio Active Directory.

Utilizzare **Remove-CsCommonAreaPhone** per rimuovere un telefono di area comune o tutti i telefoni delle aree comuni che dispongono di un elemento comune, ad esempio un nome visualizzato o un paese e un prefisso. È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Rimozione di un telefono di area comune specificato

  - Il comando seguente rimuove il telefono di area comune con l'indirizzo SIP sip:mainlobby@litwareinc.com:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Rimozione dei telefoni delle aree comuni in base al nome visualizzato

  - Questo comando consente di rimuovere tutti i telefoni delle aree comuni in cui il nome visualizzato include il valore stringa "Building 14":
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Rimozione dei telefoni delle aree comuni in base ai rispettivi codici di paese e area

  - Questo comando consente di rimuovere tutti i telefoni delle aree comuni per gli Stati Uniti (codice paese 1) e il prefisso di area 425:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

