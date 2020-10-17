---
title: Panoramica delle conferenze telefoniche con accesso esterno di Lync Server 2013
description: Panoramica delle conferenze telefoniche con accesso esterno di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa9418c13b56faab747d2c92df3301fe15d722eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549482"
---
# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Panoramica delle conferenze telefoniche con accesso esterno in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-30_

Se nell'organizzazione sono presenti utenti che devono partecipare a conferenze locali di Lync Server 2013 quando sono fuori sede o che non dispongono dell'accesso a un computer, è possibile distribuire le conferenze telefoniche in ingresso in modo che possano partecipare alla conferenza utilizzando un telefono PSTN (Public Switched Telephone Network).

Le conferenze telefoniche con accesso esterno sono una funzionalità facoltativa che è possibile configurare quando si distribuisce Lync Server 2013 Conferencing. Anche se la conferenza telefonica con accesso esterno utilizza alcuni degli stessi componenti di Lync Server 2013 utilizzati da VoIP aziendale, è possibile distribuire le conferenze telefoniche con accesso esterno anche se non si esegue la distribuzione di VoIP aziendale.

<div>


> [!NOTE]  
> Se si distribuiscono le conferenze telefoniche con accesso esterno, è necessario distribuirle in tutti i pool in cui si distribuisce Lync Server 2013 Conferencing. Non è necessario assegnare i numeri di accesso in ogni pool, ma è necessario distribuire la funzionalità di chiamata in ingresso in ogni pool. Questo requisito supporta la caratteristica del nome registrato quando un utente chiama un numero di accesso da un pool per partecipare a una conferenza di Lync Server 2013 in un pool diverso.



</div>

È necessario abilitare le conferenze per l'accesso esterno tramite criteri di riunione. Per impostazione predefinita, le conferenze abilitate per l'accesso esterno includono le informazioni seguenti nell'invito alla conferenza:

  - ID conferenza numerico che identifica la conferenza.

  - Uno o più numeri di accesso PSTN.

  - Un collegamento a una pagina delle impostazioni per le conferenze telefoniche con accesso esterno, che contiene un elenco completo dei numeri di accessi con le rispettive lingue associate. un luogo in cui creare, reimpostare o sbloccare i numeri di identificazione personale (pin); e altre informazioni, ad esempio i controlli DTMF (Dual-Tone Multi-Frequency).

Le conferenze telefoniche con accesso esterno supportano utenti sia aziendali sia anonimi. Gli utenti aziendali dispongono di credenziali di servizi di dominio Active Directory e di account Lync Server 2013 all'interno dell'organizzazione. Gli utenti anonimi non dispongono di credenziali aziendali all'interno dell'organizzazione. Nel contesto delle conferenze telefoniche con accesso esterno un utente in un'organizzazione di un partner federato che utilizza la rete PSTN per connettersi a una conferenza viene considerato un utente anonimo. Per le conferenze telefoniche con accesso esterno, diversamente da altri contesti, gli utenti federati non vengono autenticati.

Gli utenti aziendali o i coordinatori delle conferenze che partecipano a una conferenza abilitata per l'accesso esterno compongono uno dei numeri di accesso alla conferenza e devono immettere l'ID conferenza. Se un coordinatore non ha ancora eseguito l'accesso alla riunione, gli utenti possono immettere il proprio interno (o il numero di telefono completo) per le comunicazioni unificate e il PIN o attendere di essere ammessi da un coordinatore. Gli organizzatori della riunione possono partecipare alla riunione come coordinatori semplicemente immettendo il proprio PIN. Il front end server utilizza la combinazione di numero di telefono completo o interno e il PIN, per mappare in modo univoco gli utenti aziendali alle credenziali di Active Directory. Di conseguenza, gli utenti aziendali vengono autenticati e identificati in base al nome nella conferenza. Gli utenti aziendali possono anche assumere un ruolo della conferenza predefinito dall'organizzatore.

<div>


> [!NOTE]  
> Gli utenti aziendali che effettuano la chiamata da un telefono IP di Office o da un operatore Lync Server 2013 o Lync 2010 non vengono richiesti per il proprio numero di telefono perché sono già autenticati.



</div>

Gli utenti anonimi che desiderano partecipare a una conferenza telefonica con accesso esterno compongono uno dei numeri di accesso alla conferenza e devono quindi immettere il proprio ID conferenza. Gli utenti anonimi non autenticati devono inoltre registrare il proprio nome. Il nome registrato identifica gli utenti non autenticati nella conferenza. Gli utenti anonimi non vengono ammessi alla conferenza fino a quando un responsabile o un utente autenticato non accede, e non possono ricevere un ruolo predefinito.

<div>


> [!NOTE]  
> Gli utenti aziendali che scelgono di non immettere il proprio numero di telefono e il PIN non vengono autenticati e pertanto devono registrare il proprio nome e vengono considerati utenti anonimi nella conferenza.



</div>

In fase di pianificazione, l'organizzatore della riunione può scegliere di limitare l'accesso alla riunione chiudendola o bloccandola. In questo caso, agli utenti connessi tramite chiamata in ingresso viene richiesto di eseguire l'autenticazione. Se gli utenti riescono ad autenticarsi o scelgono di non farlo, vengono trasferiti alla pagina di benvenuto, in cui attendono fino a quando un responsabile non li accetta o rifiuta o, in caso di timeout, non vengono disconnessi. Gli utenti connessi tramite chiamata in ingresso ascoltano un brano musicale se devono attendere di essere ammessi alla conferenza. Una volta ammessi alla conferenza, tali utenti possono partecipare alla parte audio della conferenza e utilizzare i comandi DTMF dal tastierino del telefono. I responsabili connessi tramite chiamata in ingresso possono utilizzare i comandi DTMF per consentire o meno ai partecipanti di disattivare il proprio audio, bloccare o sbloccare la conferenza, ammettere altre persone dalla pagina di benvenuto e attivare o disattivare gli annunci di entrata o uscita. I responsabili possono inoltre utilizzare un comando DTMF per ammettere chiunque dalla pagina di benvenuto, scelta che comporta la modifica delle autorizzazioni della riunione in modo da ammettere chiunque acceda successivamente. Tutti i partecipanti connessi tramite chiamata in ingresso possono utilizzare i comandi DTMF per ascoltare la Guida e l'elenco dei partecipanti e disattivare il proprio audio.

I partecipanti connessi tramite chiamata in ingresso, che chiamino o meno dalla rete PSTN, possono ascoltare annunci personali durante la conferenza, ad esempio relativi alla disattivazione o meno del proprio audio, alla registrazione o meno della riunione o all'eventuale presenze di altri utenti nella pagina di benvenuto.

<div>


> [!NOTE]  
> I partecipanti che accedono alla conferenza facendo clic su un collegamento invece di comporre un numero non possono ascoltare gli annunci personali.



</div>

</div>

<span> </span>

</div>

</div>

</div>

