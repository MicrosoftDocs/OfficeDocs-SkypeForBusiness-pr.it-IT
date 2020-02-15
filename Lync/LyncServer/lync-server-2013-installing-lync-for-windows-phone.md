---
title: 'Lync Server 2013: installazione di Lync per Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 349a4b2609f3b810d0aa64c9e71786f309f21918
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Installazione di Lync per Windows Phone in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-03_

Lync 2013 per Windows Phone è un'applicazione installabile dall'utente disponibile nel Marketplace di Windows Phone.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Installazione di Lync per Windows Mobile

È possibile indicare agli utenti di installare Lync 2013 per Windows Phone sui propri dispositivi, indirizzati a Windows Phone Marketplace all'indirizzo <http://go.microsoft.com/fwlink/p/?linkid=231901>.

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Se si utilizza un record DNS SRV per pubblicare i servizi Web di Exchange

Per abilitare l'integrazione di Exchange per i client Lync, alcune organizzazioni pubblicano l'URL dei servizi Web di Exchange utilizzando un record DNS SRV. Il documento "informazioni e risoluzione dei problemi relativi all' [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)integrazione di Exchange", disponibile nell'area download Microsoft, descrive gli scenari in cui potrebbe essere necessario. Tuttavia, l'integrazione di Exchange per gli utenti di Windows Phone non funzionerà in questo scenario, poiché la piattaforma Windows Phone non supporta le ricerche SRV. Sarà necessario indicare agli utenti di Windows Phone di specificare l'URL dei servizi Web di Exchange anziché consentire al telefono di rilevare automaticamente il server.

Indicare agli utenti di configurare le impostazioni di Lync nei rispettivi telefoni Windows, come indicato di seguito:

1.  In Windows Phone, nelle impostazioni di Lync, selezionare la schermata di **Exchange** .

2.  Spostare il **server di rilevamento automatico** su **disattivato**.

3.  Toccare il campo vuoto e immettere il nome di dominio completo (FQDN) o l'URL per i servizi Web di Exchange.
    
    <div>
    

    > [!NOTE]  
    > È possibile specificare il nome di dominio completo (FQDN) o l'URL completo del server di servizi Web Exchange. Se si specifica il nome di dominio completo, il protocollo (https://) e il percorso dei servizi Web di Exchange (/EWS/Exchange.asmx) vengono aggiunti automaticamente. Se il percorso dei servizi Web Exchange è diverso, è possibile specificare l'URL completo.

    
    </div>

4.  Chiudere lo schermo.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Verifica dell'installazione del client mobile

Dopo aver configurato il client e aver eseguito l'accesso, utilizzare i test seguenti per verificare che l'installazione di Lync 2013 funzioni correttamente sul dispositivo mobile.

**Cercare un contatto nella directory aziendale**

1.  Nell'elenco Contatti toccare **Cerca** in basso.

2.  Cercare un contatto presente solo nell'elenco indirizzi globale.

3.  Verificare che il nome del contatto sia incluso nei risultati della ricerca.

**Testare la messaggistica istantanea e la presenza**

1.  Toccare un contatto nell'elenco contatti.

2.  Nella scheda del contatto toccare l'icona **Messaggistica istantanea**.

3.  Verificare che venga visualizzata una finestra di messaggistica istantanea e che sia possibile digitare e inviare un messaggio istantaneo.

**Testare le funzionalità di conferenza telefonica con accesso esterno**

1.  In Outlook, pianificare una riunione di Lync.

2.  Aprire l'invito alla riunione nel dispositivo mobile.

3.  Fare clic sul collegamento nell'invito per partecipare alla riunione.

4.  Rispondere alla chiamata dal servizio di conferenza e verificare di essere connessi all'audio della riunione.

**Verificare le notifiche push**

1.  Nel dispositivo mobile dell'utente A accedere a Lync con l'account dell'utente A.

2.  Aprire un'altra applicazione nel dispositivo mobile.

3.  In un altro client, accedere a Lync con l'account dell'utente B.

4.  Inviare un messaggio istantaneo dall'utente B all'utente A.

5.  Verificare che la notifica di messaggio istantaneo venga visualizzata nel dispositivo mobile dell'utente A.

</div>

</div>

<span> </span>

</div>

</div>

</div>

