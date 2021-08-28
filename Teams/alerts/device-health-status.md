---
title: Microsoft Teams Monitoraggio dei dispositivi e avvisi
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Informazioni su come usare le funzionalità di Teams e di avviso nell'interfaccia di amministrazione di Microsoft Teams per monitorare in modo proattivo lo stato di integrità dei Teams dispositivi
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 844dddfc04e1dc29311a237c3fc4f7ac41a1ce7f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636761"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams dell'integrità dei dispositivi

Il monitoraggio dell'integrità dei dispositivi nell Microsoft Teams di amministrazione consente di monitorare in modo proattivo l'integrità di vari Teams dispositivi. Monitorare lo stato offline di un dispositivo e ricevere avvisi in tempo reale se il dispositivo monitorato nell'organizzazione diventa offline.  

Prima di iniziare, sono necessarie le autorizzazioni per la creazione di team/canali nel tenant. [Altre informazioni](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>Configurare la regola dello stato del dispositivo

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione selezionare Notifiche **& avvisi**  >  **regole**.

   ![Sezione Regole nell'interfaccia di amministrazione](../media/select-rules.png)

2. Nella pagina **Regole** selezionare **Regola stato dispositivo**.

3. Selezionare il dispositivo per configurare la regola di stato per l'abilitazione degli avvisi.

    ![Teams della regola dello stato dei dispositivi.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretare la configurazione della regola


|Campo |Descrizione  |
|--------|-------------|
|**Tipo di regola**   |La regola dello stato del dispositivo consente di gestire in modo efficace. Teams dispositivi ed è classificato come tipo di gestione dei dispositivi. In futuro saranno disponibili altre regole per il tipo di gestione dei dispositivi per monitorare altre funzionalità correlate (ad esempio: dispositivo non integro e stato di accesso del dispositivo).|
|**Condizione**   |È possibile monitorare l'integrità dei dispositivi se passano offline. [Altre informazioni sulla](../devices/device-management.md) gestione dei dispositivi nell'Teams di amministrazione. |
|**Ambito**   |È possibile specificare la frequenza con cui si vuole monitorare lo stato di integrità del dispositivo menzionando la frequenza di valutazione della regola. Per impostazione predefinita, i dispositivi di teams verranno monitorati in tempo quasi reale se passano offline. |
|**Utenti del dispositivo**   |È possibile specificare i dispositivi da monitorare offline in modo proattivo selezionandoli in base agli utenti connessi. Per altre [informazioni, vedere Selezionare i dispositivi](#select-devices-for-configuration) per la configurazione. |
|**Azioni**  >  **Avviso del canale**   |Nella sezione Azioni è possibile specificare i canali dei team per cui si vogliono ricevere avvisi. Attualmente, verrà creato un team predefinito denominato **Avvisi** e notifiche di amministrazione e un canale **denominato MonitoringAlerts** in cui verranno recapitate le notifiche. <BR/> <BR/> Gli amministratori globali e Teams nel tenant verranno aggiunti automaticamente a questo team predefinito.|
|**Azioni**  >  **Webhook**   |È anche possibile ricevere notifiche con un webhook esterno (facoltativo). Specificare un URL webhook pubblico esterno nella sezione webhook in cui verrà inviato un payload di notifica JSON. <BR/> <BR/>  Il payload di notifica, tramite webhook, può essere integrato con altri sistemi dell'organizzazione per creare flussi di lavoro personalizzati.<br/><br/> 

**Schema payload JSON per webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Payload JSON di esempio:**<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Selezionare i dispositivi per la configurazione

1. È possibile selezionare Teams dispositivi da monitorare selezionando gli utenti connessi a tali dispositivi. Selezionare **Aggiungi** nella **sezione Utenti dispositivo.**

2. Selezionare uno o più utenti di cui monitorare lo stato di integrità del dispositivo

   ![aggiungere un utente nella regola dello stato di integrità del dispositivo.](../media/select-device-users.png )

   L'elenco di utenti selezionato viene visualizzato nella **sezione Utenti** dispositivo. È possibile modificare questo elenco aggiungendo o rimuovendo utenti.

Tutti i dispositivi di accesso usati dall'elenco di utenti selezionato verranno monitorati per lo stato di integrità offline.

## <a name="notifications-in-teams-client"></a>Notifiche nel client Teams

Le notifiche vengono recapitate nel canale **MonitoringAlerts** creato automaticamente del team **di avvisi e notifiche per** gli amministratori.

Una notifica offline del dispositivo può includere le informazioni seguenti:

- Nome del dispositivo offline.
- Utente del dispositivo offline.
- A che ora il dispositivo è stato offline. (Attualmente, l'ora è presentata in UTC).
- Tipo di regola che ha generato l'avviso.
- Perché viene generato un avviso.