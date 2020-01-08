---
title: 'Lync Server 2013: Gestione di oggetti contatto di Exchange ospitati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c67438745ee7cbb9de0ccfdef1d5d8959bb4679c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Gestione di oggetti contatto di Exchange ospitati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-25_

È necessario configurare un oggetto contatto per ogni numero di operatore automatico e numero di accesso del Sottoscrittore nella distribuzione tra più locali.

Per l'integrazione con la messaggistica unificata di Exchange ospitata, OcsUmUtil. exe non può essere usato per gestire gli oggetti contatto, perché dipende dalle impostazioni della messaggistica unificata di Exchange in Active Directory. In una distribuzione interlocale Lync Server 2013 e la messaggistica unificata di Exchange ospitati vengono installati in foreste separate senza attendibilità. Per motivi di sicurezza, gli amministratori di Lync Server 2013 non hanno accesso diretto alle impostazioni di Active Directory UM di Exchange. Di conseguenza, Lync Server 2013 offre un modello diverso per la gestione degli oggetti contatto in uno *spazio di indirizzi SIP condiviso* accessibile sia a lync Server 2013 che al servizio di messaggistica unificata di Exchange ospitati.

<div>

## <a name="hosted-contact-object-workflow"></a>Flusso di lavoro di oggetti contatto ospitati

Di seguito sono riportate le procedure generali per l'uso dell'amministratore del tenant ospitante di Exchange per la gestione degli oggetti contatto:

1.  L'amministratore di Exchange richiede i numeri di telefono per gli oggetti contatto di messaggistica unificata di Exchange e l'operatore automatico.

2.  L'amministratore di Lync Server 2013 crea un oggetto contatto per ogni numero di telefono e assegna un criterio di segreteria telefonica ospitata a ogni oggetto contatto.

3.  L'amministratore di Lync Server 2013 fornisce i numeri di telefono all'amministratore di Exchange.

4.  L'amministratore di Exchange assegna i numeri di telefono ai dial plan di messaggistica unificata di Exchange appropriati per gli operatori automatici e l'accesso sottoscrittore.

<div>


> [!NOTE]  
> Non è necessario configurare le impostazioni di dial plan di Lync Server 2013 sugli oggetti contatto in quanto esiste con distribuzioni locali.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Configurazione di oggetti contatto ospitati

<div>


> [!NOTE]  
> Prima che gli oggetti contatto di Lync Server 2013 possano essere abilitati per la messaggistica unificata di Exchange ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata. Il criterio può essere di ambito globale, a livello di sito o per utente, purché si applichi all'oggetto contatto che si vuole abilitare. Per informazioni dettagliate, vedere Criteri per la segreteria <A href="lync-server-2013-hosted-voice-mail-policies.md">telefonica ospitati in Lync Server 2013</A>.



</div>

Per configurare gli oggetti di contatto per l'operatore automatico ospitati e i contatti degli abbonati in una distribuzione tra più locali, è necessario usare i cmdlet seguenti:

  - **New-CsExUmContact** crea un nuovo oggetto contatto per la messaggistica unificata ospitata.

  - **Set-CsExUmContact** modifica un oggetto contatto esistente per la messaggistica unificata di Exchange ospitata.

L'esempio seguente crea un oggetto contatto di operatore automatico:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Questo esempio crea un nuovo oggetto contatto di messaggistica unificata di Exchange con l'indirizzo SIP sip:exumaa1@fabrikam.com. Il nome del pool in cui è in uso il servizio di registrazione di Lync Server 2013 è RedmondPool.litwareinc.com. L'unità organizzativa di Active Directory in cui verranno archiviate le informazioni è OU = ExUmContacts, DC = litwareinc, DC = com. Il numero di telefono dell'oggetto contatto è 2065554567. Il parametro facoltativo-AutoAttendant $True specifica che questo oggetto è un oggetto contatto di operatore automatico. L'impostazione del parametro-AutoAttendant su false (impostazione predefinita) specifica un oggetto contatto di accesso del Sottoscrittore.

Per informazioni dettagliate sui cmdlet New-CsExUmContact e Set-CsExUmContact, vedere la documentazione di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

