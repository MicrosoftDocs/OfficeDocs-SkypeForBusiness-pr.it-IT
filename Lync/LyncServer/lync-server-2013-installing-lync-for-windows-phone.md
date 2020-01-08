---
title: 'Lync Server 2013: installazione di Lync per Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeb8f43ea4f4db15a9a057bd0d7b24c55d858cb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Installazione di Lync per Windows Phone in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-03_

Lync 2013 per Windows Phone è un'applicazione installabile dall'utente disponibile in Windows Phone Marketplace.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Installazione di Lync per Windows Mobile

Puoi richiedere agli utenti di installare Lync 2013 per Windows Phone nei propri dispositivi, indirizzando il computer a Windows Phone Marketplace <http://go.microsoft.com/fwlink/p/?linkid=231901>.

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Se si usa un record SRV DNS per pubblicare i servizi Web di Exchange

Per abilitare l'integrazione di Exchange per i client Lync, alcune organizzazioni pubblicano l'URL dei servizi Web Exchange usando un record SRV DNS. Il documento "informazioni e risoluzione dei problemi di integrazione di Exchange", disponibile nell'area download [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)Microsoft, descrive scenari in cui potrebbe essere necessario. Tuttavia, l'integrazione di Exchange per gli utenti di Windows Phone non funzionerà in questo scenario, perché la piattaforma Windows Phone non supporta le ricerche SRV. È necessario indicare agli utenti di Windows Phone di specificare l'URL dei servizi Web Exchange invece di consentire al telefono di rilevare automaticamente il server.

Indica agli utenti di configurare le impostazioni di Lync nei loro telefoni Windows come indicato di seguito:

1.  In Windows Phone, nelle impostazioni di Lync, selezionare la schermata di **Exchange** .

2.  Posizionare il **server di rilevamento automatico** su **disattivato**.

3.  Toccare il campo vuoto e immettere il nome di dominio completo (FQDN) o l'URL per i servizi Web Exchange.
    
    <div>
    

    > [!NOTE]  
    > È possibile specificare il nome di dominio completo (FQDN) o l'intero URL del server di Exchange Web Services. Se specifichi il nome di dominio completo, il protocollo (https://) e il percorso dei servizi Web di Exchange (/EWS/Exchange.asmx) vengono aggiunti automaticamente. Se il percorso dei servizi Web di Exchange è diverso, è possibile specificare l'URL completo.

    
    </div>

4.  Chiudere lo schermo.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Verifica dell'installazione del client per dispositivi mobili

Dopo aver configurato il client e eseguito l'accesso, usare i test seguenti per verificare che l'installazione di Lync 2013 funzioni correttamente nel dispositivo mobile.

**Cercare un contatto nella directory aziendale**

1.  Nell'elenco contatti toccare **Cerca** nella parte inferiore.

2.  Cercare un contatto esistente solo nell'elenco indirizzi globale.

3.  Verificare che il nome del contatto venga visualizzato nei risultati della ricerca.

**Testare la messaggistica istantanea e la presenza**

1.  Nell'elenco contatti toccare un contatto.

2.  Nella scheda contatto toccare l'icona **messaggistica istantanea** .

3.  Verificare che venga visualizzata una finestra di messaggistica istantanea (IM) e che sia possibile digitare e inviare un messaggio istantaneo.

**Testare i servizi di conferenza telefonica con accesso esterno**

1.  In Outlook pianificare una riunione Lync.

2.  Nel dispositivo mobile aprire l'invito alla riunione.

3.  Fare clic sul collegamento nella riunione per partecipare.

4.  Rispondere alla chiamata dal servizio di conferenza e verificare che l'audio della riunione sia connesso.

**Verificare le notifiche push**

1.  Nel dispositivo mobile dell'utente, accedere a Lync con l'account dell'utente.

2.  Aprire un'altra applicazione nel dispositivo mobile.

3.  In un altro client accedere a Lync con l'account dell'utente B.

4.  Inviare un messaggio istantaneo dall'utente B all'utente a.

5.  Verificare che la notifica di messaggistica istantanea venga visualizzata nel dispositivo mobile dell'utente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

