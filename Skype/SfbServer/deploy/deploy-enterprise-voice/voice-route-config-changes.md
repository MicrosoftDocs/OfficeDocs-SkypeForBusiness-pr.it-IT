---
title: Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for Business
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
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Riepilogo: informazioni su come rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale in Skype for Business Server utilizzando il Pannello Skype for Business Server di controllo.'
ms.openlocfilehash: bf859dd7ed31a9a08fcba18af1b65cd1f34e8d16
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764854"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Pubblicare le modifiche in sospeso nella configurazione del routing vocale in Skype for Business
 
**Riepilogo:** Informazioni su come rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale in Skype for Business Server utilizzando il Pannello di controllo Skype for Business Server di controllo.
  
Dopo aver apportato modifiche alle impostazioni di configurazione nelle pagine del gruppo **Routing vocale**, eseguire questa procedura per esaminare, pubblicare o annullare le modifiche in sospeso.
  
> [!IMPORTANT]
> Verificare che un solo utente alla volta modifichi le impostazioni di configurazione di Routing vocale. 
  
> [!NOTE]
> Tutte le modifiche in sospeso devono essere pubblicate contemporaneamente eseguendo il comando **Salva tutto**. Non è possibile pubblicare selettivamente le modifiche in sospeso. Prima di pubblicare le modifiche in sospeso, eseguire il comando **Rivedi modifiche di cui non è stato eseguito il commit** e annullare qualsiasi modifica di configurazione che non si desidera pubblicare.
  
> [!NOTE]
> Se si esce dalle pagine del gruppo **Routing vocale** prima di eseguire il commit delle modifiche in sospeso, tutte le modifiche in sospeso andranno perse. Tuttavia, è possibile esportare la configurazione corrente (incluse le modifiche in sospeso) in un file di configurazione vocale e quindi importare e pubblicare la configurazione aggiornata. Per informazioni dettagliate, vedere [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Per rivedere, pubblicare o annullare le modifiche di configurazione del routing vocale

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator,** **CsServerAdministrator** o **CsAdministrator.**
    
2. Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Routing vocale**.
    
4. Apportare le modifiche della configurazione desiderate alle impostazioni in ogni pagina del gruppo **Routing vocale**.
    
5. Per rivedere le modifiche in sospeso senza pubblicarle, scegliere **Rivedi modifiche di cui non è stato eseguito il commit** dal menu **Commit**.
    
6. Se si desidera annullare qualsiasi modifica in sospeso, effettuare una delle operazioni seguenti:
    
   - Scegliere **Annulla tutte le modifiche di cui non è stato eseguito il commit** dal menu **Commit**.
    
   - Spostarsi sulla scheda della pagina **Routing vocale** che include le modifiche in sospeso che si desidera annullare, selezionare l'elemento con le modifiche in sospeso, fare clic su **Commit** e quindi su **Annulla modifiche selezionate**.
    
7. Dopo aver rivisto tutte le modifiche in sospeso e annullato ogni modifica che non si desidera pubblicare, fare clic su **Commit** e quindi su **Salva tutto**.
    
8. Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** in cui è visualizzato un elenco delle modifiche in sospeso fare clic su **OK**. 
    
    Quando Skype for Business Server di controllo ha eseguito il commit delle modifiche, viene visualizzato il **messaggio Configurazione routing vocale** pubblicato correttamente.
    

