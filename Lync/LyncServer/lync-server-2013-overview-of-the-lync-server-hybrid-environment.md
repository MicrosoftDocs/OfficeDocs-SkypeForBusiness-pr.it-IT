---
title: "Lync Server 2013: Panoramica dell'ambiente ibrido di Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0420e4aaded9f5ae90d26c4cbdc176e7fb4c6bb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Panoramica dell'ambiente ibrido di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-28_

L'ambiente ibrido di Lync Server 2013 si riferisce a una distribuzione in cui ci sono alcuni utenti ospitati nel Lync Server 2013 locale e altri utenti ospitati in Lync Online, ma gli utenti condividono lo stesso dominio, ad esempio user@contoso.com.

<div>

## <a name="about-this-guide"></a>Informazioni su questa guida

Questa guida descrive le attività necessarie per configurare l'ambiente Lync Server 2013 per l'interoperabilità con Lync Online e quindi per trasferire gli utenti dalla distribuzione locale per l'uso di Lync Online.

</div>

<div>

## <a name="prerequisites"></a>Prerequisiti

Per completare le attività per la configurazione di una distribuzione ibrida, sarà necessario installare le applicazioni e le utilità seguenti. I programmi di installazione per questi file sono inclusi nel supporto di installazione fornito per la distribuzione, nonché nei collegamenti inclusi nell'elenco seguente.

  - [Active Directory Federation Services (AD FS) 2,0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Strumento di sincronizzazione di Microsoft Directory 9,1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Installare Windows PowerShell per Single Sign-on con ADFS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - L'assistente per l'accesso ai Microsoft Online Services (Msoidcli-7.0. msi) è incluso nella configurazione desktop di Office 365, che può essere ottenuta dalla pagina Download collegata dal portale di amministrazione di Office 365.

</div>

<div>

## <a name="administrator-credentials"></a>Credenziali di amministratore

Quando viene richiesto di specificare le credenziali di amministratore, usare il nome utente e la password per l'account di amministratore del tenant di Office 365. Queste credenziali verranno usate anche quando si configurano Active Directory Federation Services (AD FS) 2,0, la sincronizzazione della directory, Single Sign-on, Federation e lo spostamento di utenti in Lync Online.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Connessione a PowerShell di Lync Online

Gli amministratori hanno ora la possibilità di usare Windows PowerShell per gestire Lync Online e gli account utente di Lync Online. A tale scopo, è necessario prima di tutto scaricare e installare il modulo di Lync Online Connector dall'area downloadhttp://go.microsoft.com/fwlink/?LinkId=294688)Microsoft (. Per altre informazioni su come scaricare, installare e usare il modulo di Lync Online Connector e per informazioni dettagliate sull'uso di Windows PowerShell per la gestione di Lync Online, vedere [uso di Windows PowerShell per gestire Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>

