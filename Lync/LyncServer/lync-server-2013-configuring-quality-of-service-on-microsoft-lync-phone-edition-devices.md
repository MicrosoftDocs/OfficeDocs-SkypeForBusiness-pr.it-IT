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
ms.openlocfilehash: aa8068b69afa3e02a5634041c61be6f7711e8f30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Sebbene la qualità del servizio (QoS) non sia abilitata per impostazione predefinita per i dispositivi come gli iPhone, QoS è abilitata per impostazione predefinita per i dispositivi in cui è in uso Lync Phone Edition. Questi dispositivi sono comunemente definiti telefoni UC o Unified Communication. Per verificare questo, eseguire il comando di Windows PowerShell seguente dall'interno di Lync Server Management Shell:

    Get-CsUCPhoneConfiguration

Se non sono state apportate modifiche alle impostazioni di configurazione del telefono UC, verranno restituite le informazioni che hanno un aspetto simile al seguente:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Per la qualità dei servizi, è interessante solo una di queste proprietà: VoiceDiffServTag. VoiceDiffServTag rappresenta il valore DSCP assegnato al traffico vocale proveniente da un dispositivo Lync Phone Edition.

<div>


> [!NOTE]
> Il parametro Voice8021p non è più supportato in Lync Server 2013. Il parametro è ancora valido per la compatibilità con le versioni precedenti di Microsoft Lync Server 2010; Tuttavia, non ha alcun effetto sui dispositivi usati con Lync Server 2013.



</div>

Nella maggior parte delle reti, la marcatura dei pacchetti di Lync Phone Edition con una VoiceDiffServTag di 40 non deve causare problemi. Tuttavia 40 non è il valore normalmente usato per il traffico audio, che in genere è contrassegnato dal codice DSCP 46. Per mantenere la coerenza in tutta la rete, è consigliabile modificare la proprietà VoiceDiffServTag dei telefoni UC in 46.

A questo scopo, puoi usare Windows PowerShell o il pannello di controllo di Lync Server. Per modificare il valore di VoiceDiffServTag con Windows PowerShell, eseguire il comando seguente da Lync Server Management Shell:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Il comando precedente modifica la raccolta globale delle impostazioni di configurazione del telefono UC. Tieni presente, tuttavia, che le impostazioni del telefono UC possono essere assegnate anche all'ambito del sito. Per modificare le impostazioni di configurazione del telefono UC nell'ambito del sito, è necessario specificare l'identità del sito. Ad esempio:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

È anche possibile usare il comando seguente per modificare contemporaneamente tutte le impostazioni di configurazione del telefono UC:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Se si preferisce apportare questa modifica usando il pannello di controllo di Lync Server, avviare il pannello di controllo e quindi completare la procedura seguente:

1.  Fare clic su **client** e quindi su **Configurazione dispositivo**.

2.  Nella scheda **Configurazione dispositivo** fare doppio clic sulla raccolta di impostazioni che si desidera modificare, ad esempio **globale**.

3.  Nella finestra di dialogo **modifica configurazione dispositivo** impostare il valore della casella **qualità vocale del servizio (QoS)** su **46** e quindi fare clic su **commit**.

Se si hanno più raccolte, sarà necessario ripetere questa procedura per ogni raccolta di impostazioni del telefono UC. Il pannello di controllo di Lync Server non consente di modificare contemporaneamente più insiemi di impostazioni.

Se si hanno dispositivi che non sono basati sul sistema operativo Windows (ad esempio iPhone) nell'organizzazione, questi dispositivi non saranno interessati modificando l'impostazione VoiceDiffServTag. Se si vogliono modificare i valori di DSCP in questi dispositivi, è necessario fare riferimento al manuale di amministrazione per ogni tipo di dispositivo.

</div>

<span> </span>

</div>

</div>

</div>

