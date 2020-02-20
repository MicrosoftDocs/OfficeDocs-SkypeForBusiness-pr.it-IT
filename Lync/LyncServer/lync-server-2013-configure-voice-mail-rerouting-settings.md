---
title: 'Lync Server 2013: configurare le impostazioni di reinstradamento della segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38818a6514d4d7bce5266df57347415a600a28c8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Configurare le impostazioni di reinstradamento della segreteria telefonica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

Survivable Branch Appliance e Survivable Branch Server sono in grado di garantire la sopravvivenza dei messaggi vocali per gli utenti di succursali durante un'interruzione della rete WAN, se la messaggistica unificata di Exchange è installata nel sito centrale e viene distribuito un operatore automatico di messaggistica unificata di Exchange. È opportuno che l'amministratore di Exchange configuri l'Operatore automatico in modo che accetti solo i messaggi, disabilitando altre funzionalità generiche come il trasferimento a un utente o a un operatore. In alternativa, è possibile utilizzare un Operatore automatico generico o personalizzato per il routing della chiamata.

Per informazioni dettagliate, vedere la sezione relativa alla preparazione per la sopravvivenza dei messaggi vocali [per i requisiti di resilienza del sito di succursale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="to-configure-voice-mail-survivability"></a>Per configurare il funzionamento ininterrotto della segreteria telefonica

1.  Chiedere all'amministratore di Exchange di configurare l'AA per accettare solo i messaggi (nella shell di Exchange utilizzare il cmdlet seguente: **set \<-UMAutoAttendant\> AA Name-CallSomeoneEnabled $false**. Il parametro che consente di specificare se consentire la visualizzazione di messaggi (*SendVoiceMsgEnabled*) viene impostato su true per impostazione predefinita.

2.  In Lync Server Management Shell, utilizzare il cmdlet **New-CsVoicemailReroutingConfiguration** per impostare il numero di telefono dell'operatore automatico di messaggistica unificata di Exchange nella configurazione di reinstradamento della segreteria telefonica nel Survivable Branch Appliance o Survivable Branch Server.
    
    <div>
    

    > [!NOTE]  
    > Se in seguito sarà necessario modificare l'impostazione di rerouting della segreteria telefonica, utilizzare il cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> a tale scopo. Per informazioni dettagliate su <STRONG>New-</STRONG>, vedere <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> negli argomenti della Guida della shell.

    
    </div>

3.  Impostare il numero di accesso sottoscrittore Messaggistica unificata di Exchange corrispondente al dial plan di messaggistica unificata di Exchange dell'utente di succursale come numero di accesso sottoscrittore Messaggistica unificata di Exchange nella configurazione di reinstradamento della segreteria telefonica nel Survivable Branch Appliance o Survivable Branch Server
    
    <div>
    

    > [!NOTE]  
    > Configurare il dial plan degli utenti di messaggistica unificata di Exchange in modo che sia presente un solo dial plan associato a tutti gli utenti di succursale che hanno necessità di accedere alla funzionalità di ricezione della posta vocale durante un'interruzione della rete WAN.

    
    </div>

**Passaggio successivo** per Survivable Branch Appliance o Survivable Branch Server: [Home Users on a Survivable Branch Appliance or server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

