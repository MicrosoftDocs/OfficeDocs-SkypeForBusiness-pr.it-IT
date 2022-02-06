---
title: Modifiche apportate dalla preparazione della foresta in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: In questa sezione vengono descritti gli oggetti e le impostazioni globali e i gruppi amministrativi e di servizio universali creati durante il passaggio di preparazione della foresta.
---

# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Modifiche apportate dalla preparazione della foresta in Skype for Business Server

In questa sezione vengono descritti gli oggetti e le impostazioni globali e i gruppi amministrativi e di servizio universali creati durante il passaggio di preparazione della foresta.

## <a name="active-directory-global-settings-and-objects"></a>Oggetti e impostazioni globali di Active Directory

Se si archiviano le impostazioni globali nel contenitore Configuration (come per tutte le nuove distribuzioni di Skype for Business Server), la preparazione della foresta utilizza il contenitore Services esistente e aggiunge un oggetto **RTC Service** nell'oggetto Configuration\Services. Nell'oggetto RTC Service viene aggiunto per la preparazione della foresta un oggetto **Global Settings** di tipo msRTCSIP-GlobalContainer. L'oggetto impostazioni globali contiene tutte le impostazioni applicabili alla Skype for Business Server distribuzione. Se si archiviano le impostazioni globali nel contenitore System, per la preparazione della foresta verrà usato un contenitore Microsoft nel contenitore System del dominio radice e un oggetto RTC Service nell'oggetto System\Microsoft.

Durante la preparazione della foresta viene aggiunto inoltre un nuovo oggetto **msRTCSIP-Domain** per il dominio radice in cui viene eseguita la procedura.

## <a name="active-directory-universal-service-and-administration-groups"></a>Gruppi amministrativi e di servizio universali di Active Directory

Durante la preparazione della foresta vengono creati gruppi universali basati sul dominio specificato e vengono aggiunte voci di controllo di accesso (ACE) per tali gruppi. Durante questo passaggio vengono creati i gruppi universali nei contenitori User del dominio specificato.

I gruppi universali consentono agli amministratori di accedere ai servizi e alle impostazioni globali e di gestirli. Per la preparazione della foresta vengono aggiunti i tipi di gruppi universali seguenti:

- **Gruppi amministrativi** Questi gruppi definiscono i ruoli di amministratore per una Skype for Business Server rete.

- **Gruppi infrastruttura** Questi gruppi forniscono l'autorizzazione per accedere ad aree specifiche dell'Skype for Business Server aziendale. Funzionano come componenti di gruppi amministrativi. Non modificare questi gruppi né aggiungervi direttamente gli utenti.

- **Gruppi di servizi** Questi gruppi sono account di servizio necessari per accedere a vari Skype for Business Server servizi.

Nella tabella riportata di seguito vengono descritti i gruppi amministrativi.

**Gruppi amministrativi creati durante la preparazione della foresta**

|**Gruppo amministrativo**|**Descrizione**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Consente ai membri di gestire le impostazioni di server e pool, inclusi tutti gli utenti, le impostazioni globali e i ruoli del server.  <br/> |
|RTCUniversalUserAdmins  <br/> |Consente ai membri di gestire le impostazioni utente e di spostare gli utenti da un server o da un pool a un altro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Consente ai membri di leggere le impostazioni di server, pool e utenti.  <br/> |

Nella tabella riportata di seguito vengono descritti i gruppi di infrastruttura.

**Gruppi di infrastruttura creati durante la preparazione della foresta**

|**Gruppo di infrastruttura**|**Descrizione**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede l'accesso in scrittura agli oggetti impostazione globale per Skype for Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede l'accesso in sola lettura agli oggetti impostazione globale per Skype for Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede l'accesso in sola lettura alle Skype for Business Server utente.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede l'accesso in sola lettura alle Skype for Business Server predefinite. Questo gruppo non dispone dell'accesso alle impostazioni a livello di pool, ma solo a quelle specifiche di un singolo server.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede l'accesso in sola lettura Skype for Business Server configurazione e viene inserita nel gruppo Administrators locale dei Survivable Branch Appliance durante l'installazione.  <br/> |

