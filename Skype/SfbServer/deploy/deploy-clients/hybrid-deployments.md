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
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="30512-103">Distribuzioni ibride di Skype Room System</span><span class="sxs-lookup"><span data-stu-id="30512-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="30512-104">Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="30512-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="30512-105">Distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="30512-105">Hybrid deployments</span></span>

<span data-ttu-id="30512-106">Seguire questa procedura se la topologia dispone di Skype for Business Server ed Exchange Online e si desidera ospitare la cassetta postale delle risorse di Skype Room System su Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="30512-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="30512-107">In questa sezione viene descritto anche uno scenario ibrido in cui sono distribuiti sia Exchange Online che Exchange Server distribuzione.</span><span class="sxs-lookup"><span data-stu-id="30512-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="30512-108">A scopo illustrativo, viene LyncSample.com per il dominio locale e LyncSample.ccstp.net per il dominio online.</span><span class="sxs-lookup"><span data-stu-id="30512-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="30512-109">Creare una cassetta postale delle risorse nell'interfaccia di amministrazione di Exchange (LyncSample.ccsctp.net) connettendosi a Exchange Online Management Shell come descritto in Provisioning di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="30512-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="30512-110">È possibile verificare OWA connettività utilizzando lrstest5@LyncSample.ccsctp.net per accedere.</span><span class="sxs-lookup"><span data-stu-id="30512-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="30512-111">Nell'interfaccia di amministrazione di Microsoft 365 o Office 365 Exchange, aggiungere un indirizzo di posta elettronica lrstest5@LyncSample.com (dominio locale) e impostarlo come indirizzo di risposta.</span><span class="sxs-lookup"><span data-stu-id="30512-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="30512-112">Creare un lrstest5@LyncSample.com utente di Active Directory locale, impostare l'indirizzo di posta elettronica su lrstest5@LyncSample.com e impostare l'indirizzo di destinazione su lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="30512-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="30512-113">Attivare la sincronizzazione della directory e, al termine della sincronizzazione, verificare che gli utenti si uniscono ad AAD e che non sia possibile modificare le proprietà nelle risorse del destinatario nell'interfaccia di amministrazione di Microsoft 365 o Office 365 Exchange.</span><span class="sxs-lookup"><span data-stu-id="30512-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="30512-114">Verificare OWA connettività tramite lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="30512-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="30512-115">In precedenza, è stata verificata OWA connettività tramite il dominio online.</span><span class="sxs-lookup"><span data-stu-id="30512-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="30512-116">Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing exchange Online Management Shell per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="30512-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="30512-117">Per ulteriori dettagli, vedere i passaggi da 3 a 6 nelle distribuzioni in locale a foresta singola.</span><span class="sxs-lookup"><span data-stu-id="30512-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="30512-118">Se si dispone di un ambiente ibrido con Exchange Server ed Exchange Online, passare a Exchange Management Shell e Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span><span class="sxs-lookup"><span data-stu-id="30512-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="30512-119">Attivare quindi la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="30512-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="30512-120">Se si desidera ospitare la cassetta postale di Skype Room System in Exchange Online, questi passaggi di Exchange Management Shell non sono necessari ed è possibile procedere con il passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="30512-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="30512-121">Abilitare l'account skype room system per Skype for Business eseguendo il cmdlet seguente in Skype for Business Management Shell:</span><span class="sxs-lookup"><span data-stu-id="30512-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="30512-122">Se si dispone di Skype for Business online invece di Skype for Business Server nello scenario precedente, dopo aver effettuato il provisioning della cassetta postale delle risorse di Exchange, effettuare il provisioning di un account Skype for Business come descritto nel provisioning di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="30512-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

