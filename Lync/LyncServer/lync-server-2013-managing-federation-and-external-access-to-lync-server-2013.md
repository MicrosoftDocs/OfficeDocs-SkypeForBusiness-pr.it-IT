---
title: "Lync Server 2013: Gestione della federazione e dell'accesso esterno a Lync Server 2013"
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
ms.openlocfilehash: 9dadc455389d95c91996b75928def8f03b06c64e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Gestione della federazione e dell'accesso esterno a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

La distribuzione di un Edge Server o di un pool di Edge è il primo passo per supportare utenti esterni. Per informazioni dettagliate sulla distribuzione di Edge Server, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione.

Dopo l'installazione e la configurazione della distribuzione interna di Lync Server 2013, gli utenti interni dell'organizzazione possono collaborare con altri utenti interni che dispongono di account SIP in servizi di dominio Active Directory. La collaborazione può includere l'invio e la ricezione di messaggi istantanei e l'aggiornamento dello stato presenza e la partecipazione a conferenze (note anche come "riunioni"). Puoi abilitare e configurare l'accesso degli utenti esterni per controllare se gli utenti esterni supportati possono collaborare con gli utenti interni di Lync Server. Gli utenti esterni possono includere utenti remoti della distribuzione, utenti federati (inclusi gli utenti supportati dei provider di servizi di messaggistica istantanea pubblici), la Federazione XMPP e i partecipanti anonimi alle conferenze.

Se la distribuzione include l'installazione di un server perimetrale Lync Server 2013 o di un pool di Edge, l'ambito dei possibili tipi di comunicazione è notevolmente ampliato con una serie di opzioni per l'accesso degli utenti esterni, la comunicazione con i membri di altri domini federati SIP. SIP provider federati e utenti federati XMPP. Dopo aver configurato il server perimetrale o il pool di Edge, è possibile abilitare i tipi di accesso utente esterno che si desidera specificare e configurare i criteri per il controllo dell'accesso esterno. In Lync Server 2013 è possibile abilitare e configurare l'accesso e i criteri degli utenti esterni usando il pannello di controllo di Lync Server, Lync Server Management Shell o entrambi, in base ai requisiti di attività. Per informazioni dettagliate su questi strumenti di gestione, vedere [strumenti di amministrazione di Lync server 2013](lync-server-2013-lync-server-administrative-tools.md) nella documentazione sulle operazioni, [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) nella documentazione sulle operazioni e [installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md) nella documentazione Operations.

<div>


> [!IMPORTANT]  
> Quando si progetta la configurazione e i criteri per l'accesso degli utenti esterni, è necessario comprendere la precedenza dei criteri e il modo in cui vengono applicati i criteri. Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.



</div>

Per impostazione predefinita, nessun criterio è configurato per supportare l'accesso degli utenti esterni, incluso l'accesso degli utenti remoti, l'accesso degli utenti federati, anche se è già stato abilitato il supporto per l'accesso degli utenti esterni per l'organizzazione. Per controllare l'uso dell'accesso degli utenti esterni, è necessario configurare uno o più criteri, specificando il tipo di accesso utente esterno supportato per ogni criterio. Sono inclusi i seguenti criteri di accesso esterno:

  - **Criteri globali il**   criterio globale viene creato quando si distribuisce un server perimetrale. Per impostazione predefinita, nel criterio globale non sono abilitate le opzioni di accesso degli utenti esterni. Per supportare l'accesso degli utenti esterni a livello globale, è possibile configurare il criterio globale per supportare uno o più tipi di opzioni di accesso degli utenti esterni. Il criterio globale si applica a tutti gli utenti dell'organizzazione, ma i criteri del sito e i criteri degli utenti eseguono l'override del criterio globale. Se elimini il criterio globale, non lo Rimuovi. Puoi invece reimpostarla sull'impostazione predefinita.

  - **Criteri sito è**   possibile creare e configurare uno o più criteri del sito per limitare il supporto per l'accesso degli utenti esterni a siti specifici. La configurazione dei criteri sito ha la precedenza sui criteri globali, ma solo per il sito specifico a cui i criteri si riferiscono. Ad esempio, se si Abilita l'accesso degli utenti remoti nel criterio globale, è possibile specificare un criterio per il sito che disabilita l'accesso degli utenti remoti per un sito specifico. Per impostazione predefinita, un criterio del sito viene applicato a tutti gli utenti del sito, ma è possibile assegnare un criterio utente a un utente per ignorare l'impostazione dei criteri del sito.

  - **Criteri**   per gli utenti è possibile creare e configurare uno o più criteri utente per limitare il supporto per l'accesso degli utenti remoti a un utente specifico. La configurazione nel criterio utente sostituisce il criterio globale e del sito, ma solo per gli utenti specifici a cui è assegnato il criterio utente. Ad esempio, se si Abilita l'accesso degli utenti remoti nei criteri globali e nei criteri del sito, è possibile specificare un criterio utente che disabilita l'accesso degli utenti remoti e quindi assegnare i criteri utente a utenti specifici. Se crei un criterio utente, devi applicarlo a uno o più utenti prima che abbia effetto.

Per determinare le impostazioni di configurazione e i criteri necessari per la creazione o la modifica, vedere i punti decisionali seguenti:

**Si vuole consentire agli utenti interni ed esterni del proprio dominio di collaborare usando la messaggistica istantanea, le conferenze Web e l'audio/video?**

