---
title: "Lync Server 2013: eliminare un oggetto contatto telefonico per l'area comune"
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
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Eliminare un oggetto contatto telefonico per l'area comune in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

Potresti voler eliminare l'oggetto contatto associato a un telefono con area comune. Ad esempio, se si rimuove il telefono da una sala per i dipendenti, non è necessario che un oggetto contatto sia associato al telefono. Il cmdlet **Remove-CsCommonAreaPhone** offre un modo per eliminare gli account telefonici di area comune. Quando si esegue questo cmdlet, il telefono viene eliminato dall'elenco dei telefoni delle aree comuni restituiti da **Get-CsCommonAreaPhone**. Inoltre, l'oggetto contatto associato al telefono viene eliminato da servizi di dominio Active Directory.

Usare **Remove-CsCommonAreaPhone** per rimuovere un telefono con area comune o tutti i telefoni delle aree comuni che hanno un elemento comune, ad esempio un nome visualizzato o un paese e un prefisso. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Rimozione di un telefono di area comune specificato

  - Con il comando seguente viene rimosso il telefono per l'area comune con l'indirizzo SIP sip:mainlobby@litwareinc.com:
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Rimozione dei telefoni delle aree comuni in base al nome visualizzato

  - Questo comando rimuove tutti i telefoni delle aree comuni in cui il nome visualizzato include il valore stringa "Building 14":
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Rimozione dei telefoni delle aree comuni in base ai rispettivi codici paese e area

  - Questo comando rimuove tutti i telefoni delle aree comuni per gli Stati Uniti (codice paese 1) e il prefisso 425:
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

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

