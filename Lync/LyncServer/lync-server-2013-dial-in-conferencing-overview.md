---
title: Panoramica delle conferenze telefoniche con accesso esterno di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 820c880d44a1ecede139a8d3caddf3f6c40e65a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a>Panoramica dei servizi di conferenza telefonica con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-30_

Se l'organizzazione dispone di utenti che devono partecipare a conferenze locali di Lync Server 2013 quando si trovano fuori sede o non hanno accesso a un computer, è possibile distribuire i servizi di conferenza telefonica con chiamata in modo che possano partecipare alla conferenza usando un telefono pubblico con commutazioni telefono di rete (PSTN).

I servizi di conferenza telefonica con accesso esterno sono una funzionalità facoltativa che è possibile configurare quando si distribuisce una conferenza di Lync Server 2013. Anche se i servizi di conferenza telefonica con accesso esterno usano alcuni degli stessi componenti di Lync Server 2013 usati da Enterprise Voice, è possibile distribuire i servizi di conferenza telefonica con accesso esterno anche se non si distribuisce VoIP aziendale.

<div>


> [!NOTE]  
> Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario distribuirla in tutti i pool in cui si distribuiscono le conferenze di Lync Server 2013. Non è necessario assegnare i numeri di accesso in tutti i pool, ma è necessario distribuire la caratteristica chiamata in ingresso in ogni pool. Questo requisito supporta la caratteristica nome registrato quando un utente chiama un numero di accesso da un pool per partecipare a una conferenza di Lync Server 2013 in un pool diverso.



</div>

Le conferenze devono essere abilitate per l'accesso esterno in criteri riunione. Per impostazione predefinita, le conferenze abilitate per l'accesso esterno includono le informazioni seguenti nell'invito alla conferenza:

  - ID conferenza numerico che identifica la conferenza.

  - Uno o più numeri di accesso PSTN.

  - Un collegamento a una pagina delle impostazioni di conferenza telefonica con accesso esterno, che contiene un elenco completo dei numeri di Access con le lingue associate; una posizione per creare, reimpostare o sbloccare i numeri di identificazione personali (pin); e altre informazioni, ad esempio i controlli DTMF (Dual-Tone Multi-Frequency).

I servizi di conferenza telefonica con accesso esterno supportano utenti Enterprise e Anonymous. Gli utenti aziendali hanno le credenziali dei servizi di dominio Active Directory e gli account di Lync Server 2013 all'interno dell'organizzazione. Gli utenti anonimi non hanno credenziali aziendali all'interno dell'organizzazione. Nel contesto dei servizi di conferenza telefonica con accesso esterno, un utente dell'organizzazione di un partner federato che usa la rete PSTN per connettersi a una conferenza viene considerato come un utente anonimo. Per i servizi di conferenza telefonica con accesso esterno, a differenza di altri contesti, gli utenti federati non vengono autenticati.

Gli utenti aziendali o i responsabili delle conferenze che partecipano a una conferenza abilitata per la chiamata in accesso esterno compongono uno dei numeri di accesso alla conferenza e quindi viene richiesto di immettere l'ID conferenza. Se una direttrice non è ancora entrata nella riunione, gli utenti possono immettere l'estensione UC (Unified Communications) o il numero di telefono completo e aggiungere o aspettare di essere ammessi da una direttrice. L'organizzatore della riunione può partecipare alla riunione come leader immettendo solo il PIN. Il server front-end usa la combinazione di numero di telefono completo o estensione e PIN per associare gli utenti aziendali in modo univoco alle credenziali di Active Directory. Di conseguenza, gli utenti dell'organizzazione vengono autenticati e identificati per nome nella conferenza. Gli utenti aziendali possono anche assumere un ruolo di conferenza predefinito dall'organizzatore.

<div>


> [!NOTE]  
> Gli utenti aziendali che effettuano la chiamata da un telefono Office IP o da Lync Server 2013 o Lync 2010 Attendant non vengono richiesti per il proprio numero di telefono perché sono già autenticati.



</div>

Utenti anonimi che desiderano partecipare a una conferenza telefonica con accesso esterno, digitare un numero di Access per le conferenze e quindi viene richiesto di immettere l'ID conferenza. Anche agli utenti anonimi non autenticati viene richiesto di registrare il proprio nome. Il nome registrato identifica gli utenti non autenticati nella conferenza. Gli utenti anonimi non sono ammessi alla conferenza fino a quando almeno un leader o un utente autenticato non partecipa e non è possibile assegnare loro un ruolo predefinito.

<div>


> [!NOTE]  
> Gli utenti aziendali che scelgono di non immettere il proprio numero di telefono e il PIN non vengono autenticati. Viene richiesto di registrare il proprio nome e di essere trattati come utenti anonimi nella conferenza.



</div>

In fase di pianificazione, l'organizzatore della riunione può scegliere di limitare l'accesso alla riunione rendendo la riunione chiusa o bloccata. In questo caso, gli utenti con accesso esterno vengono richiesti per l'autenticazione. Se gli utenti con accesso esterno non riescono o scelgono di non eseguire l'autenticazione, vengono trasferiti nella sala di attesa. Attendono nella sala di attesa fino a quando un leader non li accetta o li rifiuta oppure viene disconnesso. Gli utenti con accesso esterno sentono la musica se sono in attesa di essere ammessi alla conferenza. Dopo l'ammissione a una conferenza, gli utenti con accesso esterno possono partecipare alla parte audio della conferenza e possono esercitare i comandi DTMF (Dual-Tone Multi-Frequency) usando la tastiera del telefono. I responsabili delle connessioni telefoniche con accesso esterno possono esercitare i comandi DTMF per attivare o disattivare l'attivazione o disattivazione dei partecipanti, bloccare o sbloccare la conferenza, ammettere gli utenti nella sala di attesa e attivare o disattivare gli annunci di entrata e uscita. I responsabili possono anche usare un comando DTMF per ammettere tutti gli utenti della sala di attesa, che modificano le autorizzazioni della riunione per consentire a tutti i partecipanti di accedervi. Tutti i partecipanti alla chiamata in accesso esterno possono esercitare i comandi DTMF per ascoltare la guida, ascoltare il roster della conferenza e disattivare l'audio.

Partecipanti con accesso esterno (ovvero, indipendentemente dal fatto che abbiano o meno la chiamata dalla rete PSTN), ascoltare annunci personali durante la conferenza, ad esempio se sono stati riattivati o disattivati, la riunione è stata registrata o qualcuno sta aspettando nella sala di attesa.

<div>


> [!NOTE]  
> Partecipanti che partecipano alla conferenza facendo clic su un collegamento invece di effettuare la chiamata in non si sentono annunci personali.



</div>

</div>

<span> </span>

</div>

</div>

</div>

