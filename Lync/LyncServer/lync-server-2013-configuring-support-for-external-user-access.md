---
title: "Lync Server 2013: Configurazione del supporto per l'accesso degli utenti esterni"
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
ms.openlocfilehash: 143e7e661f793f7a05cb2fdbad8cdab8acaf660e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Configurazione del supporto per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

La distribuzione di un Edge Server o di un pool di Edge è il primo passo per supportare utenti esterni. Per informazioni dettagliate sulla distribuzione di Edge Server, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione. Una considerazione importante per la configurazione dei criteri consiste nel comprendere la precedenza dei criteri e il modo in cui vengono applicati i criteri. Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.

Dopo aver completato la configurazione di un server perimetrale o di un pool di Edge, è necessario abilitare i tipi di accesso utente esterno che si desidera specificare e configurare le impostazioni per l'accesso esterno. In Lync Server 2013 è possibile abilitare e configurare l'accesso e i criteri degli utenti esterni usando il pannello di controllo di Lync Server, Lync Server Management Shell o entrambi, in base ai requisiti di attività.

Per supportare l'accesso degli utenti esterni, è necessario eseguire entrambe le operazioni seguenti:

  - **Abilitare il supporto per l'organizzazione**   per abilitare il supporto per l'accesso degli utenti esterni nella distribuzione, è possibile abilitare ogni tipo di accesso esterno che si vuole supportare. È possibile abilitare e disabilitare il supporto per l'accesso degli utenti esterni modificando le impostazioni globali o creando e configurando un sito o un criterio utente nella pagina dei **criteri di accesso esterno** nel gruppo **federativo e accesso esterno** del pannello di controllo di Lync Server o tramite Lync Server Management Shell e i cmdlet associati. I cmdlet per la gestione dei **criteri di accesso esterno** si trovano nell'argomento [Federazione e cmdlet di Access esterni in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). L'abilitazione del supporto per l'accesso esterno specifica che i server in cui è in uso Lync Server Access Edge supportano le comunicazioni con utenti e server esterni. Gli utenti interni ed esterni non possono comunicare mentre l'accesso degli utenti esterni è disabilitato o se i criteri non sono ancora stati configurati per supportarlo.

  - **Configurare e assegnare uno o più criteri**   per supportare l'accesso degli utenti esterni, configurare i criteri per l'indirizzo dei requisiti che includono:
    
      - **Criteri di accesso esterno**   creati con un ambito di un sito o un utente (un criterio globale esiste per impostazione predefinita e non ha impostazioni abilitate). Si creano e si configurano i criteri per controllare l'uso di uno o più tipi di accesso degli utenti esterni, inclusi l'accesso degli utenti federati, inclusi i domini XMPP selezionati, e i provider di servizi di messaggistica istantanea pubblici supportati. I criteri esterni vengono configurati nel pannello di controllo di Lync Server usando i criteri globali o uno o più criteri per il sito e gli utenti creati amministrativamente, nella pagina **criteri di accesso esterno** del gruppo **federativo e accesso esterno** . Non è possibile eliminare il criterio globale. Si creano e si configurano i criteri per il sito e gli utenti che si desidera utilizzare per limitare l'accesso degli utenti esterni a specifici siti. I criteri globali e di sito vengono assegnati automaticamente. Se si creano e si configura un criterio utente, è necessario assegnarlo agli utenti specifici usando la pagina Configurazione utente nel pannello di controllo di Lync Server nella pagina **utenti** . Individuare l'utente o gli utenti a cui si vuole applicare il criterio e assegnarlo. a cui si vuole applicare. Per assegnare un criterio utente configurato a un utente, vedere [assegnare un criterio di accesso utente esterno a un utente abilitato a Lync in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Ogni criterio di accesso degli utenti esterni può supportare uno o più degli elementi seguenti: accesso utente remoto, accesso utente federato SIP, accesso degli utenti federati XMPP e connettività di messaggistica istantanea pubblica.
    
      - **Criteri di conferenza**   per la creazione e la configurazione dei criteri per il controllo delle conferenze nell'organizzazione, inclusi gli utenti dell'organizzazione che possono invitare utenti anonimi alle conferenze ospitate. Nella pagina dei servizi di **conferenza** del pannello di controllo di Lync Server sono presenti impostazioni dei criteri nell'ambito globale, del sito e dell'utente che controllano le impostazioni per le conferenze effettive. Per informazioni dettagliate, vedere [gestione di riunioni e conferenze in Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Gli utenti anonimi vengono abilitati per servizi di conferenza, utenti remoti e utenti federati nella pagina di **configurazione di Access Edge** . Il criterio della **configurazione di Access Edge** è globale nell'ambito. Non sono disponibili opzioni per definire un sito o un criterio utente. L'ambito è controllato nella pagina **criteri di accesso esterno** tramite l'uso di impostazioni globali, del sito o dei criteri utente.
        
        Ad esempio, se si vuole consentire agli utenti di creare, invitare e gestire servizi di conferenza con utenti remoti, è necessario impostare **Abilita comunicazioni con gli utenti remoti** nei criteri globali di **accesso esterno** , per il sito o per gli utenti e **abilitare le comunicazioni con gli utenti remoti** nella pagina di **configurazione di Access Edge** . Allo stesso modo, per consentire ai servizi di conferenza con utenti anonimi o partner federati di avere una relazione definita, ad esempio i provider e i domini SIP federati configurati, la Federazione XMPP non supporta le conferenze, è possibile impostare l' **Abilitazione delle comunicazioni con gli utenti pubblici** e **abilitare le comunicazioni con gli utenti federati** nel criterio globale, del sito o dell'utente dei **criteri di accesso esterno** . È quindi possibile selezionare impostazioni dei criteri globali gratuite **per consentire l'accesso degli utenti anonimi alle conferenze** e **abilitare la connettività di messaggistica istantanea federata e pubblica** nella pagina di **configurazione di Access Edge** .

È possibile configurare le impostazioni di accesso degli utenti esterni, inclusi i criteri che si desidera utilizzare per controllare l'accesso degli utenti esterni, anche se non è stato abilitato l'accesso degli utenti esterni per l'organizzazione. Tuttavia, i criteri e le altre impostazioni configurate sono attivi solo quando si ha accesso utente esterno abilitato per l'organizzazione. Gli utenti esterni non possono comunicare con gli utenti dell'organizzazione quando l'accesso degli utenti esterni è disabilitato o se non sono configurati criteri di accesso degli utenti esterni per supportarlo.

La distribuzione di Edge esegue l'autenticazione dei tipi di utenti esterni (ad eccezione degli utenti anonimi, che vengono autenticati dall'ID conferenza e da una passkey inviata al partecipante anonimo quando si crea la conferenza e si invitano i partecipanti) e i controlli Access in base alla configurazione del supporto Edge. Per controllare le comunicazioni, è possibile configurare uno o più criteri e configurare le impostazioni che definiscono in che modo gli utenti all'interno e all'esterno della distribuzione comunicano tra loro. I criteri e le impostazioni includono il criterio globale predefinito per l'accesso degli utenti esterni, oltre ai criteri per il sito e l'utente che è possibile creare e configurare per consentire uno o più tipi di accesso utente esterno per siti o utenti specifici.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurare criteri per controllare l'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Abilitare o disabilitare l'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Abilitare o disabilitare l'accesso degli utenti anonimi in Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

