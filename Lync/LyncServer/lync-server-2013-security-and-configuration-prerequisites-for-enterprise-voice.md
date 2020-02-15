---
title: Prerequisiti di configurazione e sicurezza per VoIP aziendale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4fb37047ec57d281e47d1c03c2f52ed455dcdf7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Prerequisiti di configurazione e sicurezza per VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

Verificare che l'infrastruttura soddisfi i prerequisiti di sicurezza, configurazione utente e hardware specifici dello scenario.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Diritti amministrativi e infrastruttura di certificazione

Verificare che nell'ambiente siano configurati i gruppi di utenti con privilegi amministrativi e l'infrastruttura di certificazione seguenti da utilizzare durante il processo di distribuzione di VoIP aziendale.

  - Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.

  - Gli amministratori che eseguono le attività di configurazione devono disporre di diritti appropriati:
    
      - **CsVoiceAdministrator:** questo ruolo di amministratore consente di eseguire attività di configurazione vocale, di gestire le applicazioni vocali e di assegnare criteri vocali agli utenti finali.
    
      - **CsUserAdministrator:** questo ruolo di amministratore consente di gestire le proprietà degli utenti, ad esempio l'abilitazione di VoIP aziendale per un utente. Consente inoltre di assegnare criteri per utente, ad eccezione del criterio di archiviazione, di spostare gli utenti e di gestire i telefoni di area comune e i dispositivi analogici.
    
      - **CsAdministrator:** questo ruolo di amministratore consente di eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.
    
    <div>
    

    > [!NOTE]
    > La delega consente a più amministratori di partecipare alla distribuzione di Lync Server senza aprire un accesso non necessario alle risorse.

    
    </div>

  - La distribuzione e la configurazione dell'infrastruttura MKI (Managed Key Infrastructure) vengono eseguite utilizzando un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.
    
    <div>
    

    > [!NOTE]
    > Per informazioni dettagliate sui requisiti dei certificati in Lync Server, vedere <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate Infrastructure requirements for Lync server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Configurazione utente

Se il Mediation Server è stato collocato con ogni pool Front end o server Standard Edition durante la distribuzione front-end, le impostazioni utente necessarie per VoIP aziendale sono state configurate automaticamente durante l'installazione dei file per i ruoli del server.

Se si sta procedendo ora alla distribuzione del carico di lavoro di VoIP aziendale, prima di iniziare il processo di distribuzione designare un numero di telefono primario per ogni utente che si intende abilitare per VoIP aziendale. In qualità di amministratori, è necessario verificare che questo numero sia univoco. Prima dell'implementazione, tutti i numeri di telefono primari devono essere normalizzati (formattati correttamente) e copiati nella proprietà **URI di linea** di ogni utente utilizzando il pannello di controllo di Lync Server.

<div>


> [!NOTE]
> Per esempi di numeri di telefono primari necessari per la distribuzione di VoIP aziendale, vedere le <A href="lync-server-2013-dial-plans-and-normalization-rules.md">regole di dial plan e di normalizzazione in Lync server 2013</A> sezione dei <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plan e delle regole di normalizzazione in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Passaggi successivi: installare i file o configurare la connettività PSTN

Dopo avere verificato i prerequisiti software e ambientali per VoIP aziendale, è possibile utilizzare il contenuto seguente per eseguire una delle operazioni indicate di seguito:

  - Installare il Mediation Server, come descritto in [Install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), ma solo se si desidera distribuire un Mediation Server autonomo o un pool perché i Mediation Server vengono installati come parte del pool Front end o del processo di distribuzione del server Standard Edition durante la collocazione.

  - In alternativa, iniziare a configurare le impostazioni per instradare le chiamate per gli utenti di VoIP aziendale, come descritto in [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

