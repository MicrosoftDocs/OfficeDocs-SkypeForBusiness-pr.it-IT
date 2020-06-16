---
title: Configurare criteri e certificati di accesso al gateway XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 72e17634a8836a56ce7002e3d0cf57440f72c60f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurare criteri e certificati di accesso al gateway XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-15_

XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:

  - Messaggistica istantanea e informazioni sulla presenza: solo da persona a persona.

  - Creazione di contatti federati XMPP nel client Lync.

When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.

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

