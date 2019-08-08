---
title: Esportare o importare un file di configurazione della route vocale in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Riepilogo: informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: ec5a3d0c7f14d85a7b64eaad1edc73ebe4e24cd2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240170"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Esportare o importare un file di configurazione della route vocale in Skype for business
 
**Riepilogo:** Informazioni su come esportare o importare un file di configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.
  
Se si vuole salvare la configurazione del routing vocale senza pubblicarla, seguire questa procedura per salvare e recuperare uno snapshot della configurazione del routing vocale. 
  
Quando si importa un file di configurazione del routing vocale (con estensione vcfg), ma nel frattempo sono state apportate modifiche alla configurazione del routing vocale nel server, le pagine del gruppo **routing vocale** nel pannello di controllo di Skype for Business Server indicheranno che le modifiche apportate al routing vocale non vengono salvate. Le modifiche non salvate sono le differenze tra le due configurazioni che richiedono la riconciliazione.
  
Se sono state apportate modifiche non salvate alle impostazioni di una pagina all'interno del gruppo, le modifiche vengono salvate nel file di configurazione vocale esportato (. vcfg). In questo modo è possibile apportare modifiche alla configurazione del routing vocale durante più sessioni prima di pubblicare le modifiche. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Per esportare una configurazione di routing vocale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **routing vocale**.
    
4. Nel menu **azioni** fare clic su **Esporta configurazione**.
    
5. Specificare un percorso e un nome file e quindi fare clic su **Salva**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Per importare una configurazione di routing vocale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **routing vocale**.
    
4. Nel menu **azioni** fare clic su **Importa configurazione**.
    
5. Individuare il file di configurazione da importare e quindi fare clic su **Apri**.
    
6. Fare clic su **commit**e quindi su **Commit all**.
    
    > [!NOTE]
    > Ogni volta che si importa un file di configurazione vocale, è necessario eseguire il comando **commit tutti** per pubblicare la modifica della configurazione. Per informazioni dettagliate, vedere [pubblicare le modifiche in sospeso alla configurazione del routing vocale in Skype for business](voice-route-config-changes.md) nella documentazione Operations.
  

