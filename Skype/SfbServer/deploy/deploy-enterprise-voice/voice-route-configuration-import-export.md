---
title: Esportare o importare un file di configurazione della route vocale in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Riepilogo: informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server utilizzando il Pannello Skype for Business Server di controllo.'
ms.openlocfilehash: 7b3b0ae7e7fe49b645fd5a6ee6b6b4d9fcc1affd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773226"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Esportare o importare un file di configurazione della route vocale in Skype for Business
 
**Riepilogo:** Informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server utilizzando il Pannello Skype for Business Server di controllo.
  
Se si desidera salvare la configurazione del routing vocale senza pubblicarla, eseguire la procedura seguente per salvare e recuperare uno snapshot della configurazione del routing vocale. 
  
Quando si importa un file di configurazione del routing vocale (con estensione vcfg), ma nel frattempo  sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo Routing vocale nel Pannello di controllo di Skype for Business Server indicheranno che sono state apportate modifiche non salvate al routing vocale. Tali modifiche costituiscono le differenze tra le due configurazioni di cui deve essere eseguita la riconciliazione.
  
Se sono state apportate modifiche non salvate alle impostazioni in qualsiasi pagina del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (con estensione vcfg). In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Per esportare una configurazione di routing vocale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator,** **CsServerAdministrator** o **CsAdministrator.**
    
2. Aprire Skype for Business Server Pannello di controllo.
    
3. Nella barra di spostamento sinistra fare clic su **Routing vocale**.
    
4. Scegliere **Esporta configurazione** dal menu **Azioni**.
    
5. Specificare un percorso e un nome di file e quindi fare clic su **Salva**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Per importare una configurazione di routing vocale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator,** **CsServerAdministrator** o **CsAdministrator.**
    
2. Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Routing vocale**.
    
4. Scegliere **Importa configurazione** dal menu **Azioni**.
    
5. Trovare il file di configurazione che si desidera importare e quindi fare clic su **Apri**.
    
6. Fare clic su **Commit** e quindi su **Salva tutto**.
    
    > [!NOTE]
    > Ogni volta che si importa un file di configurazione vocale, è necessario usare il comando **Salva tutto** per pubblicare la modifica di configurazione. Per informazioni dettagliate, vedere [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.
  

