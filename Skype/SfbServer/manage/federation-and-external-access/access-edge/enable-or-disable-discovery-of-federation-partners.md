---
title: Abilitare o disabilitare l'individuazione di partner federativi
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: Al momento della distribuzione degli Edge Server e dell'abilitazione della federazione per l'organizzazione, dovrebbe essere stato specificato se supportare l'individuazione automatica dei domini partner federati.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817426"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Abilitare o disabilitare l'individuazione dei partner federativi in Skype for Business Server

Al momento della distribuzione degli Edge Server e dell'abilitazione della federazione per l'organizzazione, dovrebbe essere stato specificato se supportare l'individuazione automatica dei domini partner federati. Utilizzare la procedura descritta in questo argomento per modificare tale configurazione.

> [!NOTE]  
> Nella procedura che segue si presuppone che sia stata già abilitata la federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della federazione, vedere [Abilitare o disabilitare l'accesso degli utenti remoti.](enable-or-disable-remote-user-access.md)

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Per abilitare o disabilitare l'individuazione automatica dei domini federati per l'organizzazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.

4.  Nella pagina **Configurazione Access Edge** fare clic su **Globale**, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica configurazione Access Edge**, in **Abilita comunicazioni con utenti federati** selezionare o deselezionare la casella di controllo **Abilita individuazione dominio partner** per abilitare o disabilitare l'individuazione automatica dei domini partner.

6.  Fare clic su **Commit**.

Per consentire agli utenti federati di collaborare con gli utenti nella distribuzione di Skype for Business Server, è inoltre necessario aver configurato almeno un criterio di accesso esterno per supportare l'accesso degli utenti federati. Per informazioni dettagliate, vedere [Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica.](enable-or-disable-federation-and-public-im-connectivity.md) Per informazioni dettagliate sul controllo dell'accesso per domini federati specifici, vedere [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and Manage SIP [federated providers.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'individuazione di partner federativi tramite Windows PowerShell cmdlet

L'individuazione dei partner federativi può essere gestita utilizzando Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration federazione. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Per abilitare l'individuazione dei partner federativi

  - Per abilitare l'individuazione dei partner federati, impostare il valore della proprietà **EnablePartnerDiscovery** su True ($True). Tenere presente che è necessario abilitare l'instradamento DNS SRV per modificare il valore di questa proprietà.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Per disabilitare l'individuazione dei partner federativi

  - Per disabilitare l'individuazione dei partner federati, impostare il valore della proprietà **EnablePartnerDiscovery** su False ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

