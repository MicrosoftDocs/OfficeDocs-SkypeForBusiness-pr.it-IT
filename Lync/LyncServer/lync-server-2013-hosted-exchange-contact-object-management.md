---
title: 'Lync Server 2013: gestione di oggetti contatto di Exchange ospitati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15abe045504653fe7a64d8bc6ef82af3ac87ba37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Gestione di oggetti contatto di Exchange ospitati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-25_

È necessario configurare un oggetto contatto per ogni numero di operatore automatico e per ogni numero di accesso sottoscrittore per una distribuzione su più computer.

Per l'integrazione con la messaggistica unificata di Exchange ospitata, non è possibile utilizzare ocsumutil.exe per gestire oggetti contatto, perché questa utilità dipende dalle impostazioni di Active Directory della messaggistica unificata di Exchange. In una distribuzione cross-premise, Lync Server 2013 e la messaggistica unificata di Exchange ospitata vengono installate in foreste separate senza alcuna relazione di trust tra di essi. Per motivi di sicurezza, gli amministratori di Lync Server 2013 non dispongono di accesso diretto alle impostazioni di Active Directory di messaggistica unificata di Exchange. Di conseguenza, Lync Server 2013 fornisce un modello diverso per la gestione degli oggetti contatto in uno *spazio di indirizzi SIP condiviso* accessibile sia per lync Server 2013 che per il servizio di messaggistica unificata di Exchange ospitato.

<div>

## <a name="hosted-contact-object-workflow"></a>Flusso di lavoro degli oggetti contatto ospitati

Di seguito sono riportate le operazioni generali per collaborare con l'amministratore del tenant di Exchange condiviso nella gestione degli oggetti contatto:

1.  L'amministratore di Exchange richiede i numero di telefono per gli oggetti contatto di accesso di sottoscrittori e di operatore automatico della messaggistica unificata di Exchange.

2.  L'amministratore di Lync Server 2013 crea un oggetto contatto per ogni numero di telefono e assegna un criterio di segreteria telefonica ospitata a ogni oggetto contatto.

3.  L'amministratore di Lync Server 2013 fornisce i numeri di telefono all'amministratore di Exchange.

4.  L'amministratore di Exchange assegna i numeri di telefono ai dial plan della messaggistica unificata di Exchange per operatori automatici e per l'accesso di sottoscrittori.

<div>


> [!NOTE]  
> Non è necessario configurare le impostazioni del dial plan di Lync Server 2013 sugli oggetti contatto come nelle distribuzioni locali.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Configurazione di oggetti contatto ospitati

<div>


> [!NOTE]  
> Prima di poter abilitare gli oggetti contatto di Lync Server 2013 per la messaggistica unificata di Exchange ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata. Il criterio può essere di ambito globale, a livello di sito o per utente, purché applicato all'oggetto contatto che si desidera abilitare. Per ulteriori informazioni, vedere <A href="lync-server-2013-hosted-voice-mail-policies.md">criteri di segreteria telefonica ospitata in Lync Server 2013</A>.



</div>

Per configurare oggetti contatto di accesso dei sottoscrittori e di operatori automatici ospitati in una distribuzione tra più uffici, è necessario utilizzare i cmdlet seguenti:

  - **New-CsExUmContact** crea un nuovo oggetto contatto per la messaggistica unificata ospitata.

  - **Set-CsExUmContact** modifica un contatto oggetto esistente per la messaggistica unificata di Exchange ospitata.

Nell'esempio seguente viene creato un oggetto contatto di operatore automatico:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

In questo esempio viene creato un nuovo oggetto contatto della messaggistica unificata di Exchange, con l'indirizzo SIP sip:exumaa1@fabrikam.com. Il nome del pool in cui è in esecuzione il servizio di registrazione di Lync Server 2013 è RedmondPool.litwareinc.com. L'unità organizzativa in cui verranno archiviate queste informazioni è OU=ExUmContacts,DC=litwareinc,DC=com. Il numero di telefono dell'oggetto contatto è 2065554567. Il parametro facoltativo -AutoAttendant $True specifica che si tratta di un oggetto contatto di operatore automatico. Se il parametro -AutoAttendant è impostato su False (impostazione predefinita) specifica un oggetto contatto di accesso di sottoscrittori.

Per informazioni dettagliate sui cmdlet New-CsExUmContact e Set-CsExUmContact, vedere la documentazione di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

