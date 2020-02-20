---
title: 'Lync Server 2013: modifiche apportate dalla preparazione della foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 709263aeffe1a8681275d943da702242944868b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Modifiche apportate dalla preparazione della foresta in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-30_

In questa sezione vengono descritti gli oggetti e le impostazioni globali e i gruppi amministrativi e di servizio universali creati durante il passaggio di preparazione della foresta.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Oggetti e impostazioni globali di Active Directory

Se si archiviano le impostazioni globali nel contenitore di configurazione (come nel caso di tutte le nuove distribuzioni di Lync Server 2013), la preparazione della foresta utilizza il contenitore dei servizi esistente e aggiunge un\\oggetto **RTC Service** nell'oggetto Configuration Services. Nell'oggetto RTC Service viene aggiunto per la preparazione della foresta un oggetto **Global Settings** di tipo msRTCSIP-GlobalContainer. L'oggetto Global Settings contiene tutte le impostazioni che si applicano alla distribuzione di Lync Server. Se si archiviano le impostazioni globali nel contenitore di sistema, la preparazione della foresta utilizza un contenitore Microsoft nel contenitore del sistema del dominio radice e un oggetto\\RTC Service nell'oggetto System Microsoft.

Durante la preparazione della foresta viene aggiunto inoltre un nuovo oggetto **msRTCSIP-Domain** per il dominio radice in cui viene eseguita la procedura.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Gruppi amministrativi e di servizio universali di Active Directory

Durante la preparazione della foresta vengono creati gruppi universali basati sul dominio specificato e vengono aggiunte voci di controllo di accesso (ACE) per tali gruppi. Durante questo passaggio vengono creati i gruppi universali nei contenitori User del dominio specificato.

I gruppi universali consentono agli amministratori di accedere ai servizi e alle impostazioni globali e di gestirli. Per la preparazione della foresta vengono aggiunti i tipi di gruppi universali seguenti:

  - **Gruppi amministrativi questi**   gruppi definiscono i ruoli di amministratore per una rete di Lync Server.

  - **Gruppi di infrastruttura**   questi gruppi forniscono le autorizzazioni per accedere a aree specifiche dell'infrastruttura di Lync Server. Funzionano come componenti di gruppi amministrativi. Non modificare questi gruppi né aggiungervi direttamente gli utenti.

  - **Gruppi di servizi**   questi gruppi sono account di servizio necessari per accedere ai diversi servizi di Lync Server.

Nella tabella riportata di seguito vengono descritti i gruppi amministrativi.

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
<td><p>Consente ai membri di gestire le impostazioni di server e pool, inclusi tutti gli utenti, le impostazioni globali e i ruoli del server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Consente ai membri di gestire le impostazioni utente e di spostare gli utenti da un server o da un pool a un altro.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Consente ai membri di leggere le impostazioni di server, pool e utenti.</p></td>
</tr>
</tbody>
</table>


Nella tabella riportata di seguito vengono descritti i gruppi di infrastruttura.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>Gruppi di infrastruttura creati durante la preparazione della foresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo di infrastruttura</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Concede l'accesso in scrittura a oggetti setting globali per Lync Server.</p></td>
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
<td><p>Concede l'accesso in sola lettura alle impostazioni di Lync Server. Questo gruppo non dispone dell'accesso alle impostazioni a livello di pool, ma solo a quelle specifiche di un singolo server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Concede l'accesso in sola lettura alla configurazione di Lync Server e viene inserito nel gruppo Administrators locale di Survivable Branch Appliances durante l'installazione.</p></td>
</tr>
</tbody>
</table>


Nella tabella riportata di seguito vengono descritti i gruppi di servizio.

