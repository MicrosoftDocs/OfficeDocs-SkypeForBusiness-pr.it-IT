---
title: 'Lync Server 2013: configurare la telefonia per un utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d10ec9aea5801f91301e5c054b13bba63f8ef29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Configurare la telefonia per un utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Le impostazioni di telefonia sono alcune delle singole impostazioni di un account utente che possono essere configurate nel pannello di controllo di Lync Server per l'utente, ovvero se il singolo utente è stato abilitato per Lync Server 2013 e l'organizzazione supporta la telefonia.

Le opzioni di telefonia utente di Lync Server includono le seguenti:

  - **Audio/video disabilitato**   l'utente non può effettuare chiamate con audio e video.

  - **Da PC a PC solo**   l'utente può effettuare solo chiamate audio o video da PC a PC.

  - **VoIP aziendale l'**   utente può utilizzare l'infrastruttura di Lync Server 2013 per instradare tutte le chiamate in ingresso e in uscita. Può inoltre effettuare chiamate da PC a PC.

  - **Controllo delle chiamate remote**   l'utente può utilizzare Lync Server 2013 per controllare il telefono desktop e può anche effettuare chiamate da PC a PC.

Per informazioni dettagliate sulla configurazione della telefonia per un'organizzazione, vedere [configurare la telefonia per un utente in Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [distribuzione di VoIP aziendale in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>Per configurare la telefonia per un account utente specifico

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo SIP o l'URI (Uniform Resource Identifier) linea dell'account utente desiderato e quindi fare clic su **Trova**.

5.  Nella tabella fare clic sull'account utente che si desidera modificare.

6.  Scegliere **Modifica** dal menu **Modifica**.

7.  In **Telefonia** eseguire le operazioni seguenti:
    
      - Per disabilitare le chiamate audio e le videochiamate per l'utente, fare clic su **Audio/video disabilitati**.
    
      - Per abilitare le comunicazioni audio da PC a PC per l'utente, ma non il controllo delle chiamate remote o VoIP aziendale, fare clic su **Solo da PC a PC**. Specificare un valore per **URI linea** per il telefono utilizzato dall'utente per le comunicazioni audio da PC a PC.
    
      - Per instradare le chiamate telefoniche dell'utente utilizzando l'infrastruttura di Lync Server 2010 in base alla classe dei criteri di servizio, incluse le comunicazioni audio da PC a PC, fare clic su **VoIP aziendale**. In **URI linea** specificare il numero di telefono per VoIP aziendale. In **Criteri dial plan** e **Criteri vocali** specificare i criteri appropriati per l'utente. Per specificare le regole di normalizzazione per la conversione dei numeri di telefono composti dall'utente nel formato E.164, selezionare il profilo località appropriato in **Criteri percorso**.
    
      - Per abilitare il controllo delle chiamate remote, che consente agli utenti di controllare la linea telefonica desktop da Lync Server 2013 per effettuare chiamate da PC a PC e chiamate da PC a telefono, fare clic su **Remote Call Control**. In **URI linea** specificare il numero di telefono per il controllo delle chiamate remote. L'utente deve disporre di un telefono da scrivania e di una connessione PBX per il routing delle chiamate.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modifica delle proprietà degli account utente in Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

