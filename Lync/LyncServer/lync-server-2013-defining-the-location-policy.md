---
title: 'Lync Server 2013: definizione dei criteri di posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb7550412fa6cdcda3a8fc4dd9b7913912c34e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>Definizione dei criteri di posizione per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

Ogni criterio di posizione contiene le informazioni seguenti:

  - **Servizi di emergenza abilitati**  
    Quando questo valore è **Sì**, il client è abilitato per il E9-1-1. Quando un client esegue la registrazione, tenta di acquisire una posizione dal servizio informazioni sulla posizione e includerà le informazioni sulla posizione come parte di una chiamata di emergenza.

<!-- end list -->

  - **Posizione richiesta**  
    Questa impostazione viene usata solo quando i **servizi di emergenza abilitati** sono impostati su **Sì**.
    
    Puoi configurare l'impostazione della **posizione necessaria** per definire il comportamento del client. Impostando il valore su **No** , l'utente non verrà richiesto per una posizione. Impostando il valore su **Sì** , l'utente verrà richiesto per una posizione, ma può chiudere la richiesta. Se si imposta il valore su **Disclaimer** , l'utente verrà richiesto di ricevere una posizione e verrà visualizzata anche una dichiarazione di non responsabilità se tenta di chiudere la richiesta. In tutti i casi, l'utente può continuare a usare il client.
    
    <div>
    

    > [!NOTE]  
    > Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il E9-1-1. Gli aggiornamenti al testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità.

    
    </div>

<!-- end list -->

  - **Dichiarazione di non responsabilità avanzata del servizio di emergenza**  
    Questa impostazione specifica la dichiarazione di non responsabilità che gli utenti vedono se eliminano la richiesta di una posizione. In Lync Server 2013 è possibile usare i criteri di posizione per impostare dichiarazioni di non credito diverse per le diverse impostazioni locali o per diversi gruppi di utenti.
    
    <div>
    

    > [!NOTE]  
    > Questa impostazione dei criteri di posizione è diversa da Lync Server 2010, in cui è stato usato il cmdlet <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> per impostare una dichiarazione di non responsabilità globale per l'intera organizzazione. Se esiste già una dichiarazione di non responsabilità globale, è necessario specificare la dichiarazione di non responsabilità nei criteri di posizione. In altre condizioni, Lync Server 2013 USA solo le dichiarazioni di non attestazione specificate nei criteri di posizione.

    
    </div>

<!-- end list -->

  - **Stringa di chiamata di emergenza**  
    Questa stringa di chiamata (meno l'iniziale "+", ma anche qualsiasi normalizzazione eseguita dal dial plan dell'utente di Lync) indica che una chiamata è una chiamata di emergenza. La **stringa** di chiamata di emergenza fa sì che il client includa le informazioni sulla posizione e sulla richiamata con la chiamata.
    
    <div>
    

    > [!NOTE]  
    > Se l'organizzazione non usa un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione del dial plan corrispondente che aggiunga un "+" alla stringa 911 prima di inviare la chiamata al routing in uscita in un server di pool Lync; il valore "+" verrà anteposto automaticamente dal client Lync come risultato dei criteri di posizione. Tuttavia, se il sito usa un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione ai criteri di dial plan applicabili che allineano il prefisso di accesso esterno e aggiunge "+". Ad esempio, se la tua posizione usa un prefisso di accesso esterno di 9 e un utente compone&nbsp;9 911 per effettuare una chiamata di emergenza, il client userà i criteri per il dial plan per normalizzare il valore in + 911 prima che il numero di telefono sia valutato dalle route nel profilo della posizione del chiamante.

    
    </div>

<!-- end list -->

  - **Maschere per stringhe di chiamate di emergenza**  
    Elenco separato da punti e virgola delle stringhe di chiamata tradotte nella **stringa di chiamata di emergenza**specificata. Ad esempio, potresti voler aggiungere 112, che è il numero di servizio di emergenza per la maggior parte dell'Europa. Un utente di Lync che visita l'Europa potrebbe non sapere che 911 è il numero di emergenza degli Stati Uniti, ma può chiamare 112 e ottenere lo stesso risultato. Come per la stringa di chiamata di emergenza, non includere un "+" prima di ogni numero e se si usano i codici di accesso per le linee esterne, verificare che esistano regole di normalizzazione nei criteri di dial plan dell'utente per eliminare la cifra del codice di accesso.

<!-- end list -->

  - **Utilizzo PSTN**  
    Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano il trunk SIP, il gateway PSTN o le chiamate di emergenza del gateway ELIN.
    
    <div>
    

    > [!NOTE]  
    > Un solo utilizzo può essere assegnato a un criterio di posizione. Questo uso PSTN esegue l'override degli usi PSTN assegnati al criterio vocale dell'utente, ma si applica solo alle chiamate poste alla stringa di chiamata di emergenza o a una delle maschere di stringhe di chiamata di emergenza.

    
    </div>

<!-- end list -->

  - **URI di notifica**  
    Specifica uno o più URI SIP del personale di sicurezza che riceve una notifica di messaggistica istantanea quando viene inserita una chiamata di emergenza. I gruppi di distribuzione sono supportati.

<!-- end list -->

  - **URI conferenza**  
    Specifica un numero DID (Direct Interior Dialing) (in genere un numero di banco di sicurezza) che deve essere convogliato in conferenza quando viene inserita una chiamata di emergenza.

<!-- end list -->

  - **Modalità conferenza**  
    Specifica se l'URI della conferenza verrà conferito alla chiamata di emergenza tramite una comunicazione unidirezionale o bidirezionale.

<!-- end list -->

  - **Intervallo di aggiornamento della posizione**  
    Specifica la quantità di tempo (in ore) tra le richieste client per un aggiornamento della posizione dal servizio informazioni sulla posizione. Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12. Il valore predefinito è 4.

</div>

<span> </span>

</div>

</div>

</div>

