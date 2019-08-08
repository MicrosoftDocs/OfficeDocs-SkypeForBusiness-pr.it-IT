---
title: Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business
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
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Riepilogo: informazioni su come rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: 6a13c2a2b2b1221203fbed84948b803a6c2ea1db
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240193"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for business
 
**Riepilogo:** Informazioni su come rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale in Skype for Business Server tramite il pannello di controllo di Skype for Business Server.
  
Dopo aver apportato le modifiche alle impostazioni di configurazione nelle pagine del gruppo **routing vocale** , eseguire questa procedura per rivedere, pubblicare o annullare le modifiche in sospeso.
  
> [!IMPORTANT]
> Assicurarsi che solo un utente alla volta modifichi le impostazioni di configurazione del routing vocale. 
  
> [!NOTE]
> Tutte le modifiche in sospeso devono essere pubblicate contemporaneamente eseguendo il comando **commit tutti** . Non è possibile pubblicare in modo selettivo le modifiche in sospeso. Prima di pubblicare le modifiche in sospeso, eseguire il comando **revisione delle modifiche non salvate** e annullare le modifiche di configurazione che non si desidera pubblicare.
  
> [!NOTE]
> Se si esce dalle pagine del gruppo **routing vocale** prima di confermare le modifiche in sospeso, tutte le modifiche in sospeso andranno perse. È tuttavia possibile esportare la configurazione corrente (incluse le eventuali modifiche in sospeso) in un file di configurazione vocale e quindi importare e pubblicare la configurazione aggiornata. Per informazioni dettagliate, vedere [esportare o importare un file di configurazione della route vocale in Skype for business](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Per rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **routing vocale**.
    
4. Apportare le modifiche di configurazione desiderate alle impostazioni in ogni pagina del gruppo di **routing vocale** .
    
5. Per rivedere le modifiche in sospeso senza pubblicarle, selezionare **rivedere le modifiche non salvate** dal menu **conferma** .
    
6. Se si vuole annullare una delle modifiche in sospeso, eseguire una delle operazioni seguenti:
    
   - Selezionare **Annulla tutte le modifiche non salvate** dal menu **conferma** .
    
   - Passare alla scheda della pagina di **routing vocale** contenente le modifiche in sospeso che si desidera annullare, selezionare l'elemento con le modifiche in sospeso, fare clic su **commit**e quindi su **Annulla modifiche selezionate**.
    
7. Dopo aver esaminato tutte le modifiche in sospeso e annullato qualsiasi che non si vuole pubblicare, fare clic su **commit**e quindi su **commit tutti**.
    
8. Nella finestra di dialogo **impostazioni di configurazione vocale** non impegnata, in cui viene visualizzato un elenco di tutte le modifiche in sospeso, fare clic su **OK**. 
    
    Quando il pannello di controllo di Skype for Business Server ha eseguito il commit delle modifiche, viene visualizzato il messaggio di **configurazione del routing vocale pubblicato correttamente** .
    

