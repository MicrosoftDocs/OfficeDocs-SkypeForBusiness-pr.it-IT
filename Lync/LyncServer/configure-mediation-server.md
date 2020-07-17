---
title: Configurare Mediation Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82da1720cab2e6895c53565da17c9411faabdfbd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>Configurare Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

In questa procedura vengono illustrati i passaggi per configurare il pool di Lync Server 2013 per l'utilizzo di Lync Server 2013 Mediation Server, anziché del Mediation Server di Office Communications Server 2007 R2 legacy.

Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario accedere come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È inoltre possibile delegare i diritti di amministratore e le autorizzazioni appropriate per l'aggiunta di ruoli del server. Per informazioni dettagliate, vedere Delegare autorizzazioni di installazione nella documentazione relativa alla distribuzione del server Standard Edition o Enterprise Edition. Per apportare altre modifiche relative alla configurazione è sufficiente appartenere al gruppo RTCUniversalServerAdmins.

<div>


> [!NOTE]  
> Per informazioni più aggiornate sulla ricerca di gateway PSTN, IP-PBX e servizi di trunking SIP qualificati che interagiscono con Lync Server 2013, vedere "Microsoft Unified Communications Open Interoperability Program" all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>Per configurare Mediation Server mediante il Generatore di topologie

1.  Aprire una topologia esistente dal Generatore di topologie.

2.  Nel riquadro sinistro spostarsi su **Gateway PSTN**.

3.  Fare clic con il pulsante destro del mouse su **Gateway PSTN** e quindi scegliere **Nuovo gateway IP/PSTN**.

4.  Inserire le informazioni seguenti nella pagina **Definisci nuovo gateway IP/PSTN**:
    
      - Immettere il nome di dominio completo (FQDN) o l'indirizzo IP del gateway. Il nome di dominio completo (FQDN) del gateway è richiesto se il gateway utilizza il protocollo TLS.
    
      - Accettare il valore predefinito di **Porta di attesa per gateway IP/PSTN** o immettere la nuova porta di attesa, se è stata modificata.
    
      - Impostare il **Protocollo trasporto SIP**.

5.  Nel riquadro sinistro spostarsi su **Pool Enterprise Edition Front End** o **Server Standard**.

6.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.

7.  In **Mediation Server** impostare le **Porte di attesa**.

8.  Quindi, associare il gateway PSTN creato selezionandolo e facendo clic su **Aggiungi**.

9.  In **Generatore di topologie** selezionare il nodo di primo livello **Lync Server**.

10. Nel menu **Azioni** selezionare **Pubblica topologia** e fare clic su **Avanti**.

11. Al termine della **Pubblicazione guidata**, fare clic su **Fine** per chiudere la procedura guidata.

<div>


> [!NOTE]  
> È importante completare l'argomento successivo, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">modificare le route vocali per utilizzare il nuovo Lync server 2013 Mediation Server</A> per assicurarsi che le route vocali puntino al Mediation Server corretto.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

