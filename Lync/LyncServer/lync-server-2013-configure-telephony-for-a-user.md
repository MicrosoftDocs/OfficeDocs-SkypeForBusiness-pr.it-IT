---
title: 'Lync Server 2013: configurare la telefonia per un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97f4fc79b871a962fe498d6dbd908b75f6b2fecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Configurare la telefonia per un utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Le impostazioni di telefonia sono alcune delle singole impostazioni di un account utente che possono essere configurate nel pannello di controllo di Lync Server per l'utente, ovvero se il singolo utente è stato abilitato per Lync Server 2013 e l'organizzazione supporta la telefonia.

Le opzioni di telefonia degli utenti di Lync Server includono le seguenti:

  - **Audio/video disabilitato**   l'utente non può effettuare chiamate con audio e video.

  - **Da PC a PC solo**   l'utente può effettuare solo chiamate audio o video da PC a PC.

  - **VoIP aziendale l'**   utente può usare l'infrastruttura Lync Server 2013 per instradare tutte le chiamate in entrata e in uscita. L'utente può anche effettuare chiamate da PC a PC.

  - **Controllo delle chiamate remote**   l'utente può usare Lync Server 2013 per controllare il telefono desktop e può anche eseguire chiamate da PC a PC.

Per informazioni dettagliate sulla configurazione della telefonia per un'organizzazione, vedere [configurare la telefonia per un utente in Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [distribuire Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>Per configurare la telefonia per un account utente specifico

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente desiderato, quindi fare clic su **trova**.

5.  Nella tabella fare clic sull'account utente che si vuole modificare.

6.  Nel menu **modifica** fare clic su **modifica**.

7.  In **telefonia**eseguire le operazioni seguenti:
    
      - Per disabilitare le chiamate audio e video per l'utente, fare clic su **disabilitato audio/video**.
    
      - Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non per controllo delle chiamate remote o VoIP aziendale, fare clic su **solo da PC a PC**. Specificare un valore per l' **URI di linea** per il telefono usato dall'utente per le comunicazioni audio da PC a PC.
    
      - Per instradare le chiamate telefoniche dell'utente tramite l'infrastruttura di Lync Server 2010 in base alla classe di criteri di servizio, incluse le comunicazioni audio da PC a PC, fare clic su **VoIP aziendale**. In **URI linea**specificare il numero di telefono per VoIP aziendale. In **criteri di dial plan** e **criteri vocali**specificare i criteri appropriati per l'utente. Per specificare le regole di normalizzazione per la traduzione dei numeri di telefono comunicati dall'utente nel formato E. 164, selezionare il profilo di posizione appropriato in **criteri posizione**.
    
      - Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Lync Server 2013 per effettuare chiamate da PC a PC e da PC a telefono, fare clic su controllo delle chiamate **Remote**. In **URI linea**specificare il numero di telefono per il controllo delle chiamate remote. L'utente deve avere un telefono desktop e una connessione PBX (Private Branch Exchange) per il routing delle chiamate.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modifica delle proprietà dell'account utente in Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

