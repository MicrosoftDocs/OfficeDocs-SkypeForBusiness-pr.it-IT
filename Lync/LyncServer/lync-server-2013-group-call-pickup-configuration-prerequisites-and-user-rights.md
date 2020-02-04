---
title: Prerequisiti e diritti utente della configurazione del prelievo delle chiamate di gruppo
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
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Prerequisiti e diritti utente della configurazione del prelievo delle chiamate di gruppo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Raccolta chiamate di gruppo è una caratteristica di gestione delle chiamate installata per impostazione predefinita quando si distribuisce VoIP aziendale. Questo argomento descrive le informazioni necessarie per configurare il prelievo delle chiamate di gruppo e i diritti utente necessari per eseguire le attività di configurazione.

In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa al ritiro delle chiamate di gruppo (vedere [pianificazione del ritiro delle chiamate di gruppo in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Prerequisiti per la configurazione del pickup delle chiamate di gruppo

Il ritiro delle chiamate di gruppo richiede i componenti seguenti:

  - Servizio applicazione

  - Applicazione Parcheggio di chiamata

Questi componenti vengono installati automaticamente quando si distribuisce VoIP aziendale.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Configurazione dei prelievo delle chiamate di gruppo diritti utente

Puoi usare gli strumenti di amministrazione seguenti per configurare il ritiro delle chiamate di gruppo:

  - Lync Server Management Shell

  - Strumento SEFAUtil Resource Kit

Usare Lync Server Management Shell per creare e gestire gruppi di pick-up delle chiamate nella tabella Orbit di Call Park. Usare lo strumento SEFAUtil Resource Kit per assegnare un gruppo di raccolta chiamate e abilitare il ritiro delle chiamate di gruppo per gli utenti o disabilitare il ritiro delle chiamate di gruppo per gli utenti.

La configurazione del ritiro delle chiamate di gruppo richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:

  - **CsVoiceAdministrator:** Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri relativi alla voce.

  - **CsUserAdministrator:** Questo ruolo di amministratore può abilitare il ritiro delle chiamate di gruppo per gli utenti. Questo ruolo di amministratore ha anche l'accesso alla visualizzazione di sola lettura a tutte le configurazioni vocali.

  - **CsServerAdministrator:** Questo ruolo di amministratore può gestire, monitorare e risolvere i problemi di server e servizi.

  - **CsAdministrator:** Questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.

<div>


> [!NOTE]
> Per informazioni dettagliate sui diritti amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



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

