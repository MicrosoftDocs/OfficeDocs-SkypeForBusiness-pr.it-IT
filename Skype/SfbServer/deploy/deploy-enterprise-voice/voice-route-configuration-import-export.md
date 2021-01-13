---
title: Esportare o importare un file di configurazione di route vocali in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Riepilogo: informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830356"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Esportare o importare un file di configurazione di route vocali in Skype for business
 
**Riepilogo:** Informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.
  
Se si desidera salvare la configurazione del routing vocale senza pubblicarla, attenersi alla seguente procedura per salvare e recuperare un'istantanea della configurazione del routing vocale. 
  
Quando si importa un file di configurazione del routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo di **routing vocale** nel pannello di controllo di Skype for Business Server indicheranno che non sono state salvate modifiche al routing vocale. Tali modifiche costituiscono le differenze tra le due configurazioni di cui deve essere eseguita la riconciliazione.
  
Se sono state apportate modifiche non salvate alle impostazioni in una pagina all'interno del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (con estensione vcfg). In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Per esportare una configurazione di routing vocale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator** .
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Nella barra di spostamento sinistra fare clic su **Routing vocale**.
    
4. Scegliere **Esporta configurazione** dal menu **Azioni**.
    
5. Specificare un percorso e un nome di file e quindi fare clic su **Salva**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Per importare una configurazione di routing vocale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator** .
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Routing vocale**.
    
4. Scegliere **Importa configurazione** dal menu **Azioni**.
    
5. Trovare il file di configurazione che si desidera importare e quindi fare clic su **Apri**.
    
6. Fare clic su **Commit** e quindi su **Salva tutto**.
    
    > [!NOTE]
    > Ogni volta che si importa un file di configurazione vocale, è necessario usare il comando **Salva tutto** per pubblicare la modifica di configurazione. Per ulteriori informazioni, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione relativa alle operazioni.
  

