---
title: 'Lync Server 2013: Prerequisiti e ruoli per la configurazione degli annunci'
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
ms.openlocfilehash: 42cbc1429d4e27ee172dc1dacf6b86fa6ac243d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Prerequisiti e ruoli per la configurazione degli annunci in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-25_

L'annuncio è una caratteristica di gestione delle chiamate vocali aziendali. Questo argomento descrive le informazioni necessarie prima di poter configurare l'annuncio e le assegnazioni di ruolo necessarie per eseguire attività di configurazione.

In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa all'annuncio (vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Prerequisiti per la configurazione degli annunci

L'applicazione di annuncio richiede i componenti seguenti:

  - Servizio applicazione

  - Response Group Application

  - Archivio file per contenere i file audio

Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Ruoli di configurazione degli annunci

È possibile usare gli strumenti di amministrazione seguenti per configurare gli annunci:

  - Pannello di controllo di Lync Server

  - Lync Server Management Shell

La configurazione dell'applicazione di annunci richiede uno dei ruoli amministrativi seguenti:

  - **CsVoiceAdministrator**   questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri relativi alla voce, incluse le impostazioni degli annunci.

  - **CsServerAdministrator**   questo ruolo di amministratore può gestire, monitorare e risolvere i problemi relativi a server e servizi e configurare tutte le impostazioni di annuncio.

  - **CsAdministrator**   questo ruolo di amministratore può eseguire tutte le attività amministrative e modificare tutte le impostazioni.

  - **CsViewOnlyAdministrator**   questo ruolo di amministratore può visualizzare la distribuzione per monitorare l'integrità della distribuzione.

<div>


> [!NOTE]  
> Per informazioni dettagliate sui diritti degli utenti amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



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

