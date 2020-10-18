---
title: "Lync Server 2013: gestione della Federazione e dell'accesso esterno a Lync Server 2013"
description: "Lync Server 2013: gestione della Federazione e dell'accesso esterno a Lync Server 2013."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d389c7490fd1884631ed2fc184d590eb42141b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574922"
---
# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Gestione della Federazione e dell'accesso esterno a Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

La distribuzione di un server perimetrale o di un pool di server perimetrali è il primo passaggio per il supporto degli utenti esterni. Per informazioni dettagliate sulla distribuzione di server perimetrali, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.

Dopo l'installazione e la configurazione della distribuzione interna di Lync Server 2013, gli utenti interni dell'organizzazione possono collaborare con altri utenti interni che dispongono di account SIP nei servizi di dominio Active Directory (AD DS). La collaborazione può includere l'invio e la ricezione di messaggi istantanei, l'aggiornamento delle informazioni sulla presenza e la partecipazione a conferenze, anche note come "riunioni". È possibile abilitare e configurare l'accesso utente esterno per controllare se gli utenti esterni supportati possono collaborare con gli utenti interni di Lync Server. Gli utenti esterni possono includere utenti remoti della propria distribuzione, utenti federati (inclusi utenti supportati dei provider di servizi di messaggistica istantanea pubblici), membri della federazione XMPP e partecipanti anonimi delle conferenze.

Se nella distribuzione è inclusa l'installazione di un server perimetrale di Lync Server 2013 o di un pool perimetrale, l'ambito dei possibili tipi di comunicazione è notevolmente esteso con una serie di opzioni per l'accesso degli utenti esterni, la comunicazione con i membri di altri domini federati SIP, i provider federati SIP e gli utenti federati XMPP. Dopo aver configurato il server perimetrale o il pool di Edge, è possibile abilitare i tipi di accesso utente esterno che si desidera fornire e configurare i criteri per il controllo dell'accesso esterno. In Lync Server 2013, è possibile abilitare e configurare l'accesso e i criteri per gli utenti esterni utilizzando il pannello di controllo di Lync Server, Lync Server Management Shell o entrambi, in base ai requisiti di attività. Per informazioni dettagliate su questi strumenti di gestione, vedere gli [strumenti di amministrazione di Lync server 2013](lync-server-2013-lync-server-administrative-tools.md) nella documentazione relativa alle operazioni, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) nella documentazione relativa alle operazioni e [installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md) nella documentazione relativa alle operazioni.

<div>


> [!IMPORTANT]  
> Quando si progettano la configurazione e i criteri per l'accesso utente esterno, è necessario conoscere la precedenza dei criteri e la modalità di applicazione degli stessi. Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.



</div>

Per impostazione predefinita, non vengono configurati criteri per supportare l'accesso utente esterno, incluso l'accesso di utenti remoti e di utenti federati, anche se il supporto dell'accesso utente esterno è già stato abilitato per l'organizzazione. Per controllare l'utilizzo dell'accesso utente esterno, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Sono inclusi i criteri di accesso esterno seguenti:

  - **Criteri globali**   I criteri globali vengono creati quando si distribuiscono i server Edge Server. Per impostazione predefinita, nei criteri globali non vengono abilitate opzioni di accesso per gli utenti esterni. Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare i criteri globali in modo da supportare uno o più tipi di opzioni di accesso degli utenti esterni. I criteri globali si applicano a tutti gli utenti dell'organizzazione, ma i criteri sito e i criteri utente sostituiscono i criteri globali. Se si eliminano i criteri globali, questi non vengono rimossi, ma ne vengono ripristinate le impostazioni predefinite.

  - **Criteri sito**   È possibile creare e configurare uno o più criteri sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito. Se ad esempio si abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio sito che disabilita l'accesso degli utenti remoti per un sito specifico. Per impostazione predefinita, un criterio sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione del criterio sito.

  - **Criteri utente**   È possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso degli utenti remoti a utenti specifici. La configurazione nel criterio utente ha la priorità sui criteri globale e sito, ma solo per gli utenti specifici a cui viene assegnato il criterio utente. Se ad esempio si abilita l'accesso degli utenti remoti nei criteri globale e sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare tale criterio utente a utenti specifici. Se si crea un criterio utente, è necessario applicarlo a uno o più utenti per renderlo effettivo.

Per stabilire quali impostazioni di configurazione e quali criteri è necessario creare o modificare, considerare gli aspetti seguenti:

