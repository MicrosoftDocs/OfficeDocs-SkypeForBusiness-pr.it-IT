---
title: Prerequisiti di configurazione e sicurezza per VoIP aziendale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d06cdb4c679d1a40eb5c6fa0e8cf837ec8d2e332
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Prerequisiti per la sicurezza e la configurazione di Enterprise Voice in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Verificare che l'infrastruttura soddisfi i prerequisiti hardware specifici per la sicurezza, la configurazione degli utenti e gli scenari.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Diritti amministrativi e infrastruttura dei certificati

Assicurarsi che l'ambiente sia configurato con i gruppi di utenti amministrativi e l'infrastruttura di certificato seguenti per l'uso durante il processo di distribuzione vocale aziendale.

  - Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.

  - Gli amministratori che eseguono le attività di configurazione devono avere diritti adeguati:
    
      - **CsVoiceAdministrator:** Questo ruolo di amministratore può eseguire attività di configurazione vocale, gestire le applicazioni vocali e assegnare criteri vocali agli utenti finali.
    
      - **CsUserAdministrator:** Questo ruolo di amministratore può gestire le proprietà degli utenti, ad esempio l'abilitazione di VoIP aziendale per un utente. Questo ruolo di amministratore può anche assegnare criteri per utente, ad eccezione dei criteri di archiviazione. trasferire utenti; e Gestisci telefoni per area comune e dispositivi analogici.
    
      - **CsAdministrator:** Questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.
    
    <div>
    

    > [!NOTE]
    > La delega consente a più amministratori di partecipare alla distribuzione di Lync Server senza aprire l'accesso non necessario alle risorse.

    
    </div>

  - L'infrastruttura MKI (Managed Key Infrastructure) viene distribuita e configurata tramite un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.
    
    <div>
    

    > [!NOTE]
    > Per informazioni dettagliate sui requisiti dei certificati in Lync Server, vedere <A href="lync-server-2013-certificate-infrastructure-requirements.md">requisiti per l'infrastruttura dei certificati per Lync server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Configurazione utente

Se il Mediation Server è stato collocato con ogni pool Front end o server Standard Edition durante la distribuzione front-end, le impostazioni utente necessarie per Enterprise Voice sono state configurate automaticamente durante l'installazione dei file per i ruoli del server.

Se si sta distribuendo di nuovo il carico di lavoro VoIP aziendale in questo momento, prima di iniziare il processo di distribuzione, designare un numero di telefono principale per ogni utente che si prevede di abilitare per VoIP aziendale. Come amministratore, sei responsabile per verificare che questo numero sia univoco. Prima dell'implementazione, tutti i numeri di telefono primari devono essere normalizzati (formattati correttamente) e copiati nella proprietà **URI della linea** di ogni utente usando il pannello di controllo di Lync Server.

<div>


> [!NOTE]
> Per gli esempi di numeri di telefono principali necessari per la distribuzione di VoIP aziendale, vedere le <A href="lync-server-2013-dial-plans-and-normalization-rules.md">regole di dial plan e normalizzazione nella sezione Lync server 2013</A> di <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plan e regole di normalizzazione in Lync Server 2013</A> nella documentazione relativa alla pianificazione.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Passaggi successivi: installare i file o configurare la connettività PSTN

Dopo aver verificato il software e i prerequisiti ambientali per Enterprise Voice, è possibile usare il contenuto seguente per:

  - Installare il Mediation Server, come descritto in [installare i file per Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), ma solo se si vuole distribuire un server o un pool di mediazione autonomo perché i server di mediazione vengono installati come parte del pool di front-end o del processo di distribuzione del server standard in una posizione collocata.

  - In alternativa, iniziare la configurazione delle impostazioni per instradare le chiamate per gli utenti di VoIP aziendale, come descritto in [configurazione di Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

