---
title: Abilitare o disabilitare l'accesso degli utenti remoti
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se si Abilita l'accesso remoto agli utenti remoti, gli utenti remoti supportati si connettono tramite Internet e non devono connettersi tramite una VPN per collaborare con utenti interni tramite Skype for Business Server.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188867"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Abilitare o disabilitare l'accesso remoto agli utenti in Skype for Business Server

Gli utenti remoti sono utenti dell'organizzazione che hanno un'identità Active Directory persistente all'interno dell'organizzazione. Gli utenti remoti spesso accedono a Skype for Business Server dall'esterno della rete usando una rete privata virtuale (VPN) quando non sono connessi alla rete dell'organizzazione. Gli utenti remoti includono dipendenti che lavorano a casa o in viaggio e altri lavoratori remoti, ad esempio fornitori attendibili, a cui sono state concesse le credenziali dell'organizzazione. Se si Abilita l'accesso remoto agli utenti remoti, gli utenti remoti supportati si connettono tramite Internet e non devono connettersi tramite una VPN per collaborare con utenti interni tramite Skype for Business Server.

Per supportare l'accesso degli utenti remoti, è necessario abilitare l'accesso degli utenti remoti. Quando si Abilita l'accesso remoto agli utenti, è possibile abilitarlo per l'intera organizzazione. Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso degli utenti remoti, è possibile disabilitarlo per l'organizzazione. Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione.


> [!NOTE]  
> L'abilitazione dell'accesso degli utenti remoti specifica solo che i server che gestiscono il servizio Access Edge supportano le comunicazioni con gli utenti remoti, ma gli utenti remoti non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione fino a quando non si configura anche in almeno un criterio per gestire l'uso dell'accesso degli utenti remoti. Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza). Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto. Per informazioni dettagliate sulla configurazione dei criteri per l'uso dell'accesso remoto agli utenti, vedere [configurare i criteri per il controllo dell'accesso degli utenti remoti in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Per abilitare o disabilitare l'accesso remoto agli utenti per l'organizzazione

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**e quindi su **configurazione bordo di Access**.

4.  Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti remoti per l'organizzazione, selezionare la casella di controllo **Abilita accesso remoto agli utenti** .
    
      - Per disabilitare l'accesso degli utenti remoti per l'organizzazione, deselezionare la casella di controllo **Abilita accesso remoto agli utenti** .

6.  Fare clic su **Commit**.

Per consentire agli utenti remoti di accedere ai server che utilizzano Skype for Business Server, è anche necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti remoti. Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti remoti in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'accesso degli utenti remoti tramite i cmdlet di Windows PowerShell

L'accesso degli utenti remoti può essere gestito tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server 2013 Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Per abilitare l'accesso remoto agli utenti

  - Per abilitare l'accesso remoto agli utenti, imposta il valore della proprietà **AllowOutsideUsers** su True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Per disabilitare l'accesso remoto agli utenti

  - Per disabilitare l'accesso remoto agli utenti, imposta il valore della proprietà **AllowOutsideUsers** su False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


