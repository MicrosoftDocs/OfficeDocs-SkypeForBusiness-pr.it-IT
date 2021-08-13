---
title: Microsoft Teams Monitoraggio e avvisi dei dispositivi
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Informazioni su come usare le funzionalità di Teams e di avviso nell'interfaccia di amministrazione di Microsoft Teams per monitorare in modo proattivo lo stato di integrità dei Teams dispositivi
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: cca6be8274d26efe661a7a928ebb568aa054cfab2fb62206ee8f3649b37f4ea0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336197"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams dell'integrità dei dispositivi

Il monitoraggio dell'integrità dei dispositivi Microsoft Teams'interfaccia di amministrazione offre la possibilità di monitorare in modo proattivo l'integrità di vari Teams dispositivi. Monitorare lo stato offline di un dispositivo e ricevere avvisi in tempo reale se il dispositivo monitorato nell'organizzazione diventa offline.  

Prima di iniziare, sono necessarie le autorizzazioni per la creazione di team/canali nel tenant. [Ulteriori informazioni](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>Configurare la regola di stato del dispositivo

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione selezionare **Notifiche & avvisi**  >  **Regole**.

   ![Sezione Regole nell'interfaccia di amministrazione](../media/select-rules.png)

2. Nella pagina **Regole** selezionare **Regola stato dispositivo**.

3. Selezionare il dispositivo per configurare la regola di stato per l'abilitazione degli avvisi.

    ![Teams della regola di stato dei dispositivi mobili.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretare la configurazione delle regole


|Campo |Descrizione  |
|--------|-------------|
|**Tipo di regola**   |La regola di stato del dispositivo ti aiuta a gestire in modo efficace. Teams dispositivi ed è classificato come tipo di gestione dei dispositivi. In futuro, saranno disponibili altre regole di tipo gestione dei dispositivi per monitorare altre funzionalità correlate (alcuni esempi possono includere: dispositivo non integro e lo stato di accesso del dispositivo).|
|**Condizione**   |Puoi monitorare l'integrità dei dispositivi se passano offline. [Altre informazioni sulla](../devices/device-management.md) gestione dei dispositivi in Teams di amministrazione. |
|**Ambito**   |Puoi specificare la frequenza con cui vuoi monitorare lo stato di integrità del dispositivo menzionando la frequenza di valutazione della regola. Per impostazione predefinita, i dispositivi dei team verranno monitorati quasi in tempo reale se vengono offline. |
|**Utenti del dispositivo**   |Puoi specificare quali dispositivi necessitano di monitoraggio proattivo offline selezionandoli in base agli utenti connessi. Per altri [dettagli, fai riferimento a Selezionare](#select-devices-for-configuration) i dispositivi per la configurazione. |
|**Azioni**  >  **Avviso canale**   |Nella sezione Azioni è possibile specificare i canali dei team per i quali si desidera ricevere avvisi. Attualmente, verrà creato un team predefinito denominato **Avvisi** e notifiche di amministrazione e un canale **denominato MonitoringAlerts** in cui verranno recapitate le notifiche. <BR/> <BR/> Gli amministratori globali e Teams nel tenant verranno aggiunti automaticamente a questo team predefinito.|
|**Azioni**  >  **Webhook**   |Puoi anche ricevere notifiche con un webhook esterno (facoltativo). Specifica un URL webhook pubblico esterno nella sezione webhook in cui verrà inviato un payload di notifica JSON. <BR/> <BR/>  Il payload di notifica, tramite webhook, può essere integrato con altri sistemi dell'organizzazione per creare flussi di lavoro personalizzati.<br/><br/> 

**Schema payload JSON per webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Payload JSON di esempio:**<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Selezionare i dispositivi per la configurazione

1. Puoi selezionare i Teams che vuoi monitorare selezionando gli utenti che hanno eseguito l'accesso a tali dispositivi. Seleziona **Aggiungi** nella **sezione Utenti dispositivo.**

2. Selezionare uno o più utenti per i quali si desidera monitorare lo stato di integrità del dispositivo

   ![aggiungere l'utente nella regola di stato di integrità del dispositivo.](../media/select-device-users.png )

   L'elenco di utenti selezionato viene visualizzato nella **sezione Utenti dispositivo.** È possibile modificare questo elenco aggiungendo o rimuovendo utenti.

Tutti i dispositivi di accesso utilizzati dall'elenco di utenti selezionato verranno monitorati per lo stato di integrità offline.

## <a name="notifications-in-teams-client"></a>Notifiche in Teams client

Le notifiche vengono recapitate nel canale **MonitoringAlerts** creato automaticamente del team di avvisi **e notifiche dell'amministratore.**

Una notifica offline del dispositivo può includere le informazioni seguenti:

- Nome del dispositivo offline.
- L'utente del dispositivo offline.
- Ora in cui il dispositivo è stato offline. (Attualmente, l'ora è presentata in UTC.
- Tipo di regola che ha generato l'avviso.
- Motivo per cui viene generato un avviso.