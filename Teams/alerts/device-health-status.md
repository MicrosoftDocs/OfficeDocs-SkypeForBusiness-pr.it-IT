---
title: Monitoraggio e avvisi dei dispositivi di Microsoft Teams
author: cazawideh
ms.author: czawideh
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
description: Informazioni su come usare le funzionalità di monitoraggio e avviso di Teams nell'interfaccia di amministrazione di Microsoft Teams per monitorare in modo proattivo lo stato di integrità dei dispositivi Teams
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 81994e3462fe678c40506d6a11b343ba733995cd
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023807"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Monitoraggio dell'integrità dei dispositivi di Microsoft Teams

Il monitoraggio dell'integrità dei dispositivi nell'interfaccia di amministrazione di Microsoft Teams offre la possibilità di monitorare in modo proattivo l'integrità di vari dispositivi Teams. Monitorare lo stato offline di un dispositivo e ricevere avvisi in tempo reale se il dispositivo monitorato nell'organizzazione passa offline.  

Prima di iniziare, sono necessarie le autorizzazioni per la creazione di team/canali nel tenant. [Altre informazioni](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>Configurare la regola dello stato del dispositivo

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Regole notifiche & avvisi** > **.**

   ![Sezione Regole nell'interfaccia di amministrazione.](../media/select-rules.png)

2. Nella pagina **Regole** selezionare **Regola stato dispositivo**.

3. Selezionare il dispositivo per configurare la regola di stato per l'abilitazione degli avvisi.

    ![Pagina delle regole dello stato dei dispositivi Teams.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretare la configurazione delle regole


|Campo |Descrizione  |
|--------|-------------|
|**Tipo di regola**   |La regola dello stato del dispositivo consente di gestire in modo efficace. Dispositivi di Teams e viene classificato come tipo di gestione dei dispositivi. In futuro saranno disponibili altre regole di tipo gestione dispositivi per monitorare altre funzionalità correlate (ad esempio: dispositivo non integro e stato di accesso del dispositivo).|
|**Condizione**   |Puoi monitorare l'integrità dei dispositivi se passano offline. [Altre informazioni](../devices/device-management.md) sulla gestione dei dispositivi nell'interfaccia di amministrazione di Teams. |
|**Ambito**   |È possibile specificare la frequenza con cui si vuole monitorare lo stato di integrità del dispositivo menzionando la frequenza di valutazione delle regole. Per impostazione predefinita, i dispositivi dei team verranno monitorati quasi in tempo reale se passano offline. |
|**Utenti di dispositivi**   |È possibile specificare quali dispositivi necessitano di un monitoraggio proattivo della statua offline selezionandoli in base agli utenti connessi. Per altre informazioni, vedere [Selezionare i dispositivi per la configurazione](#select-devices-for-configuration) . |
|**Azioni** >  **Avviso canale**   |Nella sezione Azioni è possibile specificare i canali dei team per cui ricevere avvisi. Attualmente, verrà creato un team predefinito denominato **avvisi e notifiche Amministrazione** e un canale denominato **MonitoringAlerts** a cui verranno recapitate le notifiche. <BR/> <BR/> Gli amministratori globali e gli amministratori di Teams nel tenant verranno aggiunti automaticamente a questo team predefinito.|
|**Azioni** >  **Webhook**   |È anche possibile ricevere notifiche con un webhook esterno (facoltativo). Specificare un URL webhook pubblico esterno nella sezione webhook in cui verrà inviato un payload di notifica JSON. <BR/> <BR/>  Il payload di notifica, tramite webhooks, può essere integrato con altri sistemi dell'organizzazione per creare flussi di lavoro personalizzati.<br/><br/> 

**Schema del payload JSON per webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string"} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Payload JSON di esempio**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         "DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": "Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Selezionare i dispositivi per la configurazione

1. È possibile selezionare i dispositivi di Teams da monitorare selezionando gli utenti che hanno eseguito l'accesso a tali dispositivi. Seleziona **Aggiungi** nella sezione **Utenti dispositivo** .

2. Selezionare uno o più utenti per cui si vuole monitorare lo stato di integrità del dispositivo

   ![aggiungi utente nella regola dello stato di integrità del dispositivo.](../media/select-device-users.png )

   L'elenco selezionato di utenti viene visualizzato nella sezione **Utenti dispositivo** . È possibile modificare questo elenco aggiungendo o rimuovendo utenti.

Tutti i dispositivi di accesso utilizzati dall'elenco selezionato di utenti verranno monitorati per lo stato di integrità offline.

## <a name="notifications-in-teams-client"></a>Notifiche nel client di Teams

Le notifiche vengono recapitate nel canale **MonitoringAlerts** creato automaticamente del team **di Amministrazione avvisi e notifiche**. Riceverai un avviso entro 15 minuti dalla modalità offline del dispositivo. 

Una notifica offline del dispositivo può includere le informazioni seguenti:

- Nome del dispositivo offline.
- Utente del dispositivo offline.
- A che ora il dispositivo è stato disconnetteto. Attualmente, l'ora è presentata in formato UTC.
- Tipo di regola che ha generato l'avviso.
- Perché viene generato un avviso.
