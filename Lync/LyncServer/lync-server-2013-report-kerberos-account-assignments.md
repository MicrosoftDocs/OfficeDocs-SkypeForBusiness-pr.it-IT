---
title: 'Lync Server 2013: segnalare le assegnazioni degli account Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f44f187b751ec9baa78df8890e64332070d8b33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Segnalare le assegnazioni degli account Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-01-16_

Per eseguire correttamente questa procedura, è necessario essere connessi come utenti membri del gruppo RTCUniversalServerAdmins.

È possibile utilizzare il cmdlet **Get-CsKerberosAccountAssignment** per richiedere informazioni sulle assegnazioni di account di autenticazione Kerberos e restituire informazioni sulle assegnazioni correnti nella distribuzione.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Per recuperare le assegnazioni di account di autenticazione Kerberos per un sito

1.  Come membri del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in esecuzione Lync Server 2013 o a un computer in cui sono installati gli strumenti di amministrazione.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire uno dei comandi seguenti dalla riga di comando:
    
      - Per recuperare tutte le assegnazioni di account di autenticazione Kerberos nell'organizzazione e restituire informazioni sulle assegnazioni per ognuna, eseguire il cmdlet senza parametri:
        
            Get-CsKerberosAccountAssignment
    
      - Per recuperare tutte le assegnazioni di account di autenticazione Kerberos nella distribuzione e restituire informazioni sulle assegnazioni del sito per ognuna, eseguire il cmdlet con il parametro Identity:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Ad esempio:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Per recuperare tutte le assegnazioni di account di autenticazione Kerberos in un singolo sito e restituire informazioni sulle assegnazioni per ognuna, eseguire il cmdlet con il parametro Filter:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Ad esempio:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Se si specifica *NomeSito per il parametro Filter vengono restituite informazioni su tutti i siti che contengono il nome di sito specificato in qualsiasi posizione nell'identificatore di sito (ad esempio, tutti i siti che contengono la stringa Redmond nell'identificatore di sito).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

