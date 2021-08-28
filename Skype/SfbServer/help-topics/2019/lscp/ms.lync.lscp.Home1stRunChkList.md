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
ms.localizationpriority: medium
ms.assetid: 4d0c7306-e87e-464a-82ad-a5537f141500
ROBOTS: NOINDEX, NOFOLLOW
description: Benvenuti nel Pannello Skype for Business Server, l'interfaccia utente basata sul Web per l'amministrazione e la gestione di Skype for Business Server. È possibile utilizzare il Pannello di controllo per eseguire i tipi di attività amministrative eseguite tramite Microsoft Management Console nelle versioni precedenti.
ms.openlocfilehash: 05f2882622325ed9b4bdb837811941ccb34b0401
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609775"
---
# <a name="first-run-checklist-for-skype-for-business-server-control-panel"></a>Elenco di controllo prima esecuzione per il Pannello di controllo di Skype for Business Server

Benvenuti nel Pannello Skype for Business Server, l'interfaccia utente basata sul Web per l'amministrazione e la gestione di Skype for Business Server. È possibile utilizzare il Pannello di controllo per eseguire i tipi di attività amministrative eseguite tramite Microsoft Management Console nelle versioni precedenti.

È consigliabile eseguire una serie di attività importanti dopo aver distribuito Skype for Business Server. Alcune di queste attività sono passaggi di configurazione iniziale che potrebbero essere già stati eseguiti durante la distribuzione, mentre altre sono miglioramenti o modifiche di impostazioni configurate durante la distribuzione o impostazioni predefinite. Altre attività descritte in questo argomento consentono di convalidare le configurazioni effettuate durante il processo di distribuzione.

> [!NOTE]
> Prima di eseguire le attività nella tabella seguente, assicurarsi di accedere utilizzando i diritti utente, le autorizzazioni e il ruolo corretti, come descritto nella sezione "Ruoli e ambito" dell'argomento [Role-Based Access Control.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)

## <a name="first-run-checklist"></a>Elenco di controllo per la prima esecuzione

È consigliabile esaminare le attività descritte in questo argomento e quindi eseguire le procedure appropriate per la distribuzione nell'organizzazione.

|**Attività**|**Gruppo Pannello di controllo**|**Documentazione**|
|:-----|:-----|:-----|
|Verificare che i servizi installati nella topologia vengano eseguiti come previsto.  <br/> |**Topologia** <br/> |[Visualizzare i dettagli di un servizio](/previous-versions/office/lync-server-2013/lync-server-2013-view-details-about-a-service) <br/> |
|Abilitare gli utenti per Skype for Business Server. Facoltativamente e, se si esegue la migrazione da una versione precedente, spostare gli utenti in Skype for Business Server.  <br/> |**Utenti** <br/> |[Gestione degli utenti](/previous-versions/office/lync-server-2013/lync-server-2013-user-accounts-enabled-for-lync-server) <br/> |
|Se è stata eseguita o si desidera eseguire la distribuzione di VoIP aziendale, configurare una connessione di trunk SIP per consentire la connettività alla rete PSTN (Public Switched Telephone Network).  <br/> |**Routing vocale** <br/> |[Configurazione di trunk e regole di conversione](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-trunks) <br/> |
|Se è stato distribuito VoIP aziendale, verificare le relative impostazioni di routing.  <br/> |**Routing vocale** <br/> |[Testare il routing vocale](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing) <br/> |
|Se il server di archiviazione è stato distribuito, verificare che i criteri di archiviazione e le impostazioni soddisfino le esigenze di conformità dell'organizzazione.  <br/> |**Monitoraggio e archiviazione** <br/> |[Gestione dell'archiviazione](/previous-versions/office/lync-server-2013/lync-server-2013-managing-archiving) <br/> |
|Se il Monitoring Server è stato distribuito, visualizzare i relativi rapporti per esaminare le informazioni di utilizzo e di diagnostica.  <br/> |**Home** <br/> |[Gestire l'integrità e il monitoraggio in Skype for Business Server](../../../manage/health-and-monitoring/health-and-monitoring.md) <br/> |