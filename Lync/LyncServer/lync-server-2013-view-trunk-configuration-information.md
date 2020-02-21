---
title: 'Lync Server 2013: visualizzare le informazioni di configurazione del trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 102fb942397b8329da067d8c41c16ec393076a00
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Visualizzare le informazioni di configurazione del trunk in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:

  - Se abilitare il bypass multimediale nei trunk.

  - Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).

  - Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP. Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>Per visualizzare le informazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server, fare clic su **routing vocale** e quindi su **configurazione trunk**.

2.  Nella scheda **configurazione trunk** verrà visualizzato un elenco di tutte le raccolte di impostazioni di configurazione trunk; per ogni raccolta verranno visualizzati i valori per le proprietà **Name**, **scope**, **state**e **media bypass** , oltre al numero di **utilizzi PSTN**, **alle regole dei numeri di chiamata**e alle **regole dei numeri denominate** associate all'insieme. Per visualizzare ulteriori dettagli su una raccolta di impostazioni di configurazione del trunk, fare clic sulla raccolta di interesse, fare clic su **modifica**e quindi su **Mostra dettagli**. Si noti che è possibile visualizzare informazioni dettagliate solo per una raccolta di impostazioni di configurazione del trunk alla volta.

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione del trunk SIP tramite i cmdlet di Windows PowerShell

È possibile visualizzare le impostazioni di configurazione del trunk SIP utilizzando Lync Server PowerShell e il cmdlet Get-CsTrunkConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>Per visualizzare le informazioni di configurazione del trunk SIP

  - Per visualizzare informazioni su tutte le impostazioni di configurazione del trunk SIP, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsTrunkConfiguration
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

