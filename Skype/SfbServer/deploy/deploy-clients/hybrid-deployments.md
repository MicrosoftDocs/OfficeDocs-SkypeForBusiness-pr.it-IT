---
title: Distribuzioni ibride di Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente ibrido.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805896"
---
# <a name="skype-room-system-hybrid-deployments"></a>Distribuzioni ibride di Skype Room System

Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente ibrido.
  
## <a name="hybrid-deployments"></a>Distribuzioni ibride

Seguire questa procedura se la topologia dispone di Skype for Business Server ed Exchange Online e si desidera ospitare la cassetta postale delle risorse di Skype Room System su Exchange Online. In questa sezione viene descritto anche uno scenario ibrido in cui sono distribuiti sia Exchange Online che Exchange Server distribuzione.
  
A scopo illustrativo, viene LyncSample.com per il dominio locale e LyncSample.ccstp.net per il dominio online.
  
1. Creare una cassetta postale delle risorse nell'interfaccia di amministrazione di Exchange (LyncSample.ccsctp.net) connettendosi a Exchange Online Management Shell come descritto in Provisioning di Exchange Online.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    È possibile verificare OWA connettività utilizzando lrstest5@LyncSample.ccsctp.net per accedere.
    
2. Nell'interfaccia di amministrazione di Microsoft 365 o Office 365 Exchange, aggiungere un indirizzo di posta elettronica lrstest5@LyncSample.com (dominio locale) e impostarlo come indirizzo di risposta.
    
3. Creare un lrstest5@LyncSample.com utente di Active Directory locale, impostare l'indirizzo di posta elettronica su lrstest5@LyncSample.com e impostare l'indirizzo di destinazione su lrstest5@LyncSample.com.
    
4. Attivare la sincronizzazione della directory e, al termine della sincronizzazione, verificare che gli utenti si uniscono ad AAD e che non sia possibile modificare le proprietà nelle risorse del destinatario nell'interfaccia di amministrazione di Microsoft 365 o Office 365 Exchange.
    
5. Verificare OWA connettività tramite lrstest5@LyncSample.com. In precedenza, è stata verificata OWA connettività tramite il dominio online.
    
    Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing exchange Online Management Shell per configurare la cassetta postale. Per ulteriori dettagli, vedere i passaggi da 3 a 6 nelle distribuzioni in locale a foresta singola.
    
   > [!NOTE]
   > Se si dispone di un ambiente ibrido con Exchange Server ed Exchange Online, passare a Exchange Management Shell e Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. Attivare quindi la sincronizzazione della directory. 
  
    Se si desidera ospitare la cassetta postale di Skype Room System in Exchange Online, questi passaggi di Exchange Management Shell non sono necessari ed è possibile procedere con il passaggio 6.
    
6. Abilitare l'account skype room system per Skype for Business eseguendo il cmdlet seguente in Skype for Business Management Shell:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se si dispone di Skype for Business online invece di Skype for Business Server nello scenario precedente, dopo aver effettuato il provisioning della cassetta postale delle risorse di Exchange, effettuare il provisioning di un account Skype for Business come descritto nel provisioning di Skype for Business online. 
  

