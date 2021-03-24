---
title: Pianificare il connettore dati delle chiamate | Monitoraggio dell'analisi ibrida del dashboard di qualità delle chiamate
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
description: Panoramica dell'uso degli strumenti di telemetria di Skype for Business Online per monitorare un'implementazione locale in uno scenario ibrido.
ms.openlocfilehash: f47f0969d102408299678842b18bb503eaf6aea0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110552"
---
# <a name="plan-call-data-connector"></a>Pianificare connettore dati chiamate

## <a name="overview"></a>Panoramica

In questo argomento vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione di Skype for Business Server Call Data Connector. Per ulteriori informazioni sulla configurazione di Call Data Connector, vedere [Configure Call Data Connector](configure-call-data-connector.md).


Call Data Connector semplifica notevolmente il monitoraggio delle chiamate in un ambiente ibrido perché non è più necessario utilizzare set diversi di strumenti locali e online per monitorare la qualità delle chiamate di tutti gli utenti. Sia che gli utenti siano ospitati in locale o online, è possibile scegliere di visualizzare la qualità delle chiamate per l'intera organizzazione online.

Con Call Data Connector è possibile eseguire le attività seguenti utilizzando un singolo set di strumenti:

- Monitorare l'esperienza utente in Microsoft Teams, Skype for Business online e Skype for Business Server.

- Visualizzare e risolvere i problemi nella rete.

- Assegnare ruoli di helpdesk e amministratore per Call Analytics, in modo da consentire ai dipendenti dell'helpdesk di visualizzare e risolvere i problemi relativi alle aree di responsabilità.

Con Call Data Connector, Skype for Business Server invia i dati delle chiamate al servizio cloud in modo da poter sfruttare gli strumenti Di analisi delle chiamate online (CA) e CQD (Call Quality Dashboard) di Skype for Business, come illustrato nel diagramma seguente:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-1.png)

Il server invia sia i dati QoE (Quality of Experience) che la registrazione dettagli chiamata (CDR) al servizio online.

Gli strumenti di analisi delle chiamate e CQD consentono di monitorare la qualità delle chiamate e risolvere i problemi di connessione con Microsoft Teams e i servizi Skype for Business come indicato di seguito:

- Call Analytics si concentra sui problemi di qualità con chiamate specifiche. Mostra informazioni dettagliate sulle chiamate e le riunioni per ogni utente in un account Skype for Business.  Con Call Analytics puoi assegnare le autorizzazioni a un operatore dell'helpdesk che può monitorare le chiamate senza avere accesso al resto dell'interfaccia di amministrazione di Skype for Business.

- Call Quality Dashboard si concentra sulle prestazioni della rete e sui problemi di un'organizzazione. Gli amministratori di Skype for Business e i tecnici di rete usano questo strumento per risolvere i problemi e ottimizzare le prestazioni di rete.

Per ulteriori informazioni, vedere [Call Analytics and Call Quality Dashboard.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

Naturalmente, potresti voler mantenere alcuni dati sulla qualità delle chiamate in locale. Questo potrebbe essere il caso, ad esempio, se si utilizza una soluzione di terze parti con report e flussi di lavoro personalizzati.  Call Data Connector consente di configurare l'invio di dati al servizio online mantenendo anche una copia dei dati nel server locale, come illustrato nel diagramma seguente:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che Skype for Business Server sia già stato distribuito in una topologia supportata.  Per ulteriori informazioni sulla distribuzione di Skype for Business Server e delle topologie supportate, vedere [Topology Basics.](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) Per configurare Call Data Connector, è necessario:

- Abilitare la connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare Il connettore dati di chiamata, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di dominio diviso.

   Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365](plan-hybrid-connectivity.md) e Configurare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365.](configure-hybrid-connectivity.md)

- Eseguire l'autenticazione nell'organizzazione di Microsoft 365 o Office 365 e verificare di avere abilitato i ruoli seguenti:

  - Amministratore di Skype for Business Server
  - Amministratore globale di Microsoft 365 o Office 365

- Se non l'hai già fatto, attiva Il dashboard qualità delle chiamate come descritto in Attivazione e uso del dashboard qualità delle chiamate per [Microsoft Teams e Skype for Business online.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- Abilitare il pool front end per il monitoraggio, con database LCSCdr e QoEMetrics locali. Senza questo, Call Data Connector non dispone di dati di metrica da utilizzare.

> [!IMPORTANT]
> Il connettore dati di chiamata non funzionerà se il monitoraggio non è abilitato nel pool front-end.

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