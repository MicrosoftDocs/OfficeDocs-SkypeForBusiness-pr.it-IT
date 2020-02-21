---
title: "Lync Server 2013: configurazione dell'autenticazione Kerberos"
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
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Configurazione dell'autenticazione Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Lync Server 2013 supporta l'autenticazione NTLM e Kerberos per i servizi Web. Office Communications Server 2007 e Office Communications Server 2007 R2 hanno utilizzato le impostazioni predefinite di RTCComponentService e RTCService come account utente per l'esecuzione dei pool di applicazioni dei servizi Web, consentendo l'assegnazione di un nome dell'entità servizio (SPN, Service Principal Name) all'utente account e fungere da entità di autenticazione. Lync Server utilizza NetworkService per eseguire i servizi Web e NetworkService non è in grado di assegnare nomi SPN.

Per risolvere il problema di non disporre di oggetti di Active Directory che contengano gli SPN, il pannello di controllo di Lync Server può utilizzare gli oggetti account computer per questo scopo. Gli oggetti account computer possono contenere i nomi SPN e non sono soggetti a scadenza della password, un problema associato all'utilizzo degli account utente nelle versioni precedenti.

È possibile utilizzare i cmdlet di Windows PowerShell per configurare gli oggetti computer per fornire l'autenticazione Kerberos.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Prerequisiti per l'abilitazione dell'autenticazione Kerberos in Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Creare un account di autenticazione Kerberos in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Assegnare un account di autenticazione Kerberos a un sito in Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configurazione delle password degli account di autenticazione Kerberos in Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [In Lync Server 2013 aggiungere l'autenticazione Kerberos ad altri siti](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [In Lync Server 2013 rimuovere l'autenticazione Kerberos da un sito](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Verifica e segnalazione dello stato e dell'assegnazione dell'autenticazione Kerberos in Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

