---
title: 'Lync Server 2013: configurare i numeri di accesso per le conferenze telefoniche in ingresso'
description: 'Lync Server 2013: configurare i numeri di accesso per le conferenze telefoniche con chiamata in ingresso.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0edb3492c243b36b69c4b48df8c22adc4ece7999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565081"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Configurare i numeri di accesso per le conferenze telefoniche con chiamata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2011-07-17_

Quando si distribuiscono le conferenze telefoniche con accesso esterno, è necessario configurare i numeri di telefono che gli utenti possono comporre dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze. Questi numeri di accesso esterno vengono visualizzati negli inviti alle riunioni e nella pagina Web delle impostazioni per le conferenze telefoniche con chiamata in ingresso.

Prima di poter creare numeri di accesso esterno, è necessario prima di tutto pianificare le aree di audioconferenza e quindi configurare i dial plan con le aree geografiche. Per informazioni dettagliate sulle aree geografiche, vedere Servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sulla configurazione dei dial plan per le conferenze telefoniche con accesso esterno, vedere [configurare dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<div>


> [!NOTE]  
> Non è possibile utilizzare un nuovo numero di accesso esterno finché non viene completata la replica di servizi di dominio Active Directory (AD &nbsp; DS) del numero di accesso. La replica può richiedere diverse ore per il completamento.



</div>

<div>


> [!NOTE]  
> Dopo aver creato i numeri di accesso esterno, è possibile modificare il nome visualizzato per gli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto. Utilizzare il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> per modificare il nome visualizzato. Non è necessario modificare gli oggetti di Active Directory manualmente. Per informazioni dettagliate sulla modifica di un numero di accesso, vedere la documentazione di Lync Server Management Shell per il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> .



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

[Creare o modificare un numero di accesso per le conferenze telefoniche in Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti per le conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[Configurare i dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

