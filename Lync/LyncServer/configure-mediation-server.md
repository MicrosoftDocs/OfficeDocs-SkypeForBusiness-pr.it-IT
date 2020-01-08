---
title: Configurare Mediation Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurare Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

In questa procedura vengono illustrati i passaggi per configurare il pool di Lync Server 2013 per l'uso di Lync Server 2013 Mediation Server, invece del server di mediazione legacy di Office Communications Server 2007 R2.

Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario avere effettuato l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È anche possibile delegare i diritti e le autorizzazioni di amministratore appropriati per l'aggiunta di ruoli del server. Per informazioni dettagliate, vedere delegare le autorizzazioni di configurazione nella documentazione relativa alla distribuzione del server Standard Edition o Server Enterprise Edition. Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.

<div>


> [!NOTE]  
> Per informazioni aggiornate sulla ricerca di gateway PSTN, IP-PBX e servizi di trunking SIP qualificati che funzionano con Lync Server 2013, vedere "Microsoft Unified Communications Open Interoperability Program" <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Per configurare Mediation Server tramite Generatore di topologie

1.  Aprire una topologia esistente da generatore di topologie.

2.  Nel riquadro sinistro passare a **gateway PSTN**.

3.  Fare clic con il pulsante destro del mouse su **gateway PSTN**e quindi scegliere **nuovo gateway IP/PSTN**.

4.  Completare la pagina **Definisci nuovo gateway IP/PSTN** con le informazioni seguenti:
    
      - Immettere il nome di dominio completo o l'indirizzo IP del gateway. Il nome di dominio completo del gateway è obbligatorio se il gateway usa il protocollo TLS.
    
      - Accettare il valore predefinito della **porta di ascolto per il gateway IP/PSTN** o immettere la nuova porta di attesa se è stata modificata.
    
      - Impostare il **protocollo di trasporto SIP**.

5.  Nel riquadro sinistro passare al **pool Enterprise Edition front-end** o al **Server Standard Edition**.

6.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

7.  In **Mediation Server**impostare le **porte in ascolto**.

8.  Associa quindi il gateway PSTN appena creato selezionandolo e facendo clic su **Aggiungi**.

9.  In **Generatore di topologie**selezionare il più alto nodo **Lync Server**.

10. Scegliere **Pubblica topologia** dal menu **azione** e quindi fare clic su **Avanti**.

11. Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.

<div>


> [!NOTE]  
> È importante completare l'argomento successivo, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">modificare le route vocali per usare il nuovo server di mediazione di Lync server 2013</A> per assicurarsi che le route vocali rivoltino al server Mediation corretto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

