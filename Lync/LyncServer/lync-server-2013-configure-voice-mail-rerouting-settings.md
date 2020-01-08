---
title: 'Lync Server 2013: Configurare le impostazioni di rerouting della segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Configurare le impostazioni di rerouting della segreteria telefonica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

I Survivable Branch Appliances e i Survivable Branch Server possono consentire la sopravvivenza della segreteria telefonica per gli utenti di Branch durante un'interruzione WAN, se la messaggistica unificata di Exchange viene installata presso il sito centrale e viene distribuito un operatore automatico di messaggistica unificata di Exchange (AA). È consigliabile che l'amministratore di Exchange configuri l'AA per accettare solo i messaggi, che Disabilita altre funzionalità generiche, ad esempio il trasferimento a un utente o il trasferimento a un operatore. In alternativa, è possibile usare un generico AA o un AA personalizzato per instradare la chiamata.

Per informazioni dettagliate, vedere la sezione "preparazione per la sopravvivenza della segreteria telefonica" dei [requisiti di resilienza del sito filiale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="to-configure-voice-mail-survivability"></a>Per configurare la sopravvivenza della segreteria telefonica

1.  Chiedere all'amministratore di Exchange di configurare l'AA solo per accettare i messaggi (nella shell di Exchange utilizzare il cmdlet seguente: **set \<-UMAutoAttendant\> AA Name-CallSomeoneEnabled $false**. Il parametro che specifica di consentire l'uscita dei messaggi (*SendVoiceMsgEnabled*) è true per impostazione predefinita.

2.  In Lync Server Management Shell utilizzare il cmdlet **New-CsVoicemailReroutingConfiguration** per impostare il numero di telefono AA come numero di telefono dell'operatore automatico di messaggistica unificata di Exchange nella configurazione di reindirizzamento della segreteria telefonica in Survivable Branch Appliance o Survivable Branch Server.
    
    <div>
    

    > [!NOTE]  
    > Se è necessario modificare l'impostazione di reinstradamento della segreteria telefonica in un secondo momento, usare il cmdlet <STRONG>Set-CsVoicemailReroutingConfiguration</STRONG> per eseguire questa operazione. Per informazioni dettagliate, informazioni su <STRONG>New</STRONG> e <STRONG>Set-CsVoicemailReroutingConfiguration</STRONG>, negli argomenti della Guida di Shell.

    
    </div>

3.  Impostare il numero di accesso abbonato alla messaggistica UNIFICAta di Exchange che corrisponde al dial plan di messaggistica unificata di Exchange dell'utente della filiale come numero di accesso del Sottoscrittore di Exchange UM nella configurazione di reindirizzamento della segreteria telefonica in Survivable Branch Appliance o Survivable Branch Server.
    
    <div>
    

    > [!NOTE]  
    > Configurare il dial plan degli utenti di Exchange UM in modo che sia presente un solo dial plan associato a tutti gli utenti della filiale che hanno bisogno di accedere alla funzionalità Get Voice mail durante un'interruzione WAN.

    
    </div>

**Passaggio successivo** per Survivable Branch Appliances o Survivable Branch Servers: [utenti privati in un Survivable Branch Appliance o server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

