---
title: Configurare criteri di accesso e certificati del gateway XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3f1aabeeb49ecc413107d5cd346f310c0d2d294
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurare criteri di accesso e certificati del gateway XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-15_

La Federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di Lync di accedere agli utenti del dominio XMPP:

  - Messaggistica istantanea e presenza: solo persona a persona

  - Creazione di contatti federati XMPP nel client Lync

Quando si configurano i criteri per il supporto dei partner federati di Extensible Messaging and Presence Protocol (XMPP), i criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti dei provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol) (ad esempio, Windows Live) o i domini federati SIP. Si configura un partner federato XMPP per ogni dominio federato XMPP in cui si vuole consentire agli utenti di aggiungere contatti e comunicare. Dopo aver inserito i criteri, è necessario configurare i certificati del gateway XMPP.

<div>


> [!NOTE]  
> Per avviare la migrazione del gateway XMPP, è necessario distribuire il gateway XMPP di Lync Server 2013 e configurare i criteri di accesso per consentire agli utenti il gateway XMPP di Lync Server 2013. Prima di eseguire questa procedura, tutti gli utenti devono essere spostati nella distribuzione di Lync Server 2013. Per informazioni dettagliate, vedere <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">configurare il gateway XMPP in Lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Configurare un criterio di accesso esterno per consentire agli utenti il gateway XMPP di Lync Server 2013

1.  Aprire il pannello di controllo di Lync Server.

2.  Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **criteri di accesso esterno**.

3.  Fare clic su **nuovo** e quindi su **criteri utente**.

4.  Immettere un nome per il criterio utente di accesso esterno.

5.  Specificare una descrizione per i criteri degli utenti di Access esterni.

6.  Selezionare **Abilita comunicazioni con gli utenti federati**.

7.  Selezionare **Abilita comunicazioni con utenti federati XMPP**.

8.  Fare clic su **conferma** per salvare le modifiche apportate ai criteri per il sito o per gli utenti.

</div>

</div>

<span> </span>

</div>

</div>

</div>

