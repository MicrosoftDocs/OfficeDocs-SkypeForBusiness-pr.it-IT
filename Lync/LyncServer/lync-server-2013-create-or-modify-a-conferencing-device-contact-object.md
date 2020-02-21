---
title: 'Lync Server 2013: creare o modificare un oggetto contatto per i dispositivi di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74808a2deae4f7fa52e1a48fcbd415205eca93cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Creare o modificare un oggetto contatto per i dispositivi di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-02_

Per creare un oggetto sala conferenze, creare innanzitutto un account utente di Active Directory per rappresentare il dispositivo. Utilizzare quindi il cmdlet **Enable-CsMeetingRoom** per consentire a tale account di funzionare come dispositivo per i servizi di conferenza. Se è necessario modificare le proprietà di un dispositivo per i servizi di conferenza esistente, utilizzare il cmdlet **set-CsMeetingRoom** .

Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Creazione di un dispositivo per conferenze

  - Dopo aver creato l'account utente di Active Directory che rappresenta il nuovo dispositivo per conferenze, abilitarlo utilizzando il cmdlet **Enable-CsMeetingRoom** . Assicurarsi di includere a) l'identità del dispositivo per i servizi di conferenza, b) il pool di registrazione in cui verrà ospitata l'account della sala e c) l'indirizzo SIP da assegnare a quell'account. Ad esempio:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Modifica di un dispositivo per conferenze

  - Per modificare i valori delle proprietà di un dispositivo per i servizi di conferenza esistente, utilizzare il cmdlet **set-CsMeetingRoom** . Ad esempio, il seguente comando Aggiorna il numero di telefono (LineUri) associato a un dispositivo per conferenze:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e il cmdlet [set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