Configurare le impostazioni come descritto in dettaglio negli argomenti [configurare i criteri per controllare l'accesso degli utenti remoti in Lync server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)e [abilitare o disabilitare la connettività di messaggistica istantanea pubblica e della Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Si vuole consentire agli utenti anonimi di partecipare ed essere invitati a conferenze ospitate dagli utenti nella distribuzione?**

Configurare le impostazioni come descritto nell'argomento [assegnare criteri di conferenza per supportare gli utenti anonimi in Lync server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [creare o modificare criteri di conferenza in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) e informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**Si vuole consentire agli utenti di comunicare con i contatti di dominio federato SIP?**

Configurare le impostazioni come descritto negli argomenti [configurare i criteri per controllare l'accesso degli utenti federati in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [abilitare o disabilitare la connettività di messaggistica istantanea e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)e [gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Se è stata abilitata la comunicazione con i domini federativi SIP, si desidera abilitare le comunicazioni con i contatti partner federativi XMPP?**

Configurare le impostazioni come descritto nell'argomento [configurare i criteri per controllare l'accesso degli utenti federati XMPP in Lync server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) e [gestire i partner federati XMPP in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Se è stata abilitata la comunicazione con i domini federati SIP, si vuole abilitare l'individuazione automatica della Federazione SIP?**

Configurare le impostazioni come descritto nell'argomento [abilitare o disabilitare l'individuazione dei partner federativi in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

**Se è stata abilitata la comunicazione con i domini federativi SIP, si vuole abilitare l'invio di una dichiarazione di non responsabilità ai contatti federati che informa che si usa l'archiviazione e che le comunicazioni possono essere archiviate?**

Configurare le impostazioni come descritto nell'argomento [abilitare o disabilitare l'invio di una dichiarazione di non responsabilità per l'archiviazione a partner federati in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Si vuole consentire agli utenti di comunicare con provider federati SIP che consentono la comunicazione con i provider pubblici, ad esempio Windows Live Messenger, AOL e Yahoo\!?**

Configurare le impostazioni come descritto negli argomenti [configurare i criteri per il controllo dell'accesso degli utenti pubblici in Lync server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[abilitare o disabilitare la connettività di messaggistica istantanea e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)e [creare o modificare provider federati pubblici SIP in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>



</div>

**Si vuole consentire agli utenti di comunicare con provider federati SIP ospitati in Microsoft Office 365, Microsoft Lync Online e Microsoft Lync Online 2010?**

Configurare le impostazioni come descritto negli argomenti [creare o modificare provider federati SIP pubblici in Lync server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [abilitare o disabilitare la connettività di messaggistica istantanea e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) e [creare o modificare i provider federati sip ospitati Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**La distribuzione è configurata in un dominio diviso (noto anche come ibrido), in cui alcuni utenti hanno il proprio server principale in una distribuzione locale e altri utenti sono configurati con un server principale in un ambiente online?**

Configurare le impostazioni come descritto negli argomenti [configurare i criteri per controllare l'accesso degli utenti federati in Lync server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [abilitare o disabilitare la connettività di messaggistica istantanea e la Federazione in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) e [creare o modificare i provider federati SIP ospitati Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

Se si preferisce una tabella in cui sono elencati i requisiti:


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
<th>Tab in Federazione e accesso esterno (Across) Federation o tipo di accesso esterno (in basso)</th>
<th>Criteri di accesso esterno</th>
<th>Configurazione di Access Edge</th>
<th>SIP domini federati</th>
<th>Provider federati SIP</th>
<th>Partner federato XMPP</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utenti remoti</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurare criteri per controllare l'accesso degli utenti remoti in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Abilitare o disabilitare l'accesso degli utenti remoti in Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP contatti federati</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurare criteri per controllare l'accesso utente federato in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Abilitare o disabilitare l'individuazione dei partner della federazione in Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Abilitare o disabilitare l'invio di una dichiarazione di non responsabilità relativa all'archiviazione ai partner federati in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contatti federati XMPP</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurare criteri per controllare l'accesso utente federato in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Gestire i partner federati XMPP per l'organizzazione in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Suddividere il dominio/utenti ibridi</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurare criteri per controllare l'accesso utente federato in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Creare o modificare provider federati SIP ospitati in Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Contatti del servizio di messaggistica istantanea pubblica</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configurare criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Creare o modificare provider federati SIP pubblici in Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Accesso degli utenti anonimi a riunioni e conferenze</p></td>
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


È possibile configurare le impostazioni di accesso degli utenti esterni, inclusi i criteri che si desidera utilizzare per controllare l'accesso degli utenti esterni, anche se non è stato abilitato l'accesso degli utenti esterni per l'organizzazione. Tuttavia, i criteri e le altre impostazioni configurate sono attivi solo quando si ha accesso utente esterno abilitato per l'organizzazione. Gli utenti esterni non possono comunicare con gli utenti dell'organizzazione quando l'accesso degli utenti esterni è disabilitato o se non sono configurati criteri di accesso degli utenti esterni per supportarlo.

La distribuzione di Edge esegue l'autenticazione dei tipi di utenti esterni (ad eccezione degli utenti anonimi, che vengono autenticati dall'ID conferenza e da una passkey inviata al partecipante anonimo quando si crea la conferenza e si invitano i partecipanti) e i controlli Access in base alla configurazione del supporto Edge. Per controllare le comunicazioni, è possibile configurare uno o più criteri e configurare le impostazioni che definiscono in che modo gli utenti all'interno e all'esterno della distribuzione comunicano tra loro. I criteri e le impostazioni includono il criterio globale predefinito per l'accesso degli utenti esterni, oltre ai criteri per il sito e l'utente che è possibile creare e configurare per consentire uno o più tipi di accesso utente esterno per siti o utenti specifici.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Gestire i criteri di accesso esterno per l'organizzazione in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Gestire la configurazione Access Edge per l'organizzazione in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Gestire i partner federati XMPP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Configurazione del supporto federativo per un cliente di Lync online in Lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

