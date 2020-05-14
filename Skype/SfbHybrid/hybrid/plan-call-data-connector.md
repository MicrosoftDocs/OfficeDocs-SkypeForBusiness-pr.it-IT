---
title: Pianificare il connettore dei dati delle chiamate | Dashboard qualità chiamata monitoraggio di analisi ibride
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
description: Panoramica sull'utilizzo degli strumenti di telemetria di Skype for business online per monitorare un'implementazione locale in uno scenario ibrido.
ms.openlocfilehash: 30ff8aebc739e0602f9700cbe9120d230845a023
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221316"
---
# <a name="plan-call-data-connector"></a>Pianificare il connettore dei dati delle chiamate

## <a name="overview"></a>Panoramica

In questo argomento vengono descritti i vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del connettore dei dati delle chiamate di Skype for Business Server. Per ulteriori informazioni sulla configurazione del connettore dei dati di chiamata, vedere [Configure Call Data Connector](configure-call-data-connector.md).


Il connettore dei dati di chiamata semplifica notevolmente il monitoraggio delle chiamate in un ambiente ibrido, perché non è più necessario utilizzare insiemi diversi di strumenti locali e online per monitorare tutti gli utenti della qualità delle chiamate. Se gli utenti sono ospitati in locale o online, è possibile scegliere di visualizzare la qualità delle chiamate per l'intera organizzazione online.

Con connettore dati chiamata, è possibile eseguire le attività seguenti utilizzando un singolo set di strumenti:

- Monitorare la propria esperienza utente in Microsoft teams, Skype for business online e Skype for Business Server.

- Visualizzare e risolvere i problemi della rete.

- Assegnare i ruoli di helpdesk e amministratore per l'analisi delle chiamate, in modo da consentire agli addetti al supporto tecnico di visualizzare e risolvere i problemi relativi alle aree di responsabilità.

Con il connettore dei dati di chiamata, Skype for Business Server spinge i dati delle chiamate al servizio cloud in modo che sia possibile sfruttare gli strumenti di gestione delle chiamate (CA) di Skype for business online e CQD (Call Quality Dashboard), come illustrato nel diagramma seguente:

![Segreteria telefonica cloud di questo](../../sfbserver2019/media/call-data-connector-plan-1.png)

Il server consente di inserire i dati QoE (Quality of Experience) e registrazione dettagli chiamata (CDR) nel servizio online.

Gli strumenti di analisi delle chiamate e CQD consentono di monitorare la qualità delle chiamate e risolvere i problemi di connessione con i servizi Microsoft teams e Skype for business, come indicato di seguito:

- L'analisi delle chiamate si concentra sui problemi di qualità con chiamate specifiche. Visualizza informazioni dettagliate sulle chiamate e le riunioni per ogni utente in un account Skype for business.  Con l'analisi delle chiamate, è possibile assegnare autorizzazioni a un operatore del supporto tecnico che può quindi monitorare le chiamate senza dover accedere al resto dell'interfaccia di amministrazione di Skype for business.

- Call Quality dashboard si concentra sulle prestazioni e sui problemi di rete in un'organizzazione. Gli amministratori di Skype for business e gli ingegneri di rete utilizzano questo strumento per risolvere i problemi e ottimizzare le prestazioni della rete.

Per ulteriori informazioni, vedere [Call Analytics and call Quality dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).

Naturalmente, potrebbe essere necessario mantenere alcuni dati sulla qualità delle chiamate in locale. Questo potrebbe essere il caso, ad esempio, se si utilizza una soluzione di terze parti con report e flussi di lavoro personalizzati.  Call Data Connector consente di configurare i dati per l'invio al servizio online mantenendo anche una copia dei dati nel server locale, come illustrato nel diagramma seguente:

![Segreteria telefonica cloud di questo](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a>Requisiti

I requisiti seguenti presumono che sia già stato distribuito Skype for Business Server in una topologia supportata.  Per ulteriori informazioni sulla distribuzione di Skype for Business Server e delle topologie supportate, vedere [nozioni di base sulla topologia](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics). Per configurare il connettore dei dati di chiamata, è necessario eseguire le operazioni seguenti:

- Abilitare la connettività ibrida. Se è già stato distribuito Skype for Business Server e si desidera abilitare il connettore dei dati di chiamata, è necessario verificare di disporre della connettività ibrida configurata tra gli ambienti locali e online. A volte viene chiamata configurazione di un dominio diviso.

   Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e microsoft 365 o office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Microsoft 365 o Office 365](configure-hybrid-connectivity.md).

- Eseguire l'autenticazione nell'organizzazione Microsoft 365 o Office 365 e verificare di aver abilitato i ruoli seguenti:

  - Amministratore di Skype for Business Server
  - Microsoft 365 o Office 365 Global Administrator

- Se non è stato ancora fatto, attiva il dashboard qualità chiamata, come descritto in [attivazione e utilizzo di Call Quality dashboard per Microsoft teams e Skype for business online](/microsoftteams/turning-on-and-using-call-quality-dashboard).

- Abilitare il pool Front end per il monitoraggio, con i database di LCSCdr e QoEMetrics locali. Senza questo, non è possibile utilizzare i dati di metrica per le chiamate.

> [!IMPORTANT]
> Il connettore dei dati di chiamata non funzionerà se il monitoraggio non è abilitato nel pool Front end.

- [Autenticazione da server a server](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)configurata in modo appropriato. 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a>Confronto tra i report di CQD (Call Quality dashboard on-premises e online)

| Report delle funzionalità | Skype for Business online | Skype for Business Server   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| Metrica per la condivisione di applicazioni |Sì | Limitato |
| Informazioni sull'edificio dei clienti| Sì | Sì |
| Analisi drill-down | Sì | No |
| Metriche di affidabilità multimediale | Sì | Limitato |
| Report out-of-the-box | Sì | Sì |
| Rapporti generali | Sì | No |
| Rapporti per utente | Sì | Sì |
| Personalizzazione del set di report <br> (aggiunta, eliminazione, modifica di report) | Sì | Sì |
| Metriche di condivisione dello schermo basate su video | Sì | No |
| API dei dati per l'accesso a livello di programmazione <br> per CQD | No | Sì |
||||
