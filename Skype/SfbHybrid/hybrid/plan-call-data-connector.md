---
title: Pianificare il connettore dati di chiamata | Monitoraggio dell'analisi ibrida del dashboard di qualità delle chiamate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Panoramica dell'Skype for Business strumenti di telemetria online per monitorare un'implementazione locale in uno scenario ibrido.
ms.openlocfilehash: a0288f07c942f003cfece5aceaddf4139af84569
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407175"
---
# <a name="plan-call-data-connector"></a>Pianificare connettore dati chiamate

## <a name="overview"></a>Panoramica

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In questo argomento vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione Skype for Business Server Call Data Connector. Per ulteriori informazioni sulla configurazione di Call Data Connector, vedere [Configure Call Data Connector](configure-call-data-connector.md).


Call Data Connector semplifica notevolmente il monitoraggio delle chiamate in un ambiente ibrido perché non è più necessario utilizzare set diversi di strumenti locali e online per monitorare la qualità delle chiamate di tutti gli utenti. Sia che gli utenti siano ospitati in locale o online, è possibile scegliere di visualizzare la qualità delle chiamate per l'intera organizzazione online.

Con Call Data Connector è possibile eseguire le attività seguenti utilizzando un singolo set di strumenti:

- Monitorare l'esperienza utente Microsoft Teams, Skype for Business Online e Skype for Business Server.

- Visualizzare e risolvere i problemi nella rete.

- Assegnare ruoli di helpdesk e amministratore per Call Analytics, in modo da consentire ai dipendenti dell'helpdesk di visualizzare e risolvere i problemi relativi alle aree di responsabilità.

Con Call Data Connector, il Skype for Business Server invia i dati delle chiamate al servizio cloud in modo da poter sfruttare gli strumenti di analisi delle chiamate online (CA) e CQD (Call Quality Dashboard) di Skype for Business, come illustrato nel diagramma seguente:

![SfB Cloud Voicemail diagramma.](../../sfbserver2019/media/call-data-connector-plan-1.png)

Il server invia sia i dati QoE (Quality of Experience) che la registrazione dettagli chiamata (CDR) al servizio online.

Gli strumenti di analisi delle chiamate e CQD consentono di monitorare la qualità delle chiamate e risolvere i problemi di connessione con Microsoft Teams e Skype for Business come indicato di seguito:

- Call Analytics si concentra sui problemi di qualità con chiamate specifiche. Vengono visualizzate informazioni dettagliate sulle chiamate e le riunioni per ogni utente in un Skype for Business account.  Con Call Analytics puoi assegnare le autorizzazioni a un operatore del supporto tecnico che può quindi monitorare le chiamate senza avere accesso al resto dell Skype for Business admin center.

- Il dashboard qualità delle chiamate si concentra sulle prestazioni della rete e sui problemi di un'organizzazione. Skype for Business amministratori e tecnici di rete usano questo strumento per risolvere i problemi e ottimizzare le prestazioni di rete.

Per ulteriori informazioni, vedere [Call Analytics and Call Quality Dashboard diagram with Monitoring Server details.](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

Naturalmente, potresti voler mantenere alcuni dati sulla qualità delle chiamate in locale. Ciò potrebbe verificarsi, ad esempio, se si utilizza una soluzione di terze parti con report e flussi di lavoro personalizzati.  Call Data Connector consente di configurare l'invio di dati al servizio online mantenendo anche una copia dei dati nel server locale, come illustrato nel diagramma seguente:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che sia già stata Skype for Business Server distribuita in una topologia supportata.  Per ulteriori informazioni sulla distribuzione di Skype for Business Server e topologie supportate, vedere [Topology Basics.](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) Per configurare Call Data Connector, è necessario:

- Abilitare la connettività ibrida. Se è già stata Skype for Business Server e si desidera abilitare Il connettore dati di chiamata, è necessario verificare di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di dominio diviso.

   Per ulteriori informazioni, vedere [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) e Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or [Office 365](configure-hybrid-connectivity.md).

- Eseguire l'autenticazione Microsoft 365 o Office 365'organizzazione e assicurarsi di avere abilitato i ruoli seguenti:

  - Skype for Business Server Amministratore
  - Microsoft 365 o Office 365 amministratore globale

- Se non l'hai già fatto, attiva Il dashboard qualità delle chiamate come descritto in Attivazione e utilizzo del Dashboard qualità delle chiamate per Microsoft Teams [e Skype for Business Online.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- Abilitare il pool front end per il monitoraggio, con database LCSCdr e QoEMetrics locali. Senza questo, Call Data Connector non dispone di dati di metrica da utilizzare.

> [!IMPORTANT]
> Call Data Connector non funzionerà se il monitoraggio non è abilitato nel pool front-end.

- Autenticazione da server a [server configurata correttamente.](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Confronto tra report CQD (Call Quality Dashboard) locali e online

| Report sulle funzionalità | Skype for Business online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Metrica condivisione applicazioni |Sì | Limited |
| Informazioni sull'edificio del cliente| Sì | Sì |
| Analisi drill-down | Sì | No |
| Metriche di affidabilità multimediale | Sì | Limited |
| Report predefiniti | Sì | Sì |
| Report di panoramica | Sì | No |
| Report per utente | Sì | Sì |
| Personalizzazione del set di report <br> (aggiungere, eliminare, modificare i report) | Sì | Sì |
| Metriche di condivisione dello schermo basate su video | Sì | No |
| API dei dati per l'accesso a livello di codice <br> a CQD | No | Sì |
||||