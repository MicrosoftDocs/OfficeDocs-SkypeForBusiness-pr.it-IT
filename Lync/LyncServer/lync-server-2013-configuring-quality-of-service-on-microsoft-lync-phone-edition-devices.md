---
title: Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c69bf438965c536a3ba424699a7109308368397
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534963"
---
# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Anche se la qualità del servizio (QoS) non è abilitata per impostazione predefinita per i dispositivi come iPhone, QoS è abilitata per impostazione predefinita per i dispositivi che eseguono Lync Phone Edition. Questi dispositivi sono comunemente denominati telefoni di comunicazione unificati o UC. Per verificarlo, eseguire il comando di Windows PowerShell seguente dall'interno di Lync Server Management Shell:

    Get-CsUCPhoneConfiguration

Se non sono state apportate modifiche alle impostazioni di configurazione dei telefoni UC, verranno restituite informazioni simili alle seguenti:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Per motivi di qualità del servizio, è interessante solo una delle proprietà seguenti: VoiceDiffServTag. VoiceDiffServTag rappresenta il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Lync Phone Edition.

<div>


> [!NOTE]
> Il parametro Voice8021p non è più supportato in Lync Server 2013. Il parametro è ancora valido per la compatibilità con le versioni precedenti di Microsoft Lync Server 2010; Tuttavia, non ha alcun effetto sui dispositivi utilizzati con Lync Server 2013.



</div>

Nella maggior parte delle reti, la marcatura dei pacchetti di Lync Phone Edition con una VoiceDiffServTag di 40 non deve causare problemi. 40 non è tuttavia il valore utilizzato comunemente per il traffico audio, che invece è quasi sempre contrassegnato con il codice DSCP 46. Per mantenere la coerenza all'interno della rete, è possibile modificare la proprietà VoiceDiffServTag dei telefoni UC impostandola su 46.

A tale scopo, è possibile utilizzare Windows PowerShell o il pannello di controllo di Lync Server. Per modificare il valore VoiceDiffServTag tramite Windows PowerShell, eseguire il comando riportato di seguito dall'interno di Lync Server Management Shell:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Il comando precedente modifica la raccolta globale delle impostazioni di configurazione dei telefoni UC. Tali impostazioni possono tuttavia essere assegnate anche all'ambito del sito. Per modificare le impostazioni di configurazione dei telefoni UC nell'ambito del sito, è necessario specificare l'identità (Identity) del sito. Ad esempio:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

È inoltre possibile utilizzare il comando seguente per modificare contemporaneamente tutte le impostazioni di configurazione dei telefoni UC:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Se si preferisce apportare questa modifica utilizzando il pannello di controllo di Lync Server, avviare il pannello di controllo e quindi completare la procedura seguente:

1.  Fare clic su **Client** e quindi su **Configurazione dispositivo**.

2.  Nella scheda **Configurazione dispositivo** fare doppio clic sulla raccolta di impostazioni che si desidera modificare, ad esempio **Globale**.

3.  Nella finestra di dialogo **Modifica configurazione dispositivo** impostare il valore della casella **Qualità vocale servizio (QoS)** su **46** e quindi fare clic su **Commit**.

Se si dispone di più raccolte, sarà necessario ripetere questo processo per ogni raccolta di impostazioni per i telefoni UC. Il pannello di controllo di Lync Server non consentirà di modificare contemporaneamente più insiemi di impostazioni.

Se si dispone di dispositivi non basati sul sistema operativo Windows, come nel caso di iPhone, nell'organizzazione la modifica dell'impostazione VoiceDiffServTag non inciderà su questi dispositivi. Se si desidera modificare i valori DSCP su tali dispositivi, sarà necessario fare riferimento al manuale dell'amministratore per ogni tipo di dispositivo.

</div>

<span> </span>

</div>

</div>

</div>