**Si desidera offrire agli utenti interni ed esterni del dominio la possibilità di collaborare tramite le funzionalità di messaggistica istantanea, Web Conferencing e audio/video?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to Control Remote User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)e [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Si desidera consentire agli utenti anonimi di partecipare ed essere invitati a conferenze ospitate da utenti inclusi nella distribuzione?**

Configurare le impostazioni come descritto nell'argomento [assegnazione dei criteri di conferenza per supportare gli utenti anonimi in Lync server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [creare o modificare criteri di conferenza in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**Si desidera consentire agli utenti di comunicare con i contatti dei domini federati SIP?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to Control Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)e [gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Se le comunicazioni con i domini federati SIP sono state abilitate, si desidera abilitare le comunicazioni con i contatti dei partner federati XMPP?**

Configurare le impostazioni come descritto nell'argomento [Configure policies to Control XMPP federato accesso utente in Lync server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) e [gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Se è stata abilitata la comunicazione con i domini federati SIP, si desidera abilitare l'individuazione automatica della Federazione SIP?**

Configurare le impostazioni come descritto nell'argomento [abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Se le comunicazioni con i domini federati SIP sono state abilitate, si desidera abilitare l'invio di una dichiarazione di non responsabilità ai contatti federati per avvisarli che è in uso l'archiviazione e che le comunicazioni potrebbero essere archiviate?**

Configurare le impostazioni come descritto nell'argomento [abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione ai partner federati in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Si desidera consentire agli utenti di comunicare con i provider federati SIP che consentono la comunicazione con i provider pubblici, ad esempio Windows Live Messenger, AOL e Yahoo \! ?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to Control public User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)e [creare o modificare provider federati SIP pubblici in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>



</div>

**Si desidera consentire agli utenti di comunicare con i provider federati SIP che sono provider ospitati che eseguono Microsoft 365, Microsoft Lync Online e Microsoft Lync Online 2010?**

Configurare le impostazioni come descritto negli argomenti [creare o modificare provider federati SIP pubblici in Lync server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) e [creare o modificare provider federati sip ospitati Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**La distribuzione è configurata in un dominio suddiviso (anche detto ibrido), in cui il server principale di alcuni utenti si trova in una distribuzione locale mentre per altri utenti il server principale è configurato in un ambiente online?**

Configurare le impostazioni come descritto negli argomenti [Configure policies to Control Federated User Access in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) e [creare o modificare i provider federati SIP ospitati Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

Di seguito è riportata una tabella con l'elenco dei requisiti:


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Scheda in Federazione e accesso esterno (Across) Federation o tipo di accesso esterno (verso il basso)</th>
<th>Criteri di accesso esterno</th>
<th>Configurazione Access Edge</th>
<th>Domini federati SIP</th>
<th>Provider federati SIP</th>
<th>Partner federato XMPP</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utenti remoti</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurazione di criteri per il controllo dell'accesso degli utenti remoti in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Contatti federati SIP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione ai partner federati in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contatti federati XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Gestire i partner federati XMPP in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Utenti dominio suddiviso/ibrido</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creare o modificare provider federati SIP ospitati Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contatti servizi di messaggistica istantanea pubblici</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurazione di criteri per il controllo dell'accesso degli utenti pubblici in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Creare o modificare provider federati SIP pubblici in Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Accesso utente anonimo a riunioni e conferenze</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Assegnare i criteri di conferenza per supportare gli utenti anonimi in Lync Server 2013</a></p>
<div>

> [!NOTE]  
> È inoltre necessario prendere in considerazione le impostazioni di configurazione seguenti in criteri di conferenza: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">creare o modificare un criterio di conferenza in Lync server 2013</A> e informazioni <A href="lync-server-2013-conferencing-policy-settings-reference.md">di riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


È possibile configurare impostazioni di accesso utente esterno, includendo tutti i criteri che si desidera utilizzare per controllare l'accesso utente esterno, anche se l'accesso utente esterno non è stato abilitato per l'organizzazione. Tuttavia, i criteri e altre impostazioni configurati dall'utente hanno effetto solo quando l'accesso utente esterno è abilitato per l'organizzazione. Gli utenti esterni non possono comunicare con gli utenti dell'organizzazione quando l'accesso utente esterno è disabilitato o non sono configurati criteri di accesso utente esterno per supportarlo.

La distribuzione di server perimetrali autentica i tipi di utenti esterni (ad eccezione degli utenti anonimi che vengono autenticati mediante l'ID conferenza e una passkey inviati ai partecipanti anonimi quando si crea la conferenza e si invitano i partecipanti) e controlla l'accesso in base alla configurazione del supporto perimetrale. Per controllare le comunicazioni, è possibile configurare uno o più criteri e impostazioni che definiscono la modalità di comunicazione tra gli utenti all'interno e all'esterno della distribuzione. Tali criteri e impostazioni includono i criteri globali predefiniti per l'accesso degli utenti esterni, oltre ai criteri per siti e utenti che è possibile creare e configurare per abilitare uno o più tipi di accesso degli utenti esterni per siti o utenti specifici.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Gestire i criteri di accesso esterno in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Gestire la configurazione di Access Edge per l'organizzazione in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configurazione del supporto federativo per un cliente di Lync online in Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

