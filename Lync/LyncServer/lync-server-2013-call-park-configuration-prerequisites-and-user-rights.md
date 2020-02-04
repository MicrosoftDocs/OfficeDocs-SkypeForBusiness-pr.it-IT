---
title: 'Lync Server 2013: Diritti utente e prerequisiti per la configurazione del parcheggio di chiamata'
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
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Diritti utente e prerequisiti per la configurazione del parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-10_

Call Park è una caratteristica di gestione delle chiamate che viene installata per impostazione predefinita quando si distribuisce VoIP aziendale. Questo argomento descrive le informazioni necessarie per configurare Call Park e i diritti utente necessari per eseguire le attività di configurazione.

<div>


> [!IMPORTANT]  
> I file musicali personalizzati per l'applicazione Parcheggio di chiamata non vengono sottoposto a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e i file andranno perduti se i file caricati nel pool sono danneggiati, danneggiati o eliminati. Mantieni sempre una copia di backup separata dei file personalizzati di musica in attesa caricati per Call Park.



</div>

In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa a Call Park (vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Prerequisiti per la configurazione di Call Park

Call Park richiede i componenti seguenti:

  - Servizio applicazione

  - Applicazione Parcheggio di chiamata

Questi componenti vengono installati automaticamente quando si distribuisce VoIP aziendale.

Se si vuole che i chiamanti ascoltino musica mentre la chiamata è parcheggiata, è necessario anche un file di musica in attesa. Un file predefinito per la musica in attesa viene installato automaticamente quando si distribuisce VoIP aziendale. Puoi sostituire il file predefinito con il tuo file di musica in blocco. Call Park USA file Store per contenere il file audio.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Configurazione di Call Park diritti utente

Puoi usare gli strumenti di amministrazione seguenti per configurare Call Park:

  - Pannello di controllo di Lync Server

  - Lync Server Management Shell

Puoi usare questi strumenti per configurare la tabella Orbit di Call Park e la configurazione di altre impostazioni usate da Call Park.

La configurazione di Call Park richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:

  - **CsVoiceAdministrator:** Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri relativi alla voce.

  - **CsUserAdministrator:** Questo ruolo di amministratore può abilitare il parcheggio delle chiamate nel criterio vocale. Questo ruolo di amministratore ha anche l'accesso alla visualizzazione di sola lettura a tutte le configurazioni vocali.

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

