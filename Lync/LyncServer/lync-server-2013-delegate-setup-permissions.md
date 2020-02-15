---
title: 'Lync Server 2013: delegare le autorizzazioni di installazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 394200b21d3720f288fc89780c6ff193bd278cec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Delegare le autorizzazioni di installazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Se non si desidera concedere l'appartenenza al gruppo Domain Admins agli utenti o ai gruppi che stanno distribuendo Lync Server 2013, è possibile consentire ai membri del gruppo RTCUniversalServerAdmins di eseguire il cmdlet **Enable-CsTopology** di Windows PowerShell nei server che eseguono Lync Server 2013. Per impostazione predefinita, i membri del gruppo RTCUniversalServerAdmins non hanno la possibilità di eseguire questo cmdlet. È possibile concedere i diritti e le autorizzazioni di amministratore per eseguire **Enable-CsTopology** nei server che eseguono Lync Server utilizzando il cmdlet **Grant-CsSetupPermission** e specificando un'unità organizzativa in cui si trovano gli oggetti computer per il server che esegue Lync Server 2013.

La preparazione del dominio che si verifica quando si installa Lync Server non aggiunge automaticamente le autorizzazioni che consentono ai membri del gruppo RTCUniversalServerAdmins di eseguire il cmdlet Enable-CsTopology. Per questo motivo, per impostazione predefinita è necessario essere amministratori di dominio per abilitare una topologia. Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di abilitare una topologia, è necessario eseguire il cmdlet Grant-CsSetupPermissions. Inoltre, è necessario eseguire questo cmdlet su ogni contenitore di Active Directory che ospita i computer che eseguono Lync Server.

Questo cmdlet concede esclusivamente le autorizzazioni al gruppo RTCUniversalServerAdmins; non può essere utilizzato per concedere le autorizzazioni ad altri gruppi di sicurezza o a singoli utenti.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> è il cmdlet Key che consente ai membri del gruppo RTCUniversalServerAdmins di configurare e distribuire Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Per aggiungere la possibilità di eseguire Enable-CsTopology al gruppo RTCUniversalServerAdmins

1.  Accedere a un server come membro del gruppo Domain Admins per il dominio in cui l'utente delegato verrà eseguito **Enable-CsTopology**.

2.  Aprire Lync Server 2013 Management Shell. Lync Server 2013 Management Shell viene installato automaticamente in ogni Front End Server o in qualsiasi computer in cui sono stati installati gli strumenti di amministrazione di Lync Server 2013. Per informazioni dettagliate su Lync Server 2013 Management Shell, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) nella documentazione relativa alle operazioni.

3.  Eseguire il cmdlet seguente da Lync Server 2013 Management Shell:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Se l'unità organizzativa non è di livello principale, è necessario specificare il nome di dominio completo.

    
    </div>
    
    Nell'esempio seguente l'unità organizzativa è "Lync Server", che si trova nel dominio contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

