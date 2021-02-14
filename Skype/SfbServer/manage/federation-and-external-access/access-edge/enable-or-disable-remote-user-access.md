---
title: Abilitare o disabilitare l'accesso utente remoto
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se si abilita l'accesso degli utenti remoti per gli utenti remoti, gli utenti remoti supportati si connettono tramite Internet e non devono connettersi utilizzando una VPN per collaborare con gli utenti interni tramite Skype for Business Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817396"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Abilitare o disabilitare l'accesso degli utenti remoti in Skype for Business Server

Gli utenti remoti sono utenti dell'organizzazione che dispongono di un'identità Active Directory permanente nell'organizzazione. Gli utenti remoti spesso a cui si accede a Skype for Business Server dall'esterno della rete utilizzando una rete privata virtuale (VPN) quando non sono connessi alla rete dell'organizzazione. Tra gli utenti remoti sono inclusi i dipendenti che lavorano dalla propria abitazione o in viaggio e altri lavoratori remoti, ad esempio fornitori considerati attendibili a cui sono state concesse credenziali aziendali. Se si abilita l'accesso degli utenti remoti per gli utenti remoti, gli utenti remoti supportati si connettono tramite Internet e non devono connettersi utilizzando una VPN per collaborare con gli utenti interni tramite Skype for Business Server.

Per supportare l'accesso degli utenti remoti, è necessario abilitarlo. Quando si abilita l'accesso degli utenti remoti, tale impostazione si applica all'intera organizzazione. Se successivamente si desidera impedire, in modo temporaneo o permanente, l'accesso degli utenti remoti, è possibile disabilitarlo per l'organizzazione. Attenersi alla procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione.


> [!NOTE]  
> Abilitando l'accesso degli utenti remoti, si specifica soltanto che i server che eseguono il servizio Access Edge supportano le comunicazioni con gli utenti remoti, ma questi ultimi non possono utilizzare la messaggistica istantanea o partecipare a conferenze nell'organizzazione finché non si configura almeno un criterio per la gestione dell'utilizzo dell'accesso degli utenti remoti. Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto. Per informazioni dettagliate sulla configurazione dei criteri per l'utilizzo dell'accesso degli utenti remoti, vedere Configurare i criteri per controllare l'accesso degli utenti [remoti in Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Configurazione Access Edge**.

4.  Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti remoti per l'organizzazione, selezionare la casella di controllo **Abilita accesso remoto utenti**.
    
      - Per disabilitare l'accesso degli utenti remoti per l'organizzazione, deselezionare la casella di controllo **Abilita accesso remoto utenti**.

6.  Fare clic su **Commit**.

Per consentire agli utenti remoti di accedere ai server che eseguono Skype for Business Server, è inoltre necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti remoti. Per informazioni dettagliate, vedere [Configurare i criteri per controllare l'accesso degli utenti remoti in Skype for Business Server.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'accesso degli utenti remoti tramite Windows PowerShell cmdlet

L'accesso degli utenti remoti può essere gestito utilizzando Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration remoto. Questo cmdlet può essere eseguito da Skype for Business Server 2013 Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Per abilitare l'accesso degli utenti remoti

  - Per abilitare l'accesso degli utenti remoti, impostare il valore della proprietà **AllowOutsideUsers** su True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Per disabilitare l'accesso degli utenti remoti

  - Per disabilitare l'accesso degli utenti remoti, impostare il valore della proprietà **AllowOutsideUsers** su False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