Nella tabella riportata di seguito vengono descritti i gruppi di servizio.

**Gruppi di servizio creati durante la preparazione della foresta**

|**Gruppo di servizio**|**Descrizione**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Include gli account di servizio utilizzati per eseguire Front End Server e edizione Standard server. Questo gruppo consente ai server l'accesso in lettura/scrittura Skype for Business Server impostazioni globali e agli oggetti utente di Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Include gli account di servizio utilizzati per eseguire A/V Conferencing Server, Servizi Web, Mediation Server, Server di archiviazione e Monitoring Server.  <br/> |
|RTCProxyUniversalServices  <br/> |Include gli account di servizio utilizzati per eseguire Skype for Business Server server perimetrali.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Include i server che possono partecipare alla Skype for Business Server dell'archivio di gestione centrale.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede l'accesso in sola lettura alle Skype for Business Server, ma consente la configurazione per l'installazione di un survivable branch server e di una distribuzione di survivable branch appliance.  <br/> |

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

Per informazioni dettagliate sui gruppi di controllo dell'accesso basato sui ruoli e sulle attività consentite per ognuno, vedere [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) nella documentazione relativa alla pianificazione.

Durante la preparazione della foresta vengono create voci di controllo di accesso private e pubbliche. Vengono create voci di controllo di accesso private nel contenitore delle impostazioni globali utilizzato Skype for Business Server. Questo contenitore viene utilizzato solo da Skype for Business Server e si trova nel contenitore Configurazione o nel contenitore Sistema nel dominio radice, a seconda della posizione in cui vengono archiviate le impostazioni globali. Le voci di controllo di accesso pubbliche create durante la preparazione della foresta sono elencate nella tabella seguente.

**Voci di controllo di accesso pubbliche create durante la preparazione della foresta**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Lettura del contenitore di sistema del dominio radice (non ereditato) **\\**\* <br/>        | X  <br/>                            |
| Lettura del contenitore DisplaySpecifiers della configurazione (non ereditato)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*Le voci di controllo di accesso non ereditate non concedono l'accesso agli oggetti figlio in questi contenitori. Alle voci di controllo di accesso ereditate viene concesso l'accesso agli oggetti figlio presenti in tali contenitori.

Nel contesto dei nomi di configurazione all'interno del contenitore Configuration durante la preparazione della foresta vengono eseguite le attività seguenti:

- Aggiunta di una voce **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** per la pagina della proprietà **RTC** negli attributi adminContextMenu e adminPropertyPages dell'identificatore di visualizzazione lingua per gli oggetti User, Contact e InetOrgPerson, ad esempio, CN=user-Display,CN=409,CN=DisplaySpecifiers.

- Aggiunta di un oggetto **RTCPropertySet** di tipo **controlAccessRight** in **Extended-Rights** che da applicare alle classi User e Contact.

- Aggiunta di un oggetto **RTCUserSearchPropertySet** di tipo **controlAccessRight** in **Extended-Rights** da applicare alle classi User, Contact, OU e DomainDNS.

- Aggiunta di un oggetto **msRTCSIP-PrimaryUserAddress** nell'attributo **extraColumns** di ogni identificatore di visualizzazione unità organizzativa lingua (ad esempio CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) e copia dei valori dell'attributo **extraColumns** della visualizzazione predefinita (ad esempio CN=default-Display, CN=409,CN=DisplaySpecifiers).

- Aggiunta degli attributi di filtro **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** e **msRTCSIP-UserEnabled** nell'attributo **attributeDisplayNames** di ogni identificatore di visualizzazione lingua per gli oggetti User, Contact e InetOrgPerson (ad esempio per la lingua inglese: CN=user-Display,CN=409,CN=DisplaySpecifiers).