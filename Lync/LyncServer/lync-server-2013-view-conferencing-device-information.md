---
title: 'Lync Server 2013: visualizzare le informazioni sul dispositivo per i servizi di conferenza'
description: 'Lync Server 2013: visualizzare le informazioni sul dispositivo per i servizi di conferenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bbbdcecbc15ef59b2b9e22ffd2b28ff745d67a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574772"
---
# <a name="view-conferencing-device-information-in-lync-server-2013"></a>Visualizzare le informazioni sui dispositivi di conferenza in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

È possibile visualizzare informazioni sui dispositivi di conferenza configurati per l'utilizzo nell'organizzazione tramite Windows PowerShell e il cmdlet **Get-CsMeetingRoom** . Eseguire il cmdlet **Get-CsMeetingRoom** da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

Se si utilizza il cmdlet **Get-CsMeetingRoom** senza parametri, vengono restituite informazioni su tutti i dispositivi per conferenze. I parametri facoltativi consentono di filtrare le informazioni in modi diversi. Per informazioni dettagliate, vedere la sezione Parameters di [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a>Visualizzazione di informazioni su tutti i dispositivi per conferenze

  - Per visualizzare i dettagli su tutti i dispositivi per conferenze, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsMeetingRoom
    
    Questo cmdlet restituisce informazioni simili alle seguenti per ogni dispositivo per conferenze. Si noti che in questo esempio vengono mostrate solo alcune delle informazioni che verranno visualizzate quando si esegue questo cmdlet:
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a>Visualizzazione di informazioni su uno specifico dispositivo per i servizi di conferenza

  - Per visualizzare le informazioni relative a un dispositivo Conferencing specifico, includere il parametro Identity seguito dall'identità del dispositivo per i servizi di conferenza (in genere, il nome visualizzato di Active Directory). Ad esempio:
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

