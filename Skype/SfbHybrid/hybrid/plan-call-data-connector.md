---
title: Data Connector chiamata piano | Dashboard qualità chiamata che monitora l'analisi ibrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Panoramica dell'uso degli strumenti di telemetria di Skype for business online per monitorare un'implementazione locale in uno scenario ibrido.
ms.openlocfilehash: 3300ad17b109ac069c4f7382f610dd0214b30197
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328428"
---
# <a name="plan-call-data-connector"></a>Connettore dati chiamata piano

## <a name="overview"></a>Panoramica

Questo argomento descrive i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione di Skype for Business Server Call Data Connector. Per altre informazioni sulla configurazione del connettore dati chiamata, vedere [configurare il connettore dati chiamata](configure-call-data-connector.md).


Chiamata Data Connector semplifica notevolmente il monitoraggio delle chiamate in un ambiente ibrido perché non è più necessario usare set diversi di strumenti locali e online per monitorare tutta la qualità delle chiamate degli utenti. Indipendentemente dal fatto che gli utenti siano ospitati in locale o online, è possibile scegliere di visualizzare la qualità delle chiamate per l'intera organizzazione online.

Con il connettore dati chiamata, è possibile eseguire le attività seguenti usando un set di strumenti singoli:

- Monitorare l'esperienza utente in Microsoft teams, Skype for business online e Skype for Business Server.

- Visualizzare e risolvere i problemi in tutta la rete.

- Assegnare i ruoli di helpdesk e amministratore per l'analisi delle chiamate, in modo da consentire ai dipendenti dell'helpdesk di visualizzare e risolvere i problemi relativi alle aree di responsabilità.

Con il connettore data chiamata, Skype for Business Server inserisce i dati delle chiamate nel servizio cloud in modo da poter sfruttare gli strumenti di analisi delle chiamate (CA) Skype for business online e Call Quality Dashboard (Call Quality Dashboard), come illustrato nel diagramma seguente:

![Segreteria telefonica cloud di SfB](../../sfbserver2019/media/call-data-connector-plan-1.png)

Il server inserisce i dati di qualità dell'esperienza (QoE) e di registrazione dei dettagli delle chiamate (CDR) nel servizio online.

Gli strumenti di analisi delle chiamate e Call Quality dashboard consentono di monitorare la qualità delle chiamate e risolvere i problemi di connessione con i servizi Microsoft teams e Skype for business come segue:

- L'analisi delle chiamate si incentra sui problemi di qualità con chiamate specifiche. Mostra informazioni dettagliate su chiamate e riunioni per ogni utente in un account Skype for business.  Con le analisi delle chiamate è possibile assegnare autorizzazioni a un operatore dell'helpdesk che può quindi monitorare le chiamate senza accedere al resto dell'interfaccia di amministrazione di Skype for business.

- Il dashboard qualità chiamata si basa sulle prestazioni e i problemi di rete in un'organizzazione. Gli amministratori di Skype for business e gli ingegneri di rete usano questo strumento per risolvere i problemi e ottimizzare le prestazioni di rete.

Per altre informazioni, vedere [chiamare Analytics e Call Quality dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Naturalmente, potresti voler conservare alcuni dati sulla qualità delle chiamate in locale. Questo potrebbe essere il caso, ad esempio, se si usa una soluzione di terze parti con report e flussi di lavoro personalizzati.  Chiamata Data Connector consente di configurare l'invio di dati al servizio online mantenendo anche una copia dei dati nel server locale, come illustrato nel diagramma seguente:

![Segreteria telefonica cloud di SfB](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisiti

I requisiti seguenti presuppongono che si disponga già di Skype for Business Server distribuito in una topologia supportata.  Per altre informazioni sulla distribuzione di Skype for Business Server e delle topologie supportate, vedere [nozioni di base sulla topologia](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Per configurare il connettore dati chiamata, è necessario:

- Abilitare la connettività ibrida. Se è già stato distribuito Skype for Business Server e si vuole abilitare il connettore dati chiamata, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online. Questa operazione viene talvolta definita configurazione di domini divisi.

   Per altre informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Office 365](configure-hybrid-connectivity.md).

- Eseguire l'autenticazione nel tenant di Office 365 e verificare che siano abilitati i ruoli seguenti:

  - Amministratore di Skype for Business Server
  - Amministratore globale di Office 365

- Se non è già stato fatto, attivare il dashboard qualità chiamata, come descritto in [attivazione e utilizzo di Call Quality dashboard per Microsoft teams e Skype for business online](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Abilitare il pool Front-end per il monitoraggio, con i database LCSCdr e QoEMetrics locali. Senza questo, chiamata Data Connector non consentirà di usare i dati sulle metriche.

> [!IMPORTANT]
> Il connettore dati chiamata non funzionerà se il monitoraggio non è abilitato nel pool Front-end.

- Configurata correttamente [l'autenticazione da server a server](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications). 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Confronto tra i report di dashboard di qualità delle chiamate locali e online (Call Quality Dashboard)

| Report funzionalità | Skype for business online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Metrica di condivisione applicazioni |Sì | Limitata |
| Informazioni sulla creazione di clienti| Sì | Supporto per più paesi |
| Analisi drill-down | Sì | No |
| Metriche per l'affidabilità multimediale | Sì | Limitata |
| Report di out-of-the-box | Sì | Supporto per più paesi |
| Report generali | Sì | No |
| Report per utente | Sì | Supporto per più paesi |
| Personalizzazione del set di report <br> (Aggiungi, Elimina, modifica report) | Sì | Supporto per più paesi |
| Metriche di condivisione dello schermo basate su video | Sì | No |
| API dati per l'accesso a livello di programmazione <br> per Call Quality dashboard | No | Sì |
||||