### <a name="service-groups-created-during-forest-preparation"></a>Gruppi di servizio creati durante la preparazione della foresta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo di servizio</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Include gli account di servizio utilizzati per l'esecuzione di front end server e server Standard Edition. Questo gruppo consente ai server di accedere in lettura/scrittura alle impostazioni globali di Lync Server e agli oggetti utente di Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Include gli account di servizio utilizzati per l'esecuzione di A/V Conferencing Server, servizi Web, Mediation Server, server di archiviazione e Monitoring Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Include gli account di servizio utilizzati per eseguire i server perimetrali di Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Include i server che possono partecipare alla replica dell'archivio di gestione centrale di Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Concede l'accesso in sola lettura alle impostazioni di Lync Server, ma consente la configurazione per l'installazione di una distribuzione Survivable Branch Server e Survivable Branch Appliance.</p></td>
</tr>
</tbody>
</table>


Durante la preparazione della foresta vengono quindi aggiunti i gruppi amministrativi e di servizio ai gruppi di infrastruttura appropriati, come indicato di seguito:

  - RTCUniversalServerAdmins viene aggiunto a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

  - RTCUniversalUserAdmins viene aggiunto come membro di RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

  - RTCHSUniversalServices, RTCComponentUniversalServices e RTCUniversalReadOnlyAdmins vengono aggiunti come membri di RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup e RTCUniversalUserReadOnlyGroup.

Durante la preparazione della foresta vengono creati inoltre i gruppi di controllo dell'accesso basato sui ruoli seguenti:

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

Per informazioni dettagliate sui ruoli RBAC e sulle attività consentite per ognuno di essi, vedere [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) nella documentazione relativa alla pianificazione.

Durante la preparazione della foresta vengono create voci di controllo di accesso private e pubbliche. Crea voci ACE private nel contenitore delle impostazioni globali utilizzato da Lync Server. Questo contenitore viene utilizzato solo da Lync Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda della posizione in cui vengono archiviate le impostazioni globali. Le voci di controllo di accesso pubbliche create durante la preparazione della foresta sono elencate nella tabella seguente.

### <a name="public-aces-created-by-forest-preparation"></a>Voci di controllo di accesso pubbliche create durante la preparazione della foresta

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
<td><p>Lettura del contenitore System del dominio radice (non ereditata)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Lettura del contenitore DisplaySpecifiers della configurazione (non ereditata)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>Le voci ACE non ereditate non consentono di accedere agli oggetti figlio in questi contenitori. Alle voci di controllo di accesso ereditate viene concesso l'accesso agli oggetti figlio presenti in tali contenitori.



</div>

Nel contesto dei nomi di configurazione all'interno del contenitore Configuration durante la preparazione della foresta vengono eseguite le attività seguenti:

  - Aggiunta di una voce **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** per la pagina della proprietà **RTC** negli attributi adminContextMenu e adminPropertyPages dell'identificatore di visualizzazione lingua per gli oggetti User, Contact e InetOrgPerson, ad esempio, CN=user-Display,CN=409,CN=DisplaySpecifiers.

  - Aggiunta di un oggetto **RTCPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che da applicare alle classi User e Contact.

  - Aggiunta di un oggetto **RTCUserSearchPropertySet** di tipo **controlAccessRight** in **Extended-Rights** da applicare alle classi User, Contact, OU e DomainDNS.

  - Aggiunta di un oggetto **msRTCSIP-PrimaryUserAddress** nell'attributo **extraColumns** di ogni identificatore di visualizzazione unità organizzativa lingua (ad esempio CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) e copia dei valori dell'attributo **extraColumns** della visualizzazione predefinita (ad esempio CN=default-Display, CN=409,CN=DisplaySpecifiers).

  - Aggiunta degli attributi di filtro **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** e **msRTCSIP-UserEnabled** nell'attributo **attributeDisplayNames** di ogni identificatore di visualizzazione lingua per gli oggetti User, Contact e InetOrgPerson (ad esempio per la lingua inglese: CN=user-Display,CN=409,CN=DisplaySpecifiers).

</div>

</div>

<span> </span>

</div>

</div>

</div>

