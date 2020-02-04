---
title: Elenco di controllo prima esecuzione per il Pannello di controllo di Skype for Business Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
description: Benvenuti nel pannello di controllo di Skype for Business Server, l'interfaccia utente basata sul Web per l'amministrazione e la gestione di Skype for Business Server. È possibile utilizzare il Pannello di controllo per eseguire i tipi di attività amministrative eseguiti mediante Microsoft Management Console nelle versioni precedenti.
ms.openlocfilehash: 4b22171b5094fa067bff683ed05477caf68afcd9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700151"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Elenco di controllo prima esecuzione per il Pannello di controllo di Skype for Business Server.

Benvenuti nel pannello di controllo di Skype for Business Server, l'interfaccia utente basata sul Web per l'amministrazione e la gestione di Skype for Business Server. È possibile utilizzare il Pannello di controllo per eseguire i tipi di attività amministrative eseguiti mediante Microsoft Management Console nelle versioni precedenti.

Esistono numerose attività importanti che consigliamo vivamente di eseguire dopo la distribuzione di Skype for Business Server. Alcune di queste attività sono passaggi di configurazione iniziale che potrebbero essere già stati eseguiti durante la distribuzione, mentre altre sono miglioramenti o modifiche di impostazioni configurate durante la distribuzione o impostazioni predefinite. Altre attività descritte in questo argomento consentono di convalidare le configurazioni effettuate durante il processo di distribuzione.

> [!NOTE]
> Prima di eseguire le attività riportate nella tabella seguente, eseguire l'accesso con i diritti utente, le autorizzazioni e il ruolo corretti, descritti nella sezione "Ruoli e ambito" dell'argomento [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx).

## <a name="first-run-checklist"></a>Elenco di controllo per la prima esecuzione

È consigliabile esaminare le attività a cui si fa riferimento in questo argomento e quindi eseguire le procedure appropriate per la distribuzione di Lync Server nell'organizzazione.

|**Attività**|**Gruppo Pannello di controllo**|**Documentazione**|
|:-----|:-----|:-----|
|Verificare che i servizi installati nella topologia vengano eseguiti come previsto.  <br/> |**Topologia** <br/> |[View Details About a Service](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Abilitare gli utenti per Skype for Business Server. Facoltativamente, se si esegue la migrazione da una versione precedente, trasferire gli utenti in Skype for Business Server.  <br/> |**Utenti** <br/> |[Managing Users](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Se è stata eseguita o si desidera eseguire la distribuzione di VoIP aziendale, configurare una connessione di trunk SIP per consentire la connettività alla rete PSTN (Public Switched Telephone Network).  <br/> |**Routing vocale** <br/> |[Configuring Trunks and Translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Se è stato distribuito VoIP aziendale, verificare le relative impostazioni di routing.  <br/> |**Routing vocale** <br/> |[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Se il server di archiviazione è stato distribuito, verificare che i criteri di archiviazione e le impostazioni soddisfino le esigenze di conformità dell'organizzazione.  <br/> |**Monitoraggio e archiviazione** <br/> |[Managing Archiving](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Se il Monitoring Server è stato distribuito, visualizzare i relativi rapporti per esaminare le informazioni di utilizzo e di diagnostica.  <br/> |**Home** <br/> |[Gestire monitoraggio e integrità in Skype for Business](../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


