---
title: "Lync Server 2013: configurazione del supporto per l'accesso degli utenti esterni"
description: "Lync Server 2013: configurazione del supporto per l'accesso degli utenti esterni."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5a91f9b285a80ff6a0f3c58c2c12f88d72aac98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556892"
---
# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

La distribuzione di un server perimetrale o di un pool di server perimetrali è il primo passaggio per il supporto degli utenti esterni. Per informazioni dettagliate sulla distribuzione di server perimetrali, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione. Per configurare i criteri, è necessario conoscere la precedenza dei criteri e come questi ultimi vengono applicati. Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.

Dopo aver completato l'installazione di un server perimetrale o di un pool di server perimetrali, è necessario abilitare i tipi di accesso per gli utenti esterni che si desidera fornire e configurare le impostazioni per l'accesso esterno. In Lync Server 2013, è possibile abilitare e configurare l'accesso e i criteri per gli utenti esterni utilizzando il pannello di controllo di Lync Server, Lync Server Management Shell o entrambi, in base ai requisiti di attività.

Per supportare l'accesso utente esterno, è necessario eseguire entrambe le operazioni seguenti:

  - **Abilitare il supporto per l'organizzazione**     Per abilitare il supporto per l'accesso degli utenti esterni nella distribuzione, è possibile abilitare ogni tipo di accesso esterno che si desidera supportare. È possibile abilitare e disabilitare il supporto per l'accesso degli utenti esterni modificando le impostazioni globali o creando e configurando un criterio sito o utente nella pagina **criteri di accesso esterno** del gruppo **federativo e accesso esterno** del pannello di controllo di Lync Server oppure utilizzando Lync Server Management Shell e i cmdlet associati. I cmdlet per la gestione dei **criteri di accesso esterno** sono disponibili nell'argomento [Federation and External Access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). Abilitazione del supporto per l'accesso esterno specifica che i server che eseguono il servizio Lync Server Access Edge supportano le comunicazioni con utenti e server esterni. Gli utenti interni ed esterni non sono in grado di comunicare quando l'accesso degli utenti esterni è disabilitato o se i criteri non sono ancora stati configurati per supportarlo.

  - **Configurazione e assegnazione di uno o più criteri**     Per supportare l'accesso degli utenti esterni, è necessario configurare i criteri per soddisfare i requisiti che includono:
    
      - Criteri di accesso **esterno**     Creato con un ambito di sito o utente (un criterio globale esiste per impostazione predefinita e non dispone di impostazioni abilitate). È possibile creare e configurare criteri per controllare l'utilizzo di uno o più tipi di accesso utente esterno, incluso l'accesso utente federato (inclusi, se selezionati, domini XMPP federati) gli utenti remoti e i provider di servizi di messaggistica istantanea pubblica supportati. È possibile configurare i criteri esterni nel pannello di controllo di Lync Server utilizzando il criterio globale o uno o più criteri di sito e utente creati amministrativamente, nella pagina **criteri di accesso esterno** del gruppo **Federazione e accesso esterno** . I criteri globali non possono essere eliminati. È possibile creare e configurare tutti i criteri di sito e utente che si desidera utilizzare per limitare l'accesso degli utenti esterni per siti specifici. I criteri globali e di sito vengono assegnati automaticamente. Se si crea e si configura un criterio utente, è necessario assegnarlo agli utenti specifici utilizzando la pagina Configurazione utente nel pannello di controllo di Lync Server nella pagina **utenti** . Individuare l'utente o gli utenti a cui si desidera applicare il criterio e assegnare il criterio. a cui si desidera applicare l'applicazione. Per assegnare un criterio utente configurato a un utente, vedere [assegnare un criterio di accesso utente esterno a un utente abilitato per Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Ogni criterio di accesso utente esterno è in grado di supportare una o più delle operazioni seguenti: accesso utente remoto, accesso utente federato SIP, accesso utente federato XMPP e connettività per messaggistica istantanea pubblica.
    
      - **Criteri**     di conferenza È possibile creare e configurare criteri per il controllo delle conferenze nell'organizzazione, tra cui gli utenti dell'organizzazione possono invitare gli utenti anonimi alle conferenze che ospitano. Nella pagina **conferenza** del pannello di controllo di Lync Server sono disponibili impostazioni dei criteri nell'ambito globale, del sito e dell'utente che controllano le impostazioni per le conferenze effettive. Per informazioni dettagliate, vedere [Managing Meetings and conferences in Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Nella pagina **Configurazione Access Edge** abilitare gli utenti anonimi, gli utenti remoti e gli utenti federati per i servizi di conferenza. I criteri nella pagina **Configurazione Access Edge** sono di ambito globale. Non sono presenti opzioni per definire criteri per siti o utenti. Controllare l'ambito nella pagina **Criteri di accesso esterno** mediante l'utilizzo delle impostazioni per i criteri di ambito globale, sito o utente.
        
        Se ad esempio si desidera consentire agli utenti di creare, invitare e gestire i servizi di conferenza con utenti remoti, impostare **Abilita comunicazioni con utenti remoti** nei criteri globali, di sito o utente **Criteri di accesso esterno** e **Abilita comunicazioni con utenti remoti** nella pagina **Configurazione Access Edge**. Analogamente, per consentire i servizi di conferenza con utenti anonimi o partner federati con cui è stata definita una relazione (ad esempio, provider e domini SIP federati configurati; la federazione di XMPP non supporta il servizio di conferenza), impostare **Abilita comunicazioni con utenti pubblici** e **Abilita comunicazioni con utenti federati** nei criteri globali, di sito o utente **Criteri di accesso esterno**. Selezionare quindi le impostazioni opzionali dei criteri globali **Abilita accesso utente anonimo per le conferenze** e **Abilita federazione e connettività di messaggistica istantanea pubblica** nella pagina **Configurazione Access Edge**.

È possibile configurare impostazioni di accesso utente esterno, includendo tutti i criteri che si desidera utilizzare per controllare l'accesso utente esterno, anche se l'accesso utente esterno non è stato abilitato per l'organizzazione. Tuttavia, i criteri e altre impostazioni configurati dall'utente hanno effetto solo quando l'accesso utente esterno è abilitato per l'organizzazione. Gli utenti esterni non possono comunicare con gli utenti dell'organizzazione quando l'accesso utente esterno è disabilitato o non sono configurati criteri di accesso utente esterno per supportarlo.

La distribuzione di server perimetrali autentica i tipi di utenti esterni (ad eccezione degli utenti anonimi che vengono autenticati mediante l'ID conferenza e una passkey inviati ai partecipanti anonimi quando si crea la conferenza e si invitano i partecipanti) e controlla l'accesso in base alla configurazione del supporto perimetrale. Per controllare le comunicazioni, è possibile configurare uno o più criteri e impostazioni che definiscono la modalità di comunicazione tra gli utenti all'interno e all'esterno della distribuzione. Tali criteri e impostazioni includono i criteri globali predefiniti per l'accesso degli utenti esterni, oltre ai criteri per siti e utenti che è possibile creare e configurare per abilitare uno o più tipi di accesso degli utenti esterni per siti o utenti specifici.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurazione di criteri per il controllo dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Abilitazione o disabilitazione dell'accesso degli utenti anonimi in Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

