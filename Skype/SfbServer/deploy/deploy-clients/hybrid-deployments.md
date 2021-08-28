---
title: Skype Distribuzioni ibride del sistema sala
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente ibrido.
ms.openlocfilehash: b5a512871a60a502d1e2f5e981593291149d3361
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598190"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Distribuzioni ibride del sistema sala

Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente ibrido.
  
## <a name="hybrid-deployments"></a>Distribuzioni ibride

Eseguire questa procedura se la topologia dispone di Skype for Business Server e Exchange Online e si desidera ospitare la cassetta postale della risorsa Skype Room System Exchange Online. In questa sezione viene inoltre illustrato uno scenario ibrido in cui sono stati distribuiti Exchange Online e Exchange Server distribuzione.
  
A scopo illustrativo, usiamo LyncSample.com per il dominio locale e LyncSample.ccstp.net per il dominio online.
  
1. Creare una cassetta postale delle risorse Exchange interfaccia di amministrazione (LyncSample.ccsctp.net) connettendosi a Exchange Online Management Shell, come descritto in Exchange Online Provisioning.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    È possibile verificare OWA connettività utilizzando lrstest5@LyncSample.ccsctp.net per accedere.
    
2. Nell'Microsoft 365 o Office 365 Exchange, aggiungere un indirizzo di posta elettronica lrstest5@LyncSample.com (dominio locale) e impostarlo come indirizzo di risposta.
    
3. Creare un account utente di Active Directory locale lrstest5@LyncSample.com, impostare l'indirizzo di posta elettronica su lrstest5@LyncSample.com e impostare l'indirizzo di destinazione su lrstest5@LyncSample.com.
    
4. Attivare la sincronizzazione della directory e, al termine della sincronizzazione, verificare che gli utenti si uniscono in AAD e che non sia possibile modificare le proprietà nelle risorse del destinatario nell'interfaccia di amministrazione di Microsoft 365 o Office 365 Exchange.
    
5. Verificare OWA connettività tramite lrstest5@LyncSample.com. In precedenza, è stata verificata OWA connettività tramite il dominio online.
    
    Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing in Exchange Online Management Shell per configurare la cassetta postale. Per ulteriori dettagli, vedere i passaggi da 3 a 6 in Single Forest On-prem Deployments.
    
   > [!NOTE]
   > Se si dispone di un ambiente ibrido con Exchange Server e Exchange Online, passare a Exchange Management Shell e Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. Attivare quindi la sincronizzazione della directory. 
  
    Se si desidera ospitare la cassetta postale di Skype Room System in Exchange Online, questi passaggi di Exchange Management Shell non sono necessari ed è possibile procedere al passaggio 6.
    
6. Abilitare l'account Skype Room System per Skype for Business eseguendo il cmdlet seguente in Skype for Business Management Shell:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se è stato Skype for Business Online anziché Skype for Business Server nello scenario precedente, dopo aver effettuato il provisioning della cassetta postale della risorsa Exchange, effettuare il provisioning di un account Skype for Business come descritto in provisioning online Skype for Business. 
  

