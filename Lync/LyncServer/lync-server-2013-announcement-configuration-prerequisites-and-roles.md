---
title: 'Lync Server 2013: prerequisiti e ruoli per la configurazione degli annunci'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5dac5c800f2e11829940445f9ebfe28c1a95c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531693"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Prerequisiti e ruoli per la configurazione degli annunci in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-25_

Annuncio è una funzionalità di gestione delle chiamate vocali di VoIP aziendale. In questo argomento vengono descritte le operazioni necessarie per poter configurare l'annuncio e le assegnazioni di ruolo necessarie per eseguire le attività di configurazione.

In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa all'annuncio (vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Prerequisiti per la configurazione degli annunci

L'applicazione annuncio richiede i componenti seguenti:

  - Servizio applicazione

  - Applicazione Response Group

  - Archivio file, per la memorizzazione dei file audio

Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Ruoli di configurazione degli annunci

È possibile utilizzare gli strumenti di amministrazione seguenti per configurare gli annunci:

  - Pannello di controllo di Lync Server

  - Lync Server Management Shell

La configurazione dell'applicazione annuncio richiede uno dei ruoli amministrativi seguenti:

  - **CsVoiceAdministrator**     Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri vocali, incluse le impostazioni degli annunci.

  - **CsServerAdministrator**     Questo ruolo di amministratore può gestire, monitorare e risolvere i problemi relativi a server e servizi, nonché configurare tutte le impostazioni degli annunci.

  - **CsAdministrator**     Questo ruolo di amministratore è in grado di eseguire tutte le attività amministrative e di modificare tutte le impostazioni.

  - **CsViewOnlyAdministrator**     Questo ruolo di amministratore può visualizzare la distribuzione per monitorare l'integrità della distribuzione.

<div>


> [!NOTE]  
> Per informazioni dettagliate sui diritti utente amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di VoIP aziendale in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

