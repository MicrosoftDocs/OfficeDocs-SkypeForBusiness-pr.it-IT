---
title: 'Lync Server 2013: Configurare i numeri di accesso per le conferenze telefoniche con accesso esterno'
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
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Configurare i numeri di accesso per le conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2011-07-17_

Quando si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario configurare i numeri di telefono che gli utenti possono effettuare la chiamata dalla rete PSTN (Public Switched Telephone Network) per partecipare alla parte audio delle conferenze. I numeri di accesso per le connessioni in ingresso vengono visualizzati negli inviti alle riunioni e nella pagina Web delle impostazioni di conferenza telefonica con accesso esterno.

Prima di poter creare numeri di accesso per la chiamata in ingresso, è necessario pianificare le aree dei servizi di conferenza telefonica con accesso esterno e quindi configurare i dial plan con le aree geografiche. Per informazioni dettagliate sulle aree geografiche, vedere Requisiti per i servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sulla configurazione dei dial plan per i servizi di conferenza telefonica con accesso esterno, vedere Configurare i dial plan per i servizi di [conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<div>


> [!NOTE]  
> Non è possibile usare un nuovo numero di accesso esterno finché non viene completata la replica di&nbsp;Active Directory Domain Services (ad DS). La replica può richiedere diverse ore per il completamento.



</div>

<div>


> [!NOTE]  
> Dopo aver creato i numeri di accesso esterno, è possibile modificare il nome visualizzato per gli oggetti contatto di Active Directory in modo che gli utenti possano identificare più facilmente il numero di accesso corretto. Usa il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> per modificare il nome visualizzato. Non è consigliabile modificare manualmente gli oggetti di Active Directory. Per informazioni dettagliate sulla modifica di un numero di accesso, vedere la documentazione di Lync Server Management Shell per il cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> .



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

[Creare o modificare un numero di accesso per una conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti per i servizi di conferenza telefonica con accesso esterno in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[Configurare dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

