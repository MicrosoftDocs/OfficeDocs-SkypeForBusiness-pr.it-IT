---
title: 'Lync Server 2013: Attività di distribuzione per il controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63c9cba56ccedf3559b1e9f1da1ee58cc03e195
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

In questo argomento vengono illustrate le attività di distribuzione che è necessario eseguire per abilitare il controllo delle chiamate remote per gli utenti nell'ambiente Lync Server.

<div>


> [!NOTE]  
> Se si esegue la migrazione degli utenti precedentemente abilitati per il controllo delle chiamate remote in Microsoft Office Communicator 2007 R2, è necessario eseguire un'attività di distribuzione aggiuntiva prima di iniziare a eseguire le attività di distribuzione del controllo delle chiamate remote descritte in questo argomento. Durante il processo di migrazione a Lync Server, le voci di applicazione attendibili (precedentemente note come <EM>voci dell'host autorizzato</EM>) devono essere rimosse usando gli strumenti amministrativi di Office Communications Server 2007 R2, in base alle esigenze.<BR>Per informazioni dettagliate sulla rimozione di host autorizzati, vedere <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">rimuovere un host autorizzato legacy in Lync Server 2013 (facoltativo)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Passaggio 1: installare e configurare il gateway SIP/CSTA per comunicare con il PBX

È necessario installare almeno un gateway SIP/CSTA in grado di connettersi sia a Lync Server che al PBX (Private Branch Exchange) esistente nell'ambiente per ottenere funzionalità di controllo delle chiamate remote agli utenti. Un gateway SIP/CSTA è un gateway tra SIP e un'applicazione di telecomunicazioni supportata dal computer (CSTA). Indipendentemente dal fatto che si installino più gateway o uno solo, ogni utente può essere configurato con un solo gateway o PBX. Se il tuo PBX esistente non ha un'interfaccia SIP/CSTA, assicurati di distribuire un gateway SIP/CSTA in grado di supportare il PBX, incluso il supporto per i protocolli di segnalazione specifici del fornitore PBX. Per informazioni dettagliate sulle funzionalità, consultare direttamente ogni fornitore.

Quando si è pronti a distribuire un gateway SIP/CSTA che può essere integrato con Lync Server per il controllo delle chiamate remote, consultare anche il fornitore del gateway o la documentazione del gateway del fornitore relativa alla sintassi richiesta dal gateway per le informazioni seguenti:

  - URI del server di linea del gateway

  - URI di linea per gli utenti che verranno assegnati al gateway

Le impostazioni precedenti sono necessarie durante la configurazione dell'utente e devono essere specificate come previsto dal gateway per instradare e connettere correttamente il PBX.

È possibile fare riferimento a fornitori nel sito Web Microsoft Unified Communications Open Interoperability Program [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Passaggio 2: configurare Lync Server per instradare le richieste CSTA al gateway SIP/CSTA

È necessario creare route statiche nei pool di Lync Server fino all'indirizzo di destinazione (URI del server) di tutti i gateway SIP/CSTA nella distribuzione a cui si vuole instradare le richieste di controllo delle chiamate remote. Devi anche creare una voce di applicazione attendibile che corrisponda a ogni indirizzo di destinazione. Quando si designa il gateway come applicazione attendibile, viene assegnato lo stato attendibile per l'esecuzione come parte dell'ambiente Lync Server anche se è sviluppato da una terza parte (ed esegue il nome di un *servizio esterno* perché si tratta di un servizio che non è una parte incorporata del prodotto). Infine, se Lync Server si connette al gateway SIP/CSTA usando una connessione TCP (Transmission Control Protocol) invece di una connessione TLS (Transport Layer Security), è necessario definire anche l'indirizzo IP del gateway usando generatore di topologie.

Per informazioni dettagliate sulla configurazione di route statiche, vedere [configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Per informazioni dettagliate sulla configurazione di voci di applicazione attendibili, vedere [configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Per informazioni dettagliate sulla definizione di un indirizzo IP del gateway SIP/CSTA in Generatore di topologia, vedere [definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Passaggio 3: configurare gli utenti di Lync per il controllo delle chiamate remote

Dopo che gli utenti sono stati abilitati per Lync Server, è possibile usare il pannello di controllo di Lync Server o Lync Server Management Shell per abilitarli per il controllo delle chiamate remote. È durante questo passaggio di distribuzione che si assegna a ogni utente un URI del server di linea e un URI di linea. L'URI del server di linea è l'URI SIP del gateway SIP/CSTA che si prevede di assegnare all'utente. L'URI di linea è il numero di telefono univoco assegnato all'utente.

Per informazioni dettagliate sulla configurazione degli utenti per il controllo delle chiamate remote, vedere [abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Passaggio 4: definire le regole di normalizzazione dei numeri di telefono di Lync Server

Negli scenari di controllo delle chiamate remote, Lync Server usa le regole di normalizzazione dei numeri di telefono per convertire il numero di telefono ricevuto dal gateway SIP/CSTA al formato E. 164. I numeri di telefono devono essere in questo formato standardizzato per alcune funzionalità di controllo delle chiamate remote per funzionare correttamente. Il controllo delle chiamate remote usa le stesse regole di normalizzazione dei numeri di telefono configurate per la normalizzazione dei numeri di telefono del servizio Rubrica, che sono diversi dalle regole di normalizzazione dei numeri di telefono usate per VoIP aziendale.

Per informazioni dettagliate su come il controllo delle chiamate remote USA regole di normalizzazione dei numeri di telefono, vedere [controllo delle chiamate remote e normalizzazione di numeri di telefono in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Per informazioni dettagliate sulle regole di normalizzazione dei numeri di telefono per il servizio Rubrica, vedere [amministrazione del servizio Rubrica in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) argomento della documentazione delle operazioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

