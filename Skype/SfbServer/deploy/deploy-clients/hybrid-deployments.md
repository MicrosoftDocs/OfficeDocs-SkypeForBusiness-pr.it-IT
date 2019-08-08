---
title: Distribuzioni ibride di Skype room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente ibrido.
ms.openlocfilehash: 016a4cf379200dc87b8f94d13a65f10f6c3af25f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234430"
---
# <a name="skype-room-system-hybrid-deployments"></a>Distribuzioni ibride di Skype room System

Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente ibrido.
  
## <a name="hybrid-deployments"></a>Distribuzioni ibride

Seguire questa procedura se la topologia include Skype for Business Server e Exchange Online e si vuole ospitare la cassetta postale delle risorse di sistema room Skype in Exchange Online. Questa sezione copre anche uno scenario ibrido in cui sono stati distribuiti sia Exchange Online che Exchange Server.
  
Per scopi illustrativi, usiamo LyncSample.com per il dominio locale e LyncSample.ccstp.net per il dominio online.
  
1. Creare una cassetta postale delle risorse nell'interfaccia di amministrazione di Exchange (LyncSample.ccsctp.net) connettendosi a Exchange Online Management Shell come descritto in provisioning di Exchange Online.
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Puoi verificare la connettività OWA usando lrstest5@LyncSample.ccsctp.net per accedere.
    
2. Nell'interfaccia di amministrazione di Exchange di Office 365 aggiungere un indirizzo di posta elettronica lrstest5@LyncSample.com (dominio su Prem) e impostarlo come indirizzo di risposta.
    
3. Creare un lrstest5@LyncSample.com utente di Active Directory on-Prem, impostare l'indirizzo di posta elettronica su lrstest5@LyncSample.com e impostare l'indirizzo di destinazione su lrstest5@LyncSample.com.
    
4. Attiva la sincronizzazione della directory e, dopo il completamento della sincronizzazione, verifica che gli utenti si fondono in AAD e che non sia possibile modificare le proprietà nelle risorse del destinatario nell'interfaccia di amministrazione di Exchange di Office365.
    
5. Verificare la connettività OWA con lrstest5@LyncSample.com. Prima hai verificato la connettività OWA usando il dominio online.
    
    Dopo aver creato la cassetta postale, è possibile usare Set-CalendarProcessing in Exchange Online Management Shell per configurare la cassetta postale. Fare riferimento ai passaggi da 3 a 6 in distribuzioni singole in una foresta per maggiori dettagli.
    
   > [!NOTE]
   > Se si ha un ambiente ibrido con Exchange Server ed Exchange Online, accedere a Exchange Management Shell e abilitare-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-room. Attiva quindi la sincronizzazione della directory. 
  
    Se si vuole ospitare la cassetta postale di sistema Skype room in Exchange Online, questi passaggi di Exchange Management Shell non sono necessari ed è possibile procedere con il passaggio 6.
    
6. Abilitare l'account di sistema room Skype per Skype for business eseguendo il cmdlet seguente in Skype for Business Management Shell:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se si ha Skype for business online invece di Skype for Business Server nello scenario precedente, dopo aver provisionato la cassetta postale delle risorse di Exchange, eseguire il provisioning di un account Skype for business come descritto in Skype for business online. 
  

