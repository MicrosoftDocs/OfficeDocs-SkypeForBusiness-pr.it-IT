---
title: 'Lync Server 2013: modifiche apportate dalla preparazione della foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef94ea82f31871cf90939aa25a130903f15ef756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Modifiche apportate dalla preparazione della foresta in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

Questa sezione descrive le impostazioni globali e gli oggetti e i gruppi di servizi e di amministrazione universali creati dal passaggio di preparazione della foresta.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Impostazioni globali e oggetti di Active Directory

Se si archiviano le impostazioni globali nel contenitore di configurazione, come nel caso di tutte le nuove distribuzioni di Lync Server 2013, la preparazione della foresta usa il contenitore di servizi esistente e aggiunge un oggetto\\ **servizio RTC** nell'oggetto Configuration Services. Sotto l'oggetto servizio RTC, la preparazione della foresta aggiunge un oggetto **Impostazioni globali** di tipo msRTCSIP-GlobalContainer. L'oggetto impostazioni globali contiene tutte le impostazioni applicabili alla distribuzione di Lync Server. Se si archiviano le impostazioni globali nel contenitore di sistema, la preparazione della foresta usa un contenitore Microsoft nel contenitore di sistema del dominio radice e un oggetto\\servizio RTC nell'oggetto Microsoft System.

La preparazione della foresta aggiunge anche un nuovo oggetto **msRTCSIP-Domain** per il dominio radice in cui viene eseguita la procedura.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Gruppi di amministrazione e servizio universale di Active Directory

La preparazione della foresta crea gruppi universali in base al dominio specificato e aggiunge voci di controllo di accesso (ACE) per questi gruppi. Questo passaggio crea i gruppi universali nei contenitori utente del dominio specificato.

I gruppi universali consentono agli amministratori di accedere e gestire le impostazioni e i servizi globali. La preparazione della foresta aggiunge i tipi di gruppi universali seguenti:

  - **Gruppi amministrativi questi**   gruppi definiscono i ruoli di amministratore per una rete Lync Server.

  - **Gruppi di infrastrutture**   questi gruppi conferiscono l'autorizzazione per accedere ad aree specifiche dell'infrastruttura di Lync Server. Funzionano come componenti di gruppi amministrativi. Non è consigliabile modificare questi gruppi né aggiungere utenti direttamente.

  - **Gruppi di servizi**   questi gruppi sono account di servizio necessari per accedere a vari servizi di Lync Server.

La tabella seguente descrive i gruppi amministrativi.

### <a name="administrative-groups-created-during-forest-preparation"></a>Gruppi amministrativi creati durante la preparazione della foresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo amministrativo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Consente ai membri di gestire le impostazioni del server e del pool, inclusi tutti i ruoli del server, le impostazioni globali e gli utenti.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Consente ai membri di gestire le impostazioni utente e di trasferire gli utenti da un server o da un pool a un altro.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Consente ai membri di leggere le impostazioni del server, del pool e dell'utente.</p></td>
</tr>
</tbody>
</table>


La tabella seguente descrive i gruppi di infrastrutture.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>Gruppi di infrastrutture creati durante la preparazione della foresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo infrastruttura</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Concede l'accesso in scrittura agli oggetti setting globali per Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Concede l'accesso in sola lettura agli oggetti setting globali per Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Concede l'accesso in sola lettura alle impostazioni utente di Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Concede l'accesso in sola lettura alle impostazioni di Lync Server. Questo gruppo non ha accesso alle impostazioni del livello del pool, solo alle impostazioni specifiche di un singolo server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Concede l'accesso in sola lettura alla configurazione di Lync Server e viene inserito nel gruppo amministratori locali degli appliance Survivable Branch durante l'installazione.</p></td>
</tr>
</tbody>
</table>


La tabella seguente descrive i gruppi di servizi.

### <a name="service-groups-created-during-forest-preparation"></a>Gruppi di servizi creati durante la preparazione della foresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo di servizi</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Include gli account di servizio usati per eseguire front end server e server Standard Edition. Questo gruppo consente ai server di accedere in lettura/scrittura alle impostazioni globali di Lync Server e agli oggetti utente di Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Include gli account di servizio usati per eseguire servizi di conferenza A/V, Web Services, Mediation Server, server di archiviazione e server di monitoraggio.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Include gli account di servizio usati per eseguire Lync Server Edge Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Include server che possono partecipare alla replica di Lync Server Central Management store.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Concede l'accesso in sola lettura alle impostazioni di Lync Server, ma consente la configurazione per l'installazione di una distribuzione Survivable Branch Server e Survivable Branch Appliance.</p></td>
</tr>
</tbody>
</table>


La preparazione della foresta aggiunge quindi gruppi di servizi e di amministrazione ai gruppi di infrastruttura appropriati, come indicato di seguito:

  - RTCUniversalServerAdmins viene aggiunto a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

  - RTCUniversalUserAdmins viene aggiunto come membro di RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

  - RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins vengono aggiunti come membri di RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

La preparazione della foresta crea inoltre i seguenti gruppi di controllo di accesso basati sui ruoli (RBAC):

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

Per informazioni dettagliate sui ruoli RBAC e sulle attività consentite per ognuna, vedere [pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.

La preparazione della foresta crea sia gli assi privati che quelli pubblici. Crea Ace private nel contenitore di impostazioni globali usato da Lync Server. Questo contenitore viene usato solo da Lync Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda di dove si archiviano le impostazioni globali. Le voci ACE pubbliche create dalla preparazione della foresta sono elencate nella tabella seguente.

### <a name="public-aces-created-by-forest-preparation"></a>Ace pubbliche create dalla preparazione della foresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Root Domain System container (non ereditato)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Contenitore di DisplaySpecifiers della configurazione di lettura (non ereditato)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>Le voci ACE non ereditate non consentono l'accesso agli oggetti figlio in questi contenitori. Le voci ACE ereditate concedono l'accesso agli oggetti figlio in questi contenitori.



</div>

Nel contenitore di configurazione, in contesto dei nomi di configurazione, la preparazione della foresta esegue le attività seguenti:

  - Aggiunge una voce **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** per la pagina delle **proprietà RTC** in attributi adminContextMenu e adminPropertyPages dello specificatore di visualizzazione della lingua per utenti, contatti e INETORGPERSON, ad esempio CN = user-Display, CN = 409, CN = DisplaySpecifiers.

  - Aggiunge un oggetto **RTCPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che si applica alle classi User e Contact.

  - Aggiunge un oggetto **RTCUserSearchPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che si applica alle classi User, Contact, ou e DomainDNS.

  - Aggiunge **msRTCSIP-PrimaryUserAddress** nell'attributo **Columns** di ogni specificatore di visualizzazione dell'unità organizzativa (ad esempio, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) e copia i valori dell'attributo **Columns** della visualizzazione predefinita, ad esempio CN = default-display, CN = 409, CN = DisplaySpecifiers.

  - Aggiunge gli attributi di filtro msRTCSIP **-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**e **msRTCSIP-UserEnabled** nell'attributo **nell'attributeDisplayNames** di ogni identificatore di visualizzazione della lingua per gli utenti, i contatti e gli oggetti InetOrgPerson, ad esempio in inglese: CN = user-Display, CN = 409, CN = DisplaySpecifiers.

</div>

</div>

<span> </span>

</div>

</div>

</div>

