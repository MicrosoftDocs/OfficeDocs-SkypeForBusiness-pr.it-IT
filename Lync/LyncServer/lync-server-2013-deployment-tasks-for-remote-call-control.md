---
title: 'Lync Server 2013: attività di distribuzione per il controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2ac45e0f589ac155d2e0f51b0115036a97809e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499053"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

In questo argomento vengono descritte le attività di distribuzione che è necessario eseguire per abilitare il controllo delle chiamate remote per gli utenti nell'ambiente di Lync Server.

<div>


> [!NOTE]  
> Se si esegue la migrazione degli utenti precedentemente abilitati per il controllo delle chiamate remote in Microsoft Office Communicator 2007 R2, è necessario eseguire un'attività di distribuzione aggiuntiva prima di iniziare a eseguire le attività di distribuzione del controllo delle chiamate remote descritte in questo argomento. Durante il processo di migrazione a Lync Server, è necessario rimuovere le voci di applicazioni attendibili (in precedenza note come <EM>voci host autorizzate</EM>) utilizzando gli strumenti di amministrazione di Office Communications Server 2007 R2, in base alle esigenze.<BR>Per informazioni dettagliate sulla rimozione di host autorizzati, vedere <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a Legacy Authorized host in Lync Server 2013 (optional)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Passaggio 1: installare e configurare il gateway SIP/CSTA per comunicare con un PBX

È necessario installare almeno un gateway SIP/CSTA che sia in grado di connettersi a Lync Server e al PBX (Private Branch Exchange) esistente nel proprio ambiente per fornire agli utenti le funzionalità di controllo delle chiamate remote. Un gateway SIP/CSTA è un gateway tra SIP e CSTA (Computer-Supported Telecommunications Application). Indipendentemente dal numero di gateway installati, ogni utente può essere configurato con un solo gateway o PBX. Se il PBX esistente non dispone di un'interfaccia SIP/CSTA, distribuire un gateway SIP/CSTA in grado di supportare il PBX, incluso il supporto per protocolli di segnalazione specifici del fornitore del PBX proprietario. Per informazioni dettagliate sulle funzionalità, rivolgersi direttamente al fornitore.

Quando si è pronti a distribuire un gateway SIP/CSTA che può integrarsi con Lync Server per il controllo delle chiamate remote, consultare anche il fornitore del gateway o la documentazione relativa al gateway del fornitore per quanto riguarda la sintassi richiesta dal gateway per le informazioni seguenti:

  - URI server linea del gateway

  - URI di linea per gli utenti che verranno assegnati al gateway

Le impostazioni precedenti sono necessarie durante la configurazione utente e devono essere specificate come previsto dal gateway per eseguire correttamente il routing e la connessione al PBX.

È possibile fare riferimento ai fornitori nel sito Web Microsoft Unified Communications Open Interoperability Program all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Passaggio 2: configurare Lync Server per instradare le richieste CSTA al gateway SIP/CSTA

È necessario creare route statiche nei pool di Lync Server con l'indirizzo di destinazione (URI server) di tutti i gateway SIP/CSTA nella distribuzione a cui si intende instradare le richieste di controllo delle chiamate remote. È inoltre necessario creare una voce di applicazione attendibile corrispondente a ogni indirizzo di destinazione. Quando si designa il gateway come applicazione attendibile, viene assegnato lo stato attendibile all'esecuzione come parte dell'ambiente Lync Server anche se è stato sviluppato da terze parti (ed è in esecuzione ciò che viene definito come *servizio esterno* , poiché si tratta di un servizio che non è una parte incorporata del prodotto). Infine, se Lync Server si connetterà al gateway SIP/CSTA utilizzando una connessione TCP (Transmission Control Protocol) anziché una connessione TLS (Transport Layer Security), è necessario definire anche l'indirizzo IP del gateway tramite Generatore di topologie.

Per informazioni dettagliate sulla configurazione delle route statiche, vedere [configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Per informazioni dettagliate sulla configurazione di voci di applicazioni attendibili, vedere [Configure a Trusted Application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Per informazioni dettagliate sulla definizione di un indirizzo IP del gateway SIP/CSTA in Generatore di topologie, vedere [define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Passaggio 3: configurare gli utenti di Lync per il controllo delle chiamate remote

Dopo che gli utenti sono stati abilitati per Lync Server, è possibile utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per abilitare il controllo delle chiamate remote. Durante questo passaggio di distribuzione si assegna a ogni utente in URI server linea e un URI di linea. L'URI server linea è l'URI SIP del gateway SIP/CSTA che si intende assegnare all'utente. L'URI di linea è il numero di telefono univoco assegnato all'utente.

Per informazioni dettagliate sulla configurazione degli utenti per il controllo delle chiamate remote, vedere [abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Passaggio 4: definire le regole di normalizzazione dei numeri di telefono di Lync Server

Negli scenari di controllo delle chiamate remote, Lync Server utilizza le regole di normalizzazione dei numeri di telefono per convertire il numero di telefono ricevuto dal gateway SIP/CSTA nel formato E. 164. I numeri di telefono devono essere in questo formato standardizzato per garantire il corretto funzionamento di alcune funzionalità di controllo delle chiamate remote. Il controllo delle chiamate remote utilizza le stesse regole di normalizzazione dei numeri di telefono configurate per la normalizzazione dei numeri di telefono del servizio Rubrica, che sono diverse da quelle utilizzate per VoIP aziendale.

Per informazioni dettagliate su come il controllo delle chiamate remote utilizza le regole di normalizzazione dei numeri di telefono, vedere [Remote Call Control and Phone Number normalizzation in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Per informazioni dettagliate sulle regole di normalizzazione dei numeri di telefono per il servizio Rubrica, vedere [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic nella documentazione relativa alle operazioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

