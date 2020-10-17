---
title: 'Lync Server 2013: prerequisiti per la configurazione del parcheggio di chiamata e diritti utente'
description: 'Lync Server 2013: prerequisiti per la configurazione del parcheggio di chiamata e diritti utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01187ad32fa7338765c0fa5b409b4e185e8ad35
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563532"
---
# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Requisiti di configurazione del parcheggio di chiamata e diritti utente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-10_

Il parcheggio di chiamata è una funzionalità di gestione delle chiamate installata per impostazione predefinita quando si distribuisce VoIP aziendale. In questo argomento vengono descritte le operazioni necessarie per poter configurare il parcheggio di chiamata e i diritti utente necessari per eseguire le attività di configurazione.

<div>


> [!IMPORTANT]  
> I file musicali personalizzati per l'applicazione Parcheggio di chiamata non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e i file andranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati. Mantenere sempre una copia di backup distinta dei file di musica di attesa personalizzati caricati per il parcheggio chiamate.



</div>

In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa al parcheggio di chiamata (vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Prerequisiti per la configurazione del parcheggio di chiamata

Il parcheggio di chiamata richiede i componenti seguenti:

  - Servizio dell'applicazione

  - Applicazione Parcheggio di chiamata

Questi componenti vengono installati automaticamente quando si distribuisce VoIP aziendale.

Se si desidera che i chiamanti ascoltino musica nell'intervallo di tempo in cui la chiamata è parcheggiata, sarà necessario inoltre un file di musica di attesa. Quando si distribuisce VoIP aziendale, viene installato automaticamente un file di musica di attesa predefinito. È possibile sostituire il file predefinito con un proprio file di musica di attesa. Il parcheggio di chiamata utilizza l'archivio file per contenere il file audio.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Configurazione del parcheggio di chiamata diritti utente

È possibile utilizzare gli strumenti di amministrazione seguenti per configurare il parcheggio di chiamata:

  - Pannello di controllo di Lync Server

  - Lync Server Management Shell

È possibile utilizzare questi strumenti per configurare la tabella di orbit del parcheggio di chiamata e per la configurazione di altre impostazioni utilizzate dal parcheggio di chiamata.

La configurazione del parcheggio di chiamata richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:

  - **CsVoiceAdministrator:** Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri vocali.

  - **CsUserAdministrator:** Questo ruolo di amministratore può abilitare il parcheggio di chiamata nel criterio vocale. Dispone inoltre dell'accesso per la visualizzazione di sola lettura di tutte le configurazioni vocali.

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

