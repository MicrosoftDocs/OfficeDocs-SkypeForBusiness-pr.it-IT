---
title: 'Lync Server 2013: Delegare le autorizzazioni di installazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7df00740ac971fd56e289da04ca43abb1619329
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a>Delegare le autorizzazioni di installazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Se non si vuole concedere l'appartenenza al gruppo Domain Admins agli utenti o ai gruppi che distribuiscono Lync Server 2013, è possibile abilitare i membri del gruppo RTCUniversalServerAdmins per eseguire il cmdlet di Windows PowerShell **Enable-CsTopology** nei server che eseguono Lync Server 2013. Per impostazione predefinita, i membri del gruppo RTCUniversalServerAdmins non hanno la possibilità di eseguire questo cmdlet. I diritti di amministratore e le autorizzazioni per l'esecuzione di **Enable-CsTopology** nei server che eseguono Lync Server vengono concessi tramite il cmdlet **Grant-CsSetupPermission** e specificando un'unità organizzativa in cui si trovano gli oggetti computer per il server in cui è in esecuzione Lync Server 2013.

La preparazione del dominio che viene eseguita quando si installa Lync Server non aggiunge automaticamente le autorizzazioni che consentono ai membri del gruppo RTCUniversalServerAdmins di eseguire il cmdlet Enable-CsTopology. Ciò significa che, per impostazione predefinita, è necessario essere un amministratore di dominio per abilitare una topologia. Per assegnare ai membri del gruppo RTCUniversalServerAdmins il diritto di abilitare una topologia, è necessario eseguire il cmdlet Grant-CsSetupPermissions. Sarà inoltre necessario eseguire questo cmdlet in ogni contenitore di Active Directory che ospita i computer che eseguono Lync Server.

Tieni presente che questo cmdlet concede solo le autorizzazioni per il gruppo RTCUniversalServerAdmins; il cmdlet non può essere usato per concedere autorizzazioni ad altri gruppi di sicurezza o a singoli utenti.

<div>


> [!NOTE]  
> <STRONG>Enable-CsTopology</STRONG> è il cmdlet Key che consente ai membri del gruppo RTCUniversalServerAdmins di configurare e distribuire Lync Server 2013.



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a>Per aggiungere la possibilità di eseguire Enable-CsTopology al gruppo RTCUniversalServerAdmins

1.  Accedere a un server come membro del gruppo Domain Admins per il dominio in cui l'utente delegato eseguirà **Enable-CsTopology**.

2.  Aprire Lync Server 2013 Management Shell. Lync Server 2013 Management Shell viene installato automaticamente in ogni server front-end o in qualsiasi computer in cui sono stati installati gli strumenti di amministrazione di Lync Server 2013. Per informazioni dettagliate su Lync Server 2013 Management Shell, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) nella documentazione Operations.

3.  Eseguire il cmdlet seguente da Lync Server 2013 Management Shell:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > Se l'unità organizzativa non è di primo livello, è necessario specificare il nome di dominio completo.

    
    </div>
    
    Nell'esempio seguente l'unità organizzativa è "Lync Servers", che si trova nel dominio contoso.com.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

