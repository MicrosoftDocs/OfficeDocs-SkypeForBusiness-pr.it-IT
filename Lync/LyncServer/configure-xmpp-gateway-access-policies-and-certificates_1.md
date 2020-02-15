---
title: Configurare i certificati e i criteri di accesso del gateway XMPP
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
ms.openlocfilehash: 9f622ed573a6d30d35b55d2c07ec21ef79b46424
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurare i certificati e i criteri di accesso del gateway XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-15_

La federazione XMPP definisce una distribuzione esterna basata sul protocollo XMPP (eXtensible Messaging and Presence Protocol). Una configurazione XMPP consente agli utenti di Lync di comunicare con gli utenti di domini XMPP mediante:

  - Messaggistica istantanea e informazioni sulla presenza: solo da persona a persona.

  - Creazione di contatti federati XMPP nel client Lync.

Quando si configurano i criteri per il supporto di partner federati XMPP, tali criteri si applicano agli utenti di domini federati XMPP, ma non agli utenti di provider di servizi di messaggistica istantanea SIP (Session Initiation Protocol), ad esempio Windows Live, o di domini federati SIP. Configurare un partner federato XMPP per ogni dominio federato XMPP di cui si desidera consentire agli utenti di aggiungere contatti e con cui possono comunicare. Dopo aver configurato i criteri, è necessario configurare i certificati del gateway XMPP.

<div>


> [!NOTE]  
> Per avviare la migrazione del gateway XMPP, è necessario distribuire il gateway XMPP di Lync Server 2013 e configurare i criteri di accesso per abilitare gli utenti per il gateway XMPP di Lync Server 2013. Prima di eseguire questa procedura, è necessario spostare tutti gli utenti nella distribuzione di Lync Server 2013. Per ulteriori informazioni, vedere <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">configurare il gateway XMPP in Lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Configurare criteri di accesso esterno in modo da abilitare gli utenti per il gateway XMPP di Lync Server 2013

1.  Aprire il Pannello di controllo di Lync Server.

2.  Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Criteri di accesso esterno**.

3.  Fare clic su **Nuovo** e quindi su **Criteri utente**.

4.  Immettere un nome per l'impostazione dei criteri utente di accesso esterno.

5.  Specificare una descrizione per l'impostazione dei criteri utente di accesso esterno.

6.  Selezionare **Abilita comunicazioni con utenti federati**.

7.  Selezionare **Abilita le comunicazioni con gli utenti federati XMPP**.

8.  Fare clic su **Commit** per salvare le modifiche apportate ai criteri utente o sito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

