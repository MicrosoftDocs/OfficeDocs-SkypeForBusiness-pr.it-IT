---
title: 'Lync Server 2013: creare o modificare un oggetto contatto per i dispositivi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b468b2338d115e7b646c28fd4d0b310b6e132d79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Creare o modificare un oggetto contatto per i dispositivi di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-02_

Per creare un oggetto sala conferenze, crea prima di tutto un account utente di Active Directory per rappresentare il dispositivo. USA quindi il cmdlet **Enable-CsMeetingRoom** per abilitare l'account come dispositivo per i servizi di conferenza. Se è necessario modificare le proprietà di un dispositivo di conferenza esistente, usare il cmdlet **set-CsMeetingRoom** .

Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Creazione di un dispositivo per i servizi di conferenza

  - Dopo aver creato l'account utente di Active Directory che rappresenta il nuovo dispositivo per i servizi di conferenza, abilitarlo usando il cmdlet **Enable-CsMeetingRoom** . Assicurati di includere un) l'identità del dispositivo di conferenza, b) il pool di registrar in cui verrà assegnato l'account della sala e c) l'indirizzo SIP da assegnare all'account. Ad esempio:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Modifica di un dispositivo per conferenze

  - Per modificare i valori delle proprietà di un dispositivo di conferenza esistente, usare il cmdlet **set-CsMeetingRoom** . Ad esempio, il comando seguente aggiorna il numero di telefono (LineUri) associato a un dispositivo per i servizi di conferenza:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e al cmdlet [set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

