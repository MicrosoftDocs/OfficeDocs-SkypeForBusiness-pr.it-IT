---
title: "Lync Server 2013: Panoramica dell'ambiente ibrido di Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32132faee3b52140d20a7f01e6a0bad0e88c620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Panoramica dell'ambiente ibrido di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-28_

L'ambiente ibrido di Lync Server 2013 si riferisce a una distribuzione in cui alcuni utenti sono ospitati in Lync Server 2013 locale e ad altri utenti ospitati in Lync Online, ma gli utenti condividono lo stesso dominio, ad esempio user@contoso.com.

<div>

## <a name="about-this-guide"></a>Informazioni su questa guida

In questa guida vengono descritte le attività necessarie per configurare l'ambiente Lync Server 2013 per l'interoperabilità con Lync Online e quindi per spostare gli utenti dalla distribuzione locale per l'utilizzo di Lync Online.

</div>

<div>

## <a name="prerequisites"></a>Prerequisiti

Per completare le attività di configurazione di una distribuzione ibrida, è necessario installare le applicazioni e le utilità seguenti. I programmi di installazione per questi file sono inclusi nei supporti di installazione forniti per la distribuzione, nonché nei collegamenti inclusi nell'elenco seguente.

  - [Active Directory Federation Services (ADFS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Strumento di sincronizzazione della directory Microsoft 9,1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Installazione di Windows PowerShell per Single Sign-on con AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - L'assistente per l'accesso ai Microsoft Online Services (Msoidcli-7.0. msi) è incluso nel programma di installazione desktop di Office 365, che può essere ottenuto dalla pagina dei download collegata dal portale di amministrazione di Office 365.

</div>

<div>

## <a name="administrator-credentials"></a>Credenziali di amministratore

Quando viene richiesto di fornire le credenziali di amministratore, utilizzare il nome utente e la password per l'account Administrator del tenant di Office 365. Queste credenziali vengono utilizzate anche quando si configura Active Directory Federation Services (AD FS) 2,0, la sincronizzazione della directory, il servizio Single Sign-on, la Federazione e lo spostamento degli utenti in Lync Online.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Connessione a PowerShell di Lync Online

Gli amministratori hanno ora la possibilità di utilizzare Windows PowerShell per gestire Lync Online e gli account utente di Lync Online. A tale scopo, è innanzitutto necessario scaricare e installare il modulo di Lync Online Connector dall'area download Microsoft (http://go.microsoft.com/fwlink/?LinkId=294688). Per ulteriori informazioni sul download, l'installazione e l'utilizzo del modulo di Lync Online Connector e per informazioni dettagliate sull'utilizzo di Windows PowerShell per la gestione di Lync Online, vedere [utilizzo di Windows PowerShell per gestire Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>

