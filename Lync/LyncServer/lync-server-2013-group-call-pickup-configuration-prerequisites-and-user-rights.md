---
title: Prerequisiti e diritti utente per la configurazione del prelievo delle chiamate di gruppo
description: Prerequisiti di configurazione del prelievo delle chiamate di gruppo e diritti utente.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554452"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Prerequisiti di configurazione del prelievo delle chiamate di gruppo e diritti utente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Prelievo delle chiamate di gruppo è una funzionalità di gestione delle chiamate installata per impostazione predefinita quando si distribuisce VoIP aziendale. In questo argomento vengono descritte le operazioni necessarie per poter configurare il prelievo delle chiamate di gruppo e i diritti utente necessari per eseguire le attività di configurazione.

In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa al prelievo delle chiamate di gruppo (vedere [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Prerequisiti per la configurazione del prelievo delle chiamate di gruppo

Il prelievo delle chiamate di gruppo richiede i componenti seguenti:

  - Servizio dell'applicazione

  - Applicazione Parcheggio di chiamata

Questi componenti vengono installati automaticamente quando si distribuisce VoIP aziendale.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Configurazione del prelievo delle chiamate di gruppo diritti utente

È possibile utilizzare gli strumenti di amministrazione seguenti per configurare il prelievo delle chiamate di gruppo:

  - Lync Server Management Shell

  - Strumento del Resource Kit di SEFAUtil

Utilizzo di Lync Server Management Shell per la creazione e la gestione dei gruppi di prelievo delle chiamate nella tabella orbit del parcheggio di chiamata. Utilizzare lo strumento SEFAUtil Resource Kit per assegnare un gruppo di prelievo di chiamata e abilitare il prelievo delle chiamate di gruppo per gli utenti o per disabilitare il prelievo delle chiamate di gruppo per gli utenti

La configurazione del prelievo delle chiamate di gruppo richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:

  - **CsVoiceAdministrator:** Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri vocali.

  - **CsUserAdministrator:** Questo ruolo di amministratore può abilitare il prelievo delle chiamate di gruppo per gli utenti. Dispone inoltre dell'accesso per la visualizzazione di sola lettura di tutte le configurazioni vocali.

  - **CsServerAdministrator:** Questo ruolo di amministratore può gestire, monitorare e risolvere i problemi relativi a server e servizi.

  - **CsAdministrator:** Questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.

<div>


> [!NOTE]
> Per informazioni dettagliate sui diritti amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



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

