---
title: 'Lync Server 2013: definizione dei criteri percorso'
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
ms.openlocfilehash: 64c164f24f0f2c140a140b7343dd526979cc2bff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a>Definizione dei criteri percorso per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

Ogni criterio percorso contiene le informazioni seguenti:

  - **Servizi di emergenza abilitati**  
    Quando questo valore è **Yes**, il client è abilitato per il servizio E9-1-1. Quando un client si registra, tenta di acquisire una posizione dal servizio informazioni percorso e includerà le informazioni sul percorso come parte di una chiamata di emergenza.

<!-- end list -->

  - **Posizione obbligatoria**  
    Questa impostazione viene utilizzata solo quando i **servizi di emergenza abilitati** sono impostati su **Sì**.
    
    È possibile configurare l'impostazione del **percorso necessario** per definire il comportamento del client. L'impostazione del valore su **No** significa che all'utente non verrà richiesto un percorso. Se si imposta il valore su **Sì** , l'utente riceverà la richiesta di una posizione, ma può ignorare il prompt. Se si imposta il valore come dichiarazione di non **responsabilità** , all'utente verrà richiesto un percorso e verrà visualizzata una dichiarazione di non responsabilità se si tenta di eliminare il messaggio. In tutti i casi, l'utente può continuare a utilizzare il client.
    
    <div>
    

    > [!NOTE]  
    > Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il servizio E9-1-1. Gli aggiornamenti del testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità.

    
    </div>

<!-- end list -->

  - **Dichiarazione di non responsabilità avanzata del servizio di emergenza**  
    Questa impostazione consente di specificare la dichiarazione di non responsabilità che gli utenti vedranno se ignorano la richiesta di un percorso. In Lync Server 2013, è possibile utilizzare i criteri percorso per impostare diverse dichiarazioni di non responsabilità per le diverse impostazioni locali o gruppi di utenti diversi.
    
    <div>
    

    > [!NOTE]  
    > Questa impostazione dei criteri percorso è diversa da Lync Server 2010, in cui è stato utilizzato il cmdlet <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> per impostare una dichiarazione di non responsabilità globale per l'intera organizzazione. Se esiste già una dichiarazione di non responsabilità globale, è necessario specificare la dichiarazione di non responsabilità nei criteri percorso. Vale a dire che Lync Server 2013 utilizza solo dichiarazioni di non responsabilità specificate nei criteri percorso.

    
    </div>

<!-- end list -->

  - **Stringa di chiamata di emergenza**  
    Questa stringa di composizione (meno la principale "+", ma inclusa la normalizzazione fatta dal dial plan dell'utente di Lync) significa che una chiamata è una chiamata di emergenza. La **stringa di composizione di emergenza** induce il client a includere le informazioni sul percorso e sulla richiamata tramite la chiamata.
    
    <div>
    

    > [!NOTE]  
    > Se l'organizzazione non utilizza un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione del dial plan corrispondente che aggiunga una "+" alla stringa 911 prima di inviare la chiamata al routing in uscita su un server del pool Lync. il "+" verrà anteposto automaticamente dal client Lync come risultato del criterio percorso. Tuttavia, se il sito utilizza un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione al criterio del dial plan applicabile che rimuove il prefisso di accesso esterno e aggiunge "+". Ad esempio, se la posizione utilizza un prefisso di accesso esterno pari a 9 e un utente compone&nbsp;9 911 per effettuare una chiamata di emergenza, il client utilizzerà i criteri di dial plan per normalizzare questo valore su + 911 prima che il numero composto venga valutato dalle route nel profilo località del chiamante.

    
    </div>

<!-- end list -->

  - **Maschere di stringa di chiamata di emergenza**  
    Elenco separato da punto e virgola di stringhe di composizione che vengono convertite nella **stringa di chiamata di emergenza**specificata. Ad esempio, si consiglia di aggiungere 112, che è il numero di servizio di emergenza per la maggior parte dell'Europa. Un utente di Lync in visita dall'Europa potrebbe non sapere che 911 è il numero di emergenza degli Stati Uniti, ma può comporre 112 e ottenere lo stesso risultato. Analogamente alla stringa di chiamata di emergenza, non includere un "+" prima di ogni numero e se si utilizzano codici di accesso alla linea esterna, accertarsi che siano presenti regole di normalizzazione nel criterio di dial plan dell'utente per eliminare la cifra del codice di accesso.

<!-- end list -->

  - **Utilizzo PSTN**  
    Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano il trunk SIP, il gateway PSTN o le chiamate di emergenza del gateway ELIN.
    
    <div>
    

    > [!NOTE]  
    > È possibile assegnare un solo utilizzo a un criterio percorso. Questo utilizzo PSTN sostituisce gli utilizzi PSTN assegnati ai criteri vocali dell'utente, ma si applica solo alle chiamate effettuate alla stringa di chiamata di emergenza o a una delle maschere di chiamata di stringa di emergenza.

    
    </div>

<!-- end list -->

  - **URI di notifica**  
    Specifica uno o più URI SIP del personale di sicurezza che ricevono una notifica di messaggistica istantanea quando viene effettuata una chiamata di emergenza. Sono supportati i gruppi di distribuzione.

<!-- end list -->

  - **URI conferenza**  
    Specifica un numero DID (Direct Inward Dialing) (in genere, un numero del desk di sicurezza) che dovrebbe essere utilizzato per la conferenza quando viene effettuata una chiamata di emergenza.

<!-- end list -->

  - **Modalità conferenza**  
    Specifica se l'URI conferenza verrà configurata nella chiamata di emergenza utilizzando una comunicazione unidirezionale o bidirezionale.

<!-- end list -->

  - **Intervallo di aggiornamento delle posizioni**  
    Specifica la quantità di tempo (in ore) tra le richieste dei client per un aggiornamento del percorso dal servizio informazioni percorso. Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12. Il valore predefinito è 4.

</div>

<span> </span>

</div>

</div>

</div>

