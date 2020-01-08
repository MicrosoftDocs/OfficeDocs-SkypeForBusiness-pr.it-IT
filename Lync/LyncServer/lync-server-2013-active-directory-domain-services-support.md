---
title: 'Lync Server 2013: Supporto per Servizi di dominio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b264abefb1234892df355fee123dd6ce68b4dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Supporto per Servizi di dominio Active Directory in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

Lync Server 2013 usa l'Central Management store per archiviare i dati di configurazione per server e servizi, invece di affidarsi a servizi di dominio Active Directory per queste informazioni, come in passato. Lync Server 2013 archivia ancora le operazioni seguenti in servizi di dominio Active Directory:

  - **Estensioni dello schema**
    
      - Estensioni degli oggetti utente
    
      - Estensioni per le classi Lync Server 2010 e Office Communications Server 2007 R2 per mantenere la compatibilità con le versioni precedenti supportate

  - **Dati** (archiviati nello schema esteso di Lync Server 2013 e nelle classi esistenti)
    
      - URI SIP utente e altre impostazioni utente
    
      - Oggetti contatto per le applicazioni (ad esempio, l'applicazione Response Group e l'applicazione Operatore Conferenza)
    
      - Dati pubblicati per la compatibilità con le versioni precedenti
    
      - Un punto di controllo del servizio (SCP) per l'archivio di gestione centrale
    
      - Account di autenticazione Kerberos (un oggetto computer facoltativo)

In questa sezione vengono descritti i requisiti di supporto di servizi di dominio Active Directory per Lync Server 2013. Per informazioni dettagliate sul supporto delle topologie, vedere [topologie di Active Directory supportate in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) nella documentazione relativa alla supportabilità.

<div>

## <a name="supported-domain-controller-operating-systems"></a>Sistemi operativi supportati per domain controller

Lync Server 2013 supporta i controller di dominio che gestiscono i sistemi operativi seguenti:

  - Sistema operativo Windows Server 2012 R2

  - Sistema operativo Windows Server 2012

  - Sistema operativo Windows Server 2008 R2

  - Sistema operativo Windows Server 2008

  - Windows Server 2008 Enterprise 32 bit

  - Versioni di 32 bit o 64 del sistema operativo Window Server 2003 R2

  - Versioni di 32 bit o 64 del sistema operativo Windows Server 2003

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>Livello di funzionalità della foresta e del dominio

È necessario generare tutti i domini in cui si distribuisce Lync Server 2013 a un livello di funzionalità del dominio di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o almeno Windows Server 2003.

Tutte le foreste in cui si distribuisce Lync Server 2013 devono essere elevate a un livello di funzionalità della foresta di Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o almeno Windows Server 2003.

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>Supporto per i controller di dominio di sola lettura

Lync Server 2013 supporta distribuzioni di servizi di dominio Active Directory che includono controller di dominio di sola lettura o server di catalogo globale di sola lettura, purché siano disponibili controller di dominio scrivibili.

</div>

<div>

## <a name="domain-names"></a>Nomi di dominio

Lync Server non supporta i domini con etichetta singola. Ad esempio, è supportata una foresta con un dominio radice denominato **contoso. local** , ma un dominio radice denominato **local** non è supportato. Per informazioni dettagliate, vedere l'articolo 300684 della Microsoft Knowledge Base "informazioni sulla configurazione di Windows per i domini con nomi DNS con etichetta [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)singola".

<div>


> [!NOTE]  
> Lync Server non supporta la ridenominazione dei domini. Se è necessario rinominare un dominio in cui è distribuito Lync Server, è necessario prima disinstallare Lync Server, quindi rinominare il dominio e quindi reinstallare Lync Server.



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>Ambienti di servizi di dominio Active Directory bloccati

In un ambiente di servizi di dominio Active Directory bloccato gli utenti e gli oggetti computer vengono spesso collocati in unità organizzative specifiche con l'ereditarietà delle autorizzazioni disabilitata per proteggere la delega amministrativa e per consentire l'uso di oggetti Criteri di gruppo per l'applicazione criteri di sicurezza. Lync Server 2013 può essere distribuito in un ambiente Active Directory bloccato. Per informazioni dettagliate sulle informazioni necessarie per distribuire Lync Server in un ambiente bloccato, vedere Preparazione di [servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

