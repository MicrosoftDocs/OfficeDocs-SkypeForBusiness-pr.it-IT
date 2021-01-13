---
title: Elenco di controllo prima esecuzione per il Pannello di controllo di Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.Home1stRunChkList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Benvenuti nel pannello di controllo di Skype for Business Server, l'interfaccia utente basata sul Web per l'amministrazione e la gestione di Skype for Business Server. È possibile utilizzare il pannello di controllo per eseguire i tipi di attività amministrative eseguite per l'utilizzo di Microsoft Management Console nelle versioni precedenti.
ms.openlocfilehash: fdd6aeefb6c4914dec54673f426c95c4028388ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836626"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Elenco di controllo prima esecuzione per il Pannello di controllo di Skype for Business Server

Benvenuti nel pannello di controllo di Skype for Business Server, l'interfaccia utente basata sul Web per l'amministrazione e la gestione di Skype for Business Server. È possibile utilizzare il pannello di controllo per eseguire i tipi di attività amministrative eseguite per l'utilizzo di Microsoft Management Console nelle versioni precedenti.

Vi sono una serie di attività importanti che è consigliabile eseguire dopo aver distribuito Skype for Business Server. Alcune di queste attività sono passaggi di configurazione iniziale che potrebbero essere già stati eseguiti durante la distribuzione, mentre altre sono miglioramenti o modifiche di impostazioni configurate durante la distribuzione o impostazioni predefinite. Altre attività descritte in questo argomento consentono di convalidare le configurazioni effettuate durante il processo di distribuzione.

> [!NOTE]
> Prima di eseguire le attività descritte nella tabella seguente, verificare di aver eseguito l'accesso utilizzando i diritti utente, le autorizzazioni e il ruolo corretti come descritto nella sezione "ruoli e ambito" dell'argomento relativo al [controllo di accesso basato sui](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) ruoli.

## <a name="first-run-checklist"></a>Elenco di controllo per la prima esecuzione

È consigliabile esaminare le attività a cui si fa riferimento in questo argomento e quindi eseguire le procedure appropriate per la distribuzione nell'organizzazione.

|**Attività**|**Gruppo del pannello di controllo**|**Documentazione**|
|:-----|:-----|:-----|
|Verificare che i servizi installati nella topologia vengano eseguiti come previsto.  <br/> |**Topologia** <br/> |[Visualizzare i dettagli relativi a un servizio](https://technet.microsoft.com/library/bc8e8202-cd68-47e4-95b2-bb36e51cc124.aspx) <br/> |
|Abilitare gli utenti per Skype for Business Server. Facoltativamente, se si esegue la migrazione da una versione precedente, spostare gli utenti in Skype for Business Server.  <br/> |**Utenti** <br/> |[Gestione degli utenti](https://technet.microsoft.com/library/8021087e-5084-4a39-9fef-ab9376c6d371.aspx) <br/> |
|Se è stata eseguita o si desidera eseguire la distribuzione di VoIP aziendale, configurare una connessione di trunk SIP per consentire la connettività alla rete PSTN (Public Switched Telephone Network).  <br/> |**Routing vocale** <br/> |[Configuring Trunks and translation Rules](https://technet.microsoft.com/library/0c339511-a185-484e-94f0-dbe918b7e48a.aspx) <br/> |
|Se è stato distribuito VoIP aziendale, verificare le relative impostazioni di routing.  <br/> |**Routing vocale** <br/> |[Testare il routing vocale](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx) <br/> |
|Se il server di archiviazione è stato distribuito, verificare che i criteri di archiviazione e le impostazioni soddisfino le esigenze di conformità dell'organizzazione.  <br/> |**Monitoraggio e archiviazione** <br/> |[Gestione dell'archiviazione](https://technet.microsoft.com/library/48c6cc8c-c2c1-4534-9a8a-fd5eb738076a.aspx) <br/> |
|Se il Monitoring Server è stato distribuito, visualizzare i relativi rapporti per esaminare le informazioni di utilizzo e di diagnostica.  <br/> |**Home** <br/> |[Gestione dell'integrità e del monitoraggio in Skype for Business Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |


