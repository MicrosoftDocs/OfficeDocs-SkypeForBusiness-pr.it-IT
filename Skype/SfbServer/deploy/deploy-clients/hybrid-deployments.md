---
title: Distribuzioni ibride di Skype room System
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
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente ibrido.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805896"
---
# <a name="skype-room-system-hybrid-deployments"></a>Distribuzioni ibride di Skype room System

Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente ibrido.
  
## <a name="hybrid-deployments"></a>Ambienti ibridi

Attenersi alla seguente procedura se la topologia include Skype for Business Server e Exchange Online e si desidera ospitare la cassetta postale per le risorse di sistema Skype room su Exchange Online. In questa sezione viene inoltre illustrato uno scenario ibrido in cui sono distribuiti sia Exchange Online che Exchange Server.
  
A scopo illustrativo, viene utilizzato LyncSample.com per il dominio locale e LyncSample.ccstp.net per il dominio online.
  
1. Creare una cassetta postale per le risorse nell'interfaccia di amministrazione di Exchange (LyncSample.ccsctp.net) mediante la connessione a Exchange Online Management Shell, come descritto in Exchange Online provisioning.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    È possibile verificare la connettività OWA utilizzando lrstest5@LyncSample.ccsctp.net per eseguire l'accesso.
    
2. Nell'interfaccia di amministrazione di Exchange di Microsoft 365 o Office 365, aggiungere un indirizzo di posta elettronica lrstest5@LyncSample.com (su-Prem Domain) e impostarlo come indirizzo di risposta.
    
3. Creare un utente di Active Directory lrstest5@LyncSample.com, impostare l'indirizzo di posta elettronica su lrstest5@LyncSample.com e impostare l'indirizzo di destinazione su lrstest5@LyncSample.com.
    
4. Attivare la sincronizzazione della directory e, dopo aver completato la sincronizzazione, verificare che gli utenti si fondono in AAD e che non sia possibile modificare le proprietà nelle risorse del destinatario nell'interfaccia di amministrazione di Microsoft 365 o Office 365 Exchange.
    
5. Verificare la connettività OWA mediante lrstest5@LyncSample.com. (In precedenza, è stata verificata la connettività OWA utilizzando il dominio online).
    
    Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing su Exchange Online Management Shell per configurare la cassetta postale. Per ulteriori informazioni, fare riferimento ai passaggi da 3 a 6 nelle distribuzioni on-Prem di una foresta singola.
    
   > [!NOTE]
   > Se si dispone di un ambiente ibrido con Exchange Server ed Exchange Online, accedere a Exchange Management Shell e Enable-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-room. Attivare quindi la sincronizzazione della directory. 
  
    Se si desidera ospitare la cassetta postale del sistema Skype room in Exchange Online, questi passaggi di Exchange Management Shell non sono necessari ed è possibile procedere con il passaggio 6.
    
6. Abilitare l'account di sistema della sala Skype per Skype for business eseguendo il cmdlet seguente su Skype for Business Management Shell:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se si ha Skype for business online invece di Skype for Business Server nello scenario sopra riportato, dopo aver provisionato la cassetta postale per le risorse di Exchange, eseguire il provisioning di un account Skype for business come descritto in Skype for business online. 
  

