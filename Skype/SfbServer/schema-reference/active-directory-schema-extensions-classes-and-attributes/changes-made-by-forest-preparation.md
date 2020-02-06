---
title: Modifiche apportate dalla preparazione della foresta in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Questa sezione descrive le impostazioni globali e gli oggetti e i gruppi di servizi e di amministrazione universali creati dal passaggio di preparazione della foresta.
ms.openlocfilehash: 26917915d89aff721e74f094eb8ad5bb72db3cf6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815534"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Modifiche apportate dalla preparazione della foresta in Skype for Business Server

Questa sezione descrive le impostazioni globali e gli oggetti e i gruppi di servizi e di amministrazione universali creati dal passaggio di preparazione della foresta.

## <a name="active-directory-global-settings-and-objects"></a>Impostazioni globali e oggetti di Active Directory

Se si archiviano le impostazioni globali nel contenitore di configurazione (come nel caso di tutte le nuove distribuzioni di Skype for Business Server), la preparazione della foresta usa il contenitore di servizi esistente e aggiunge un oggetto **RTC Service** sotto l'oggetto Configuration\Services.. Sotto l'oggetto servizio RTC, la preparazione della foresta aggiunge un oggetto **Impostazioni globali** di tipo msRTCSIP-GlobalContainer. L'oggetto impostazioni globali contiene tutte le impostazioni applicabili alla distribuzione di Skype for Business Server. Se si archiviano le impostazioni globali nel contenitore di sistema, la preparazione della foresta usa un contenitore Microsoft nel contenitore di sistema del dominio radice e un oggetto servizio RTC sotto l'oggetto System\microsoft..

La preparazione della foresta aggiunge anche un nuovo oggetto **msRTCSIP-Domain** per il dominio radice in cui viene eseguita la procedura.

## <a name="active-directory-universal-service-and-administration-groups"></a>Gruppi di amministrazione e servizio universale di Active Directory

La preparazione della foresta crea gruppi universali in base al dominio specificato e aggiunge voci di controllo di accesso (ACE) per questi gruppi. Questo passaggio crea i gruppi universali nei contenitori utente del dominio specificato.

I gruppi universali consentono agli amministratori di accedere e gestire le impostazioni e i servizi globali. La preparazione della foresta aggiunge i tipi di gruppi universali seguenti:

- **Gruppi amministrativi** Questi gruppi definiscono i ruoli di amministratore per una rete di Skype for Business Server.

- **Gruppi di infrastrutture** Questi gruppi conferiscono l'autorizzazione per accedere ad aree specifiche dell'infrastruttura di Skype for Business Server. Funzionano come componenti di gruppi amministrativi. Non è consigliabile modificare questi gruppi né aggiungere utenti direttamente.

- **Gruppi di servizi** Questi gruppi sono account di servizio necessari per accedere a vari servizi di Skype for Business Server.

La tabella seguente descrive i gruppi amministrativi.

**Gruppi amministrativi creati durante la preparazione della foresta**

|**Gruppo amministrativo**|**Descrizione**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Consente ai membri di gestire le impostazioni del server e del pool, inclusi tutti i ruoli del server, le impostazioni globali e gli utenti.  <br/> |
|RTCUniversalUserAdmins  <br/> |Consente ai membri di gestire le impostazioni utente e di trasferire gli utenti da un server o da un pool a un altro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Consente ai membri di leggere le impostazioni del server, del pool e dell'utente.  <br/> |

La tabella seguente descrive i gruppi di infrastrutture.

**Gruppi di infrastrutture creati durante la preparazione della foresta**

|**Gruppo infrastruttura**|**Descrizione**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede l'accesso in scrittura agli oggetti delle impostazioni globali per Skype for Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede l'accesso in sola lettura agli oggetti setting globali per Skype for Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede l'accesso in sola lettura alle impostazioni utente di Skype for Business Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede l'accesso in sola lettura alle impostazioni di Skype for Business Server. Questo gruppo non ha accesso alle impostazioni del livello del pool, solo alle impostazioni specifiche di un singolo server.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede l'accesso in sola lettura alla configurazione di Skype for Business Server e viene inserito nel gruppo amministratori locali degli appliance Survivable Branch durante l'installazione.  <br/> |

La tabella seguente descrive i gruppi di servizi.

**Gruppi di servizi creati durante la preparazione della foresta**

|**Gruppo di servizi**|**Descrizione**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Include gli account di servizio usati per eseguire front end server e server Standard Edition. Questo gruppo consente ai server di accedere in lettura/scrittura alle impostazioni globali di Skype for Business Server e agli oggetti utente di Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Include gli account di servizio usati per eseguire servizi di conferenza A/V, Web Services, Mediation Server, server di archiviazione e server di monitoraggio.  <br/> |
|RTCProxyUniversalServices  <br/> |Include gli account di servizio usati per eseguire Skype for Business Server Edge Server.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Include i server che possono partecipare alla replica di Skype for Business Server Central Management store.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede l'accesso in sola lettura alle impostazioni di Skype for Business Server, ma consente la configurazione per l'installazione di un Survivable Branch Server e della distribuzione Survivable Branch Appliance.  <br/> |

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

Per informazioni dettagliate sui ruoli RBAC e sulle attività consentite per ognuno, vedere [controllo di accesso basato](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) sui ruoli nella documentazione relativa alla pianificazione.

La preparazione della foresta crea sia gli assi privati che quelli pubblici. Crea assi privati nel contenitore di impostazioni globali usato da Skype for Business Server. Questo contenitore viene usato solo da Skype for Business Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda della posizione in cui si archiviano le impostazioni globali. Le voci ACE pubbliche create dalla preparazione della foresta sono elencate nella tabella seguente.

**Ace pubbliche create dalla preparazione della foresta**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Read Root Domain System container (non ereditato)**\\**\* <br/>        | X  <br/>                            |
| Contenitore di DisplaySpecifiers della configurazione di lettura (non ereditato)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* Le voci ACE non ereditate non consentono l'accesso agli oggetti figlio in questi contenitori. Le voci ACE ereditate concedono l'accesso agli oggetti figlio in questi contenitori.

Nel contenitore di configurazione, in contesto dei nomi di configurazione, la preparazione della foresta esegue le attività seguenti:

- Aggiunge una voce **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** per la pagina delle **proprietà RTC** in attributi adminContextMenu e adminPropertyPages dello specificatore di visualizzazione della lingua per utenti, contatti e INETORGPERSON, ad esempio CN = user-Display, CN = 409, CN = DisplaySpecifiers.

- Aggiunge un oggetto **RTCPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che si applica alle classi User e Contact.

- Aggiunge un oggetto **RTCUserSearchPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che si applica alle classi User, Contact, ou e DomainDNS.

- Aggiunge **msRTCSIP-PrimaryUserAddress** nell'attributo **Columns** di ogni specificatore di visualizzazione dell'unità organizzativa (ad esempio, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) e copia i valori dell'attributo **Columns** della visualizzazione predefinita, ad esempio CN = default-display, CN = 409, CN = DisplaySpecifiers.

- Aggiunge gli attributi di filtro msRTCSIP **-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**e **msRTCSIP-UserEnabled** nell'attributo **nell'attributeDisplayNames** di ogni identificatore di visualizzazione della lingua per gli utenti, i contatti e gli oggetti InetOrgPerson, ad esempio in inglese: CN = user-Display, CN = 409, CN = DisplaySpecifiers.


