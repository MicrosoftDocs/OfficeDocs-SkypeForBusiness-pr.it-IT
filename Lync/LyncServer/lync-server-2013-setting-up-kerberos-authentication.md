---
title: "Lync Server 2013: Configurazione dell'autenticazione Kerberos"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c644dd613b3186b314e8fc78b42197709286200
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Configurazione dell'autenticazione Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Lync Server 2013 supporta l'autenticazione NTLM e Kerberos per i servizi Web. Office Communications Server 2007 e Office Communications Server 2007 R2 ha usato RTCComponentService e RTCService predefiniti come account utente per eseguire i pool di applicazioni dei servizi Web, consentendo l'assegnazione di un nome dell'entità servizio (SPN) all'utente account e per fungere da entità di autenticazione. Lync Server usa NetworkService per eseguire i servizi Web e NetworkService non può avere assegnati nomi SPN.

Per risolvere il problema di non avere oggetti Active Directory per contenere i nomi SPN, il pannello di controllo di Lync Server può usare gli oggetti account del computer per questo scopo. Gli oggetti account computer possono contenere i nomi SPN e non sono soggetti alla scadenza della password, che è stato un problema con l'uso degli account utente nelle versioni precedenti.

Puoi usare i cmdlet di Windows PowerShell per configurare gli oggetti computer per ottenere l'autenticazione Kerberos.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Prerequisiti per abilitare l'autenticazione Kerberos in Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Creare un account di autenticazione Kerberos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Assegnare un account di autenticazione Kerberos a un sito in Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configurazione delle password degli account di autenticazione Kerberos in Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Aggiungere l'autenticazione Kerberos ad altri siti in Lync Server 2013](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Rimuovere l'autenticazione Kerberos da un sito in Lync Server 2013](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Verifica e segnalazione dello stato e dell'assegnazione dell'autenticazione Kerberos in Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

