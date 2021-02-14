---
title: Pianificare il connettore dati di chiamata | Call Quality Dashboard Monitoring Hybrid Analytics
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
description: Panoramica dell'uso degli strumenti di telemetria di Skype for Business online per monitorare un'implementazione locale in uno scenario ibrido.
ms.openlocfilehash: 30ff8aebc739e0602f9700cbe9120d230845a023
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221316"
---
# <a name="plan-call-data-connector"></a>Pianificare connettore dati chiamate

## <a name="overview"></a>Panoramica

In questo argomento vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del connettore dati delle chiamate di Skype for Business Server. Per ulteriori informazioni sulla configurazione di Call Data Connector, vedere [Configure Call Data Connector.](configure-call-data-connector.md)


Call Data Connector semplifica notevolmente il monitoraggio delle chiamate in un ambiente ibrido perché non è più necessario utilizzare set diversi di strumenti online e locali per monitorare la qualità delle chiamate di tutti gli utenti. Indipendentemente dal fatto che gli utenti siano ospitati in locale o online, è possibile scegliere di visualizzare la qualità delle chiamate per l'intera organizzazione online.

Con Call Data Connector, è possibile eseguire le attività seguenti utilizzando un unico set di strumenti:

- Monitorare l'esperienza utente in Microsoft Teams, Skype for Business online e Skype for Business Server.

- Visualizzare e risolvere i problemi nella rete.

- Assegnare ruoli di helpdesk e amministratore per Call Analytics, in modo da consentire ai dipendenti dell'helpdesk di visualizzare e risolvere i problemi relativi alle aree di responsabilità.

Con Call Data Connector, Skype for Business Server invia i dati delle chiamate al servizio cloud in modo da poter sfruttare gli strumenti Di analisi delle chiamate (CA) e Call Quality Dashboard (CQD) di Skype for Business Online, come illustrato nel diagramma seguente:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-1.png)

Il server invia sia i dati QoE (Quality of Experience) che i dati di registrazione dettagli chiamata (CDR) al servizio online.

Gli strumenti analisi delle chiamate e DQD consentono di monitorare la qualità delle chiamate e risolvere i problemi di connessione con i servizi di Microsoft Teams e Skype for Business come segue:

- Call Analytics si concentra sui problemi di qualità con chiamate specifiche. Mostra informazioni dettagliate sulle chiamate e le riunioni per ogni utente in un account Skype for Business.  Con Call Analytics, puoi assegnare le autorizzazioni a un operatore del supporto tecnico che può monitorare le chiamate senza avere accesso al resto dell'interfaccia di amministrazione di Skype for Business.

- Call Quality Dashboard si concentra sulle prestazioni di rete e sui problemi all'interno di un'organizzazione. Gli amministratori di Skype for Business e i tecnici di rete usano questo strumento per risolvere i problemi e ottimizzare le prestazioni di rete.

Per ulteriori informazioni, vedere [Call Analytics and Call Quality Dashboard.](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)

Naturalmente, è consigliabile mantenere alcuni dati sulla qualità delle chiamate in locale. Ciò può verificarsi, ad esempio, se si utilizza una soluzione di terze parti con report e flussi di lavoro personalizzati.  Call Data Connector consente di configurare l'invio dei dati al servizio online mantenendo anche una copia dei dati nel server locale, come illustrato nel diagramma seguente:

![SfB Cloud Voicemail](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che Skype for Business Server sia già stato distribuito in una topologia supportata.  Per ulteriori informazioni sulla distribuzione di Skype for Business Server e sulle topologie supportate, vedere [Topology Basics.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics) Per configurare il connettore dati di chiamata, è necessario:

- Abilitare la connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare Il connettore dati di chiamata, è necessario verificare che la connettività ibrida sia impostata tra l'ambiente locale e quello online. A volte viene definita configurazione di dominio diviso.

   Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365](plan-hybrid-connectivity.md) e Configurare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365.](configure-hybrid-connectivity.md)

- Eseguire l'autenticazione nell'organizzazione di Microsoft 365 o Office 365 e verificare che siano abilitati i ruoli seguenti:

  - Amministratore di Skype for Business Server
  - Amministratore globale di Microsoft 365 o Office 365

- Se non l'hai già fatto, attiva dashboard qualità chiamata come descritto in Attivazione e uso del dashboard qualità delle chiamate per [Microsoft Teams e Skype for Business online.](/microsoftteams/turning-on-and-using-call-quality-dashboard)

- Abilitare il pool front-end per il monitoraggio, con database LCSCdr e QoEMetrics locali. In caso contrario, il connettore di dati di chiamata non dirà i dati della metrica da utilizzare.

> [!IMPORTANT]
> Il connettore dati di chiamata non funzionerà se il monitoraggio non è abilitato nel pool front-end.

- Autenticazione da server a [server configurata correttamente.](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications) 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Confronto tra report CQD (Call Quality Dashboard) locali e online

| Report sulle funzionalità | Skype for Business online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Metrica condivisione applicazioni |Sì | Limitato |
| Informazioni sull'edificio del cliente| Sì | Sì |
| Analisi di drill-down | Sì | No |
| Metrica dell'affidabilità multimediale | Sì | Limitato |
| Report predefiniti | Sì | Sì |
| Report di panoramica | Sì | No |
| Report per utente | Sì | Sì |
| Personalizzazione dell'insieme di report <br> (aggiungere, eliminare, modificare i report) | Sì | Sì |
| Metriche di condivisione dello schermo basata su video | Sì | No |
| API dei dati per l'accesso programmatico <br> a CQD | No | Sì |
||||
