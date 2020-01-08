---
title: 'Lync Server 2013: Generare un rapporto sulle assegnazioni degli account Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Generare un rapporto sulle assegnazioni degli account Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-01-16_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.

Puoi usare il cmdlet **Get-CsKerberosAccountAssignment** per eseguire query sulle assegnazioni degli account di autenticazione Kerberos e segnalare informazioni sulle assegnazioni correnti nella distribuzione.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Per eseguire query sulle assegnazioni degli account di autenticazione Kerberos per un sito

1.  Come membro del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in uso Lync Server 2013 o in un computer in cui sono installati gli strumenti di amministrazione.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando eseguire uno dei comandi seguenti:
    
      - Per eseguire query su tutte le assegnazioni degli account di autenticazione Kerberos nell'organizzazione e restituire informazioni sulle assegnazioni su ognuno di essi, Esegui il cmdlet senza parametri:
        
            Get-CsKerberosAccountAssignment
    
      - Per eseguire query su tutte le assegnazioni degli account di autenticazione Kerberos nella distribuzione e restituire informazioni sulle assegnazioni del sito su ognuna di esse, Esegui il cmdlet con il parametro Identity:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Ad esempio:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Per eseguire query su tutte le assegnazioni degli account di autenticazione Kerberos in un singolo sito e restituire informazioni sulle assegnazioni su ognuna di esse, Esegui il cmdlet con il parametro Filter:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Ad esempio:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Specificando * nomesito per il parametro Filter vengono restituite informazioni su tutti i siti che contengono il nome del sito specificato in un punto qualsiasi dell'identificatore del sito, ad esempio tutti i siti che contengono la stringa Redmond nell'identificatore del sito.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

